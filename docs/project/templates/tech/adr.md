---
title: "ADR: {Short decision title}"
type: decision
audience: engineers + LLMs
last_updated: YYYY-MM-DD
---

## Metadata

| Field | Value |
|---|---|
| **File Name** | `YYYY-MM-DD--short-title.md` *(naming convention only, omit from document)* |
| **Domain** | `{domain_name}` |
| **Status** | Proposed / Accepted / Superseded |
| **Deciders** | `@ldap1`, `@ldap2` *(optional)* |
| **Date** | YYYY-MM-DD |
| **Supersedes** | *(optional link)* |
| **Superseded by** | *(optional link)* |

## Context

What problem are we solving? What constraints matter?

## Decision

What we decided, in one paragraph.

## Options considered

| Option | Pros | Cons | Risks | Complexity |
|---|---|---|---|---|
| A — *chosen* |  |  |  | Low/Med/High |
| B |  |  |  | Low/Med/High |

## Consequences

- Positive: ...
- Negative: ...
- Follow-ups: ...

## Related docs

- Architecture: `../architecture.md`
- API docs: `../api/README.md`
- Feature rollout (if any): `../features/`

<!--
AGENT:
- Keep ADRs short and decision-focused.
- Put “what changed in code” in feature docs, not here.
- Prefer linking to code pointers from feature docs.
-->