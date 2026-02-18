# Feature: {Feature Title}

---

## Metadata

| Field             | Value                                                      |
|-------------------|------------------------------------------------------------|
| **File Name**     | `{YY-MM-DD}--{short-name}.md` *(naming convention only, omit from document)* |
| **Proposed Date** | YYYY-MM-DD                                                 |
| **Finished Date** | YYYY-MM-DD *(leave blank until completed)*                 |
| **Ticket**        | [XXX-XXXX](https://xxxxx.atlassian.net/browse/XXX-XXXX) |
| **Pull Request**  | [PR #XX](https://github.com/user/project/pull/XX) |
| **Owners**        | `@ldap1`, `@ldap2`                                         |
| **Effort**        | Low / Medium / High / Highest *(determined by AI Agent)*   |

---

## Summary

> *One or two sentences describing what this feature does and why it exists.*

---

## Context

### Background

*Describe the business or technical context that led to this feature. What problem does it solve? What opportunity does it address?*

### Motivation

*Why is this feature necessary now? What are the drivers behind this implementation?*

---

## Technical Specification

### Scope

*Define what is included and what is explicitly excluded from this feature.*

**In Scope:**
- Item 1
- Item 2

**Out of Scope:**
- Item 1
- Item 2

### Architecture

*Describe the technical approach, affected components, and integration points.*

#### Diagrams (recommended)

Use Mermaid for lightweight diagrams that work well for both humans and LLMs:

- Prefer `sequenceDiagram` for request/flow interactions (API, jobs, integrations).
- Prefer `flowchart` for high-level component flows.

**Naming conventions for diagrams**

- Use a descriptive heading above diagrams, e.g. `POST /x — Create something`.
- Use clear participant names (avoid abbreviations unless common).
- Keep diagrams at system interaction level; avoid line-by-line code detail.

### Dependencies

*List any external dependencies, services, or systems this feature relies on.*

---

## Risk Assessment

### Identified Risks

| Risk | Likelihood | Impact | Mitigation Strategy |
|------|------------|--------|---------------------|
| *Describe the risk* | Low / Medium / High | Low / Medium / High | *How will this be mitigated?* |

### Rollback Plan

*Describe the strategy to revert changes if the feature causes issues in production.*

### Monitoring and Alerts

*Define what metrics or alerts should be monitored after deployment to detect issues early.*

---

## Implementation Notes

*Any relevant notes about the implementation, trade-offs made, or important decisions.*

---

## References

### Previous Features

*Link to any related features that this builds upon or modifies. Only include if applicable.*

| Feature | Relationship |
|---------|--------------|
| [YYYY-MM-DD--feature-name](./YYYY-MM-DD--feature-name.md) | *Describe how it relates* |

### External Resources

*Links to external documentation, specifications, or resources.*

---

## Technical Debt and Next Steps

### Known Limitations

*Document any known limitations or shortcuts taken during implementation.*

### Future Improvements

- [ ] Improvement 1
- [ ] Improvement 2

---

## Disclaimers

*Any important disclaimers, known issues, or caveats users should be aware of.*

---

*Last updated: YYYY-MM-DD*

---
---

## Agent Instructions

<!--
AGENT:
- Ask for ticket + PR link if available
- Extract context from ticket/specs; don’t guess API fields
- Keep “decisions” as links to ADRs; keep rollout/ops notes here
- Fill progressively with the user and replace placeholders

Discovery questions:
- What problem does this solve and for whom?
- What is in-scope vs out-of-scope?
- What are key dependencies and risks?
- How will we validate (tests + metrics)?
-->
