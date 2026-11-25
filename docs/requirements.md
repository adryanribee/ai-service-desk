# Requirements specification

Status: planning baseline for product review; no implementation or test results are claimed.

## Product and actors
A Portuguese-language web service desk for any organization, deployed separately per company. It supports invited internal staff and external customers. MIT open source; installation, configuration, hosting and support may be offered commercially.

## Functional requirements
| ID | Requirement |
|---|---|
| FR-01 | First-run setup creates the installation's Master, organization and configurable departments, without preset business data. Master appoints administrators and manages sensitive integrations. |
| FR-02 | Administrator manages users, custom roles, department membership, categories, responsible staff, schedules, branding, welcome text and AI rules; can deactivate users without deleting history. |
| FR-03 | Invite-only onboarding via email or invite link; email/password and Google/Microsoft login; no public registration or MVP 2FA. |
| FR-04 | Requesters see only their own tickets; agents may belong to multiple departments and access their assigned department queues; administrators see all tickets. |
| FR-05 | Responsive Portuguese chat, light/dark theme, maximum five active conversations per requester; searchable completed history; no requirement for ChatGPT-style sidebar. |
| FR-06 | Every conversation creates a unique protocol; messages can be edited with visible edit marker and previous versions available to requester and authorized agent. |
| FR-07 | Stream AI responses progressively; accept and interpret permitted image/document attachments, no audio. |
| FR-08 | Notion-only knowledge ingestion; general and department-specific collections, not directly browsable by requesters. Cite permitted document identifiers without internal URLs or paths. |
| FR-09 | Classify, retrieve knowledge before automated routing, ask clarifying questions when ambiguous, escalate on insufficient evidence or explicit human request. |
| FR-10 | Department queue receives complete conversation; AI stops responding after handoff. Agents may correct classification, transfer, set priority and add private notes. |
| FR-11 | Priorities low, medium, high, critical; AI proposes and agent can override; critical tickets highlighted. Configurable department SLA and working hours. |
| FR-12 | In-app toast and notification events for tickets/messages; external notifications deferred. |
| FR-13 | AI and agents cannot conclude without clear requester confirmation; administrator can force closure with reason. Requester may cancel, only authorized agents/admin may reopen. No automatic expiry. |
| FR-14 | Configurable statuses mapped to core lifecycle semantics; status changes visible in conversation and audit log. |
| FR-15 | Per-response feedback, final satisfaction evaluation and AI-generated final summary (without resuming autonomous human-phase chat). |
| FR-16 | Configurable AI provider/model and independent embedding provider; recommended OpenAI, Gemini, Ollama and compatible custom APIs. Organization supplies credentials and pays usage. Master manages Notion integration; manual and scheduled sync. |
| FR-17 | Configurable retention/deletion policy; completed tickets archived rather than ordinary manual deletion; authorized policy-based erasure remains supported. |
| FR-18 | Optional fictitious demo seed; clean installation contains no customer data. |

## Nonfunctional requirements
- NFR-01: server-side role and resource authorization, including notes, attachments, RAG and custom roles; no privilege escalation.
- NFR-02: strong password hashing (Argon2id recommended), secrets outside source, encrypted integration credentials, no secrets in logs.
- NFR-03: LGPD transparency and explicit consent where applicable; record consent and support withdrawal; document lawful bases and retention rather than treating consent as universal.
- NFR-04: attachment type and size policies, content validation and safe storage; reject unsupported files.
- NFR-05: Docker-based local and cloud deployment; structured logs, audit events and health checks; availability status must distinguish provider failure from app failure.
- NFR-06: CI tests/lint required before merge; typed contracts and reproducible dependency management.
- NFR-07: test scenario five departments, 25 agents, five administrators and up to 100 requesters (130 simulated concurrent users as proposed upper-bound scenario, not proven capacity). Measure latency, errors, AI quality and cost before setting thresholds.
- NFR-08: user-facing Portuguese, public docs in English, documented installation with demo walkthrough.

## Open decisions
Precise SLA pause rules, invite expiry, custom status mapping, attachment limits, cost cap, deployment host, model availability, metrics thresholds, consent/legal retention specifics and backup procedure require implementation-stage validation. No backup/restore feature in MVP; production operations still need an explicit backup plan. See [acceptance criteria](acceptance-criteria.md).
