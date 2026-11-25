# Use cases

| ID | Actor | Main flow | Exception |
|---|---|---|---|
| UC-01 | Master | Install, create Master, configure organization, invite admins, connect Notion and AI | Invalid credentials fail safely; setup cannot be repeated publicly |
| UC-02 | Admin | Configure department, users, roles, hours, SLA, branding | Unauthorized grant denied |
| UC-03 | Requester | Accept invitation, authenticate, open chat and get protocol | Sixth active chat denied; invalid attachment rejected |
| UC-04 | AI | Classify, retrieve, respond with safe source label, request confirmation | Ambiguous input clarified; lack of evidence or human request routed |
| UC-05 | Agent | Open authorized queue, view context, reply, correct priority, transfer or note | Unauthorized department blocked; AI stops on handoff |
| UC-06 | Requester | Confirm resolution or cancel, rate response and overall service, search completed history | Ambiguous thanks cannot close |
| UC-07 | Admin/agent | Admin force closes with justification; authorized agent/admin reopens | Requester reopening denied; audit event preserved |
| UC-08 | Master | Configure model and embedding provider, synchronize Notion manually or periodically | Failed sync reported, no unauthorized documents retrieved |
