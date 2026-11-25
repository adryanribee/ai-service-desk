# Initial API contracts (proposed)

REST under /api/v1, OpenAPI generated from Pydantic models; SSE for assistant message streaming. All authenticated routes enforce role and object permissions. Use structured errors with code, message and correlation_id; 401 unauthenticated, 403 unauthorized, 409 state conflict, 422 validation, 429 rate limit, 503 dependency unavailable. Avoid leaking resource existence where appropriate.

| Method and path | Contract |
|---|---|
| POST /setup | One-time Master/organization creation; disabled after setup |
| POST /auth/invitations | Authorized role sends invitation; expiring single-use token proposed |
| POST /auth/login | Credentials → session; OAuth callbacks separately |
| GET/POST /departments | List authorized / configure by admin |
| GET/POST /tickets | Paginated authorized list / create with protocol, state, timestamps |
| GET /tickets/{id} | Authorized ticket and history |
| POST /tickets/{id}/messages | Body and attachment IDs → persisted message |
| PATCH /tickets/{id}/messages/{message_id} | New revision, original retained |
| GET /tickets/{id}/events | Authorized status/message event stream, SSE |
| PATCH /tickets/{id}/assignment | Department/agent changes with reason |
| PATCH /tickets/{id}/priority | Validated agent override |
| POST /tickets/{id}/notes | Internal note, agent only |
| PATCH /tickets/{id}/status | Validated target state, reason and confirmation evidence |
| POST /tickets/{id}/feedback | Response or overall rating |
| POST /attachments | Validated private upload |
| PUT /settings/providers | Master-only provider config; secrets write-only |
| POST /knowledge/sync | Master-authorized sync job |
| GET /knowledge/sync/{id} | Sync status and safe errors |
| GET /health/live; /health/ready | Process and dependency readiness |

Classification result: intent, department_id, category_id, priority, confidence signal, rationale. Server verifies configured IDs, authorization and allowed transition; confidence is not assumed calibrated. Contract version, exact schemas and pagination cursor to be finalized during foundation/backend.
