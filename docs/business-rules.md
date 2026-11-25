# Business rules

| ID | Rule |
|---|---|
| BR-01 | One organization per independent deployment. Master is created during secure one-time setup, appoints admins and manages integration secrets. No universal developer account. |
| BR-02 | Invitation required even for federated login. All permissions enforced server-side; custom roles cannot exceed grantor authority. |
| BR-03 | Maximum five active conversations per requester; enforce atomically. Completed/cancelled tickets do not count. |
| BR-04 | Every conversation receives an immutable protocol and persistent message history. Edits create revisions, never overwrite audit history. |
| BR-05 | Consult authorized knowledge before automated routing; direct human request must not be blocked by retrieval. Ask for clarification if classification is ambiguous. No fabricated answers. |
| BR-06 | Escalation routes to one best-fit department with recorded rationale; multiple departments may be handled through transfer, not automatic splitting in MVP. |
| BR-07 | On human handoff, preserve history and stop autonomous AI replies. Queue is department-based; agents can correct classification and transfer. |
| BR-08 | AI suggests low/medium/high/critical priority; agents can override with audit. Critical tickets highlighted. SLA uses configured department schedules; precise pause/transfer calculation pending. |
| BR-09 | AI/agent closure requires unequivocal requester confirmation in context. Thanks alone, partial success or planned attempt are insufficient. Administrator override requires reason and audit. |
| BR-10 | Requester can cancel; agents/admin can reopen subject to access; no inactivity expiry. Reopening must respect active-ticket limit policy (edge case pending). |
| BR-11 | Core states: AI support, human support, waiting for requester, completed, cancelled. Custom display statuses map to core semantics; queue assignment is tracked separately. Awaiting test was mentioned but its exact mapping remains to validate. |
| BR-12 | State changes are visible as chat system events and in immutable audit trail. Internal notes are never exposed to requesters. |
| BR-13 | Final satisfaction and summary are recorded; summary failure does not undo valid closure. AI summary is not an autonomous reply. |
| BR-14 | Archive completed tickets; retention-based erasure and privacy requests are handled separately with authorization and audit minimization. |
| BR-15 | Notion content is only accessible through authorized retrieval, with safe source labels but no internal paths; exclude removed/revoked documents from retrieval (technical recommendation). |
