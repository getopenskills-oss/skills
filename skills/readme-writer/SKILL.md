---
name: readme-writer
description: "Write or improve a project README that gets a new user from zero to running in minutes: what it is, install, quick start, configuration, and how to contribute. Use when the user asks for a README or better project docs."
---

# README Writer

## When to use
- A repository has no README, or the README is outdated or confusing.
- The user is about to publish or open-source a project.

## Process
1. **Learn the project from the source, not from guesses.** Read the manifest (`package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`), entry points, scripts, `.env.example`, Dockerfile, CI config, and the license.
2. **Run the setup steps yourself if you can**, and note anything that is missing or fails.
3. **Write for the first five minutes of a newcomer.** They want to know what it is, whether it fits their need, and how to see it work.
4. Ask the user only for things the code cannot tell you (audience, project status, roadmap).

## Structure
```
# Project name
One sentence: what it does and for whom.

(optional: screenshot or short demo GIF)

## Features            — 3–6 bullets, concrete
## Quick start         — copy-pasteable commands from clone to running
## Configuration       — env vars / options table: name, default, description
## Usage               — the 2–3 most common tasks with examples
## Development         — tests, lint, project layout (only if contributors exist)
## Contributing        — or link to CONTRIBUTING.md
## License
```

## Rules
- Every command must be real and in the right order; mark placeholders clearly (`<your-api-key>`).
- Prefer short sections and code blocks over long paragraphs.
- State requirements explicitly (runtime versions, OS, accounts, API keys).
- Never invent features, badges, benchmarks, or install methods the project does not have.
- Keep secrets out of examples.
