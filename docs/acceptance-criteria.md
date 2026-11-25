# Acceptance criteria and release gate

All items below are planned verification, not passed tests. Product owner approves final release after evidence review.

## Planning approval

The product owner approved the planning baseline and release criteria on 2026-11-24 (America/Sao_Paulo), authorizing the foundation phase. This is not approval to publish the MVP, nor evidence that any acceptance test has passed. Final release approval remains a separate gate.

## Definition of Done
- [ ] Requirement and implementation traceable; code reviewed, tests and lint pass, documentation updated; evidence linked in Notion.
- [ ] No unresolved critical security or correctness issue; known limitations documented.

## MVP release checklist
- [ ] AC-01 (FR-01–04): clean install creates Master; invites, login, roles, department isolation and deactivation tested; no public self-registration or default secret.
- [ ] AC-02 (FR-05–07): responsive Portuguese chat, themes, five-active-ticket limit, protocols, search, edit history, streaming and permitted image/document handling verified.
- [ ] AC-03 (FR-08–10,16): Notion manual/automatic sync, scoped retrieval, safe source labels, independent embeddings and compatible providers verified; unclear/unanswerable requests escalate and history survives handoff; AI stops replying.
- [ ] AC-04 (FR-11–14): department queue, transfer, private notes, priority, critical highlight, SLA, notifications, custom statuses and audit events verified; no unilateral closure or inactivity expiry; admin override reason; cancellation/reopening permissions.
- [ ] AC-05 (FR-15,17): feedback, final summary, archive and retention policies verified; privacy requests handled appropriately.
- [ ] AC-06 (NFR-01–04): server-side authorization, strong hash, secret isolation, attachment validation, prompt injection and access-boundary tests, privacy/consent review.
- [ ] AC-07 (NFR-05–07): local/cloud installation documented and verified; health checks, safe logs, provider failure behavior; CI passes; load scenario 25 agents + 5 admins + up to 100 requesters; record actual latency, errors, classification quality and cost; thresholds agreed before release.
- [ ] AC-08 (FR-18,NFR-08): optional synthetic seed, clean install tutorial, English README, MIT license notice, real screenshots, five-minute demo script and short video; no real company data or secrets.
- [ ] AC-09: owner reviews evidence and approves release; unresolved blockers prevent release.

## Scope exclusions
No audio, external support channels, analytics dashboard, multi-tenant deployment, direct knowledge uploads, automatic multi-department splitting, AI agent suggestions, automatic expiry, built-in backup/restore, or Redis/Celery in MVP. External notification delivery deferred. Production backup/restore procedure and exact hosting budget must be considered before real deployment.
