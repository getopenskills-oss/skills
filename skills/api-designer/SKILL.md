---
name: api-designer
description: "Design clean, consistent HTTP/REST APIs: resources, endpoints, request and response shapes, errors, pagination, auth and versioning, delivered as an OpenAPI sketch. Use when the user is designing or reviewing an API."
---

# API Designer

## When to use
- Designing a new API or endpoint, or reviewing one before it ships.
- "What should this endpoint look like?", "how do I paginate / version / return errors?"

## Process
1. **Start from use cases**, not tables: list what clients need to do (3–10 jobs), and who the clients are (browser, mobile, other services, AI agents).
2. **Model resources** as nouns (`/orders`, `/orders/{id}/items`); use HTTP methods for verbs. Use an action sub-resource only for real commands (`POST /orders/{id}/cancel`).
3. **Define each endpoint**: method, path, auth, request body, success response, error responses, idempotency.
4. **Apply conventions consistently** (below), then write an OpenAPI 3.1 sketch.
5. **Review** for breaking-change risk, security, and what happens at 10× the data.

## Conventions
- JSON with consistent casing (pick `camelCase` or `snake_case` once).
- Status codes: 200 read, 201 created (+ `Location`), 204 no content, 400 invalid input, 401 not authenticated, 403 not allowed, 404 not found, 409 conflict, 422 validation, 429 rate limited.
- One error shape everywhere: `{ "error": { "code": "invalid_email", "message": "…", "field": "email" } }`.
- Pagination: cursor-based for feeds (`?cursor=…&limit=50` → `nextCursor`); offset only for small, stable lists. Always cap `limit`.
- Filtering and sorting via query params (`?status=open&sort=-createdAt`).
- Timestamps in ISO 8601 UTC; money as integer minor units plus currency.
- Idempotency keys (`Idempotency-Key` header) for POSTs that create payments or orders.
- Versioning: additive changes are free; breaking changes need a new version (`/v2` or a header) and a deprecation period.

## Security checklist
- Authenticate every non-public endpoint; authorize per object (a user can only read *their* order).
- Validate and bound every input; never trust IDs from the client.
- Rate-limit; never leak stack traces or internal IDs in errors.

## Output
1. Endpoint table: method, path, purpose, auth.
2. OpenAPI 3.1 YAML sketch with schemas and example responses.
3. Open questions and trade-offs.
