# Workflows

## Request lifecycle
```mermaid
flowchart TD
 A[Invited requester starts chat] --> B[Persist ticket and protocol]
 B --> C[AI classifies and retrieves authorized knowledge]
 C --> D{Clear intent and sufficient evidence?}
 D -->|Ambiguous| E[Ask for clarification]
 E --> C
 D -->|Answerable| F[Stream grounded response]
 D -->|Actionable or insufficient evidence| G[Route to department queue]
 F --> H{Requester confirms resolution?}
 H -->|Yes| I[Complete and record summary and feedback]
 H -->|No| C
 G --> J[Human support with full history]
 J --> K[Waiting for requester]
 K -->|Confirmed| I
 K -->|Needs more help| J
```
Explicit human request bypasses automated answering. AI stops autonomous chat at handoff. No inactivity expiration. Cancellation is available to requester; authorized admin can force closure with reason; authorized agent/admin may reopen.

## Illustrative cases
- IT: password-reset question with sufficient authorized knowledge is answered and closed only after confirmation.
- Maintenance: machine repair request is routed to configured maintenance queue; agent responds and awaits confirmation.
- HR: leave-policy question uses authorized department knowledge without exposing the internal Notion URL; if uncertain, escalate.
These departments are examples, not seeded mandatory departments.

## State transitions
AI support → human support or waiting for requester or completed after confirmation; human support → waiting for requester; waiting → previous support mode or completed; active → cancelled by requester; completed/cancelled → human support by authorized agent/admin subject to policy. Administrative override is audited. Custom statuses map to core states; SLA pause behavior is pending.
