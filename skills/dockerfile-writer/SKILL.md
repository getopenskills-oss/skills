---
name: dockerfile-writer
description: "Write small, secure, fast-building Dockerfiles and docker-compose files for an application, using multi-stage builds, layer caching and a non-root user. Use when the user asks to containerize an app or improve an existing Dockerfile."
---

# Dockerfile Writer

## When to use
- "Dockerize this app", "my image is 2 GB", "builds are slow", "write a docker-compose for local dev".

## Process
1. **Inspect the project**: language and version, package manager and lockfile, build command, start command, port, required env vars, files that must not be copied (secrets, `node_modules`, `.git`).
2. **Choose a base image** pinned to a specific version (`node:22-slim`, `python:3.13-slim`, distroless for compiled apps). Avoid `latest`.
3. **Write a multi-stage build**: a build stage with dev tooling, a minimal runtime stage with only what runs.
4. **Order layers for caching**: copy lockfiles → install dependencies → copy source → build.
5. **Add `.dockerignore`.**
6. **Build and run it** to verify; report image size.

## Template (Node example)
```dockerfile
FROM node:22-slim AS deps
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm ci

FROM deps AS build
COPY . .
RUN npm run build && npm prune --omit=dev

FROM node:22-slim
WORKDIR /app
ENV NODE_ENV=production
COPY --from=build /app/node_modules ./node_modules
COPY --from=build /app/dist ./dist
COPY package.json ./
USER node
EXPOSE 3000
CMD ["node", "dist/server.js"]
```

## Checklist
- Runs as a non-root user.
- No secrets in the image (use runtime env vars or build secrets, never `ARG`/`ENV` with real values).
- Exec-form `CMD`/`ENTRYPOINT` so signals reach the process; add `HEALTHCHECK` when the platform uses it.
- One process per container; logs to stdout/stderr.
- For compose: named volumes for data, `depends_on` with health conditions, `.env` file for local values only.

## Rules
- Do not invent build or start commands — read them from the project.
- Explain any trade-off (e.g. alpine vs. slim for native modules).
