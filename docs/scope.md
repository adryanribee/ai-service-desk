# AI Service Desk — Product scope

Status: Approved product scope; detailed planning baseline submitted for review.

## 1. Product vision

AI Service Desk is a configurable support platform for organizations of different sizes and industries. It addresses a common operational scenario: fragmented support channels, manual request routing and repetitive questions that consume staff time. This is a hypothetical use case, not a claim about a specific organization.

The goal is to deliver an efficient, maintainable portfolio project that demonstrates full-stack engineering, AI-assisted request routing and retrieval-augmented generation (RAG).

## 2. MVP scope

| ID | Capability | Scope |
| --- | --- | --- |
| SC-01 | Deployment | One independent installation per organization; no shared multi-tenant instance. |
| SC-02 | Initial setup | First-run configuration for the organization, initial Master, administrators and departments. No mandatory predefined departments. |
| SC-03 | Branding | Configurable service desk name, logo and colors. |
| SC-04 | Access | Internal staff and external customers may use the platform by invitation only; public self-registration is excluded. |
| SC-05 | Channel | Web application with a conversational chat interface as the sole request entry channel. |
| SC-06 | Attachments | Users can attach images and documents to conversations. Supported formats, limits and storage policies are to be defined. |
| SC-07 | AI triage | Interpret requests, classify them using organization-configured departments and route actionable requests to the appropriate team. |
| SC-08 | Knowledge base | Notion is the sole knowledge source for the MVP. Document ingestion, vector indexing and retrieval support grounded answers with traceable sources. |
| SC-09 | Human support | Department-specific access and workspace to receive, respond to and transfer requests. Agents require requester confirmation; administrators may override with an audited reason. |
| SC-10 | Resolution | AI may close a request only after an explicit, unambiguous confirmation of successful resolution from the requester. Ambiguous acknowledgements require clarification. |
| SC-11 | AI provider | Configurable AI provider rather than a hard dependency on OpenAI; OpenAI, Gemini and Ollama recommended; compatible custom providers and separate embedding configuration. |
| SC-12 | Language | Portuguese user interface and support interactions. |
| SC-13 | History | Preserve request and conversation history with appropriate access controls and auditability. |

## 3. Outside the MVP

- Shared multi-tenant hosting, public self-registration and mandatory preset departments.
- WhatsApp, email and Microsoft Teams support channels.
- Traditional ticket creation forms alongside chat.
- Direct document upload as a knowledge-base ingestion channel (conversation attachments remain in scope).
- Administrative analytics dashboard and multilingual interface.
- Redis/Celery and advanced optimization until supported by measured bottlenecks.

## 4. Resolution policy

Statements such as “Funcionou perfeitamente” or “Meu problema foi resolvido” may confirm resolution in context. “Obrigado”, “Vou tentar” and partial success are not sufficient. Failed or uncertain requests remain open for continued support or human escalation. The closure action must be enforced by application rules rather than keyword matching alone.

## 5. Detailed planning baseline

See [requirements](requirements.md), [business rules](business-rules.md), [workflows](workflows.md), [architecture](architecture.md), [API contracts](api-contracts.md), [use cases](use-cases.md) and [acceptance criteria](acceptance-criteria.md). Additional approved scope: five active chats, four base roles including Master, editable messages with revisions, streaming, attachment interpretation, queues, SLA, in-app notifications, custom statuses, feedback, final summary, no automatic expiry, local/cloud deployment, MIT source with paid services. Audio and external notifications are outside MVP. Detailed operational limits and thresholds remain open. Public demonstrations use fictitious data only.
