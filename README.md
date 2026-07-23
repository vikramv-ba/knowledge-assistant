# Knowledge Base Governance

This repository is the central source of truth for approved domain, system, integration, workflow, and sizing knowledge used by the team and any connected chatbot or retrieval service.

## Who can approve knowledge changes?

Knowledge changes must be approved through a pull request.

Approval requirements:

- The relevant `CODEOWNERS` reviewer must approve the change.
- At least one subject matter expert for the affected area must review the content.
- Architecture, integration, security, or sizing changes require approval from the designated technical owner.
- Business rules, domain definitions, and workflows require approval from the designated business or product owner.
- Changes affecting multiple areas require approval from each materially impacted owner.
- Authors must not be the sole approver of their own changes.

Emergency corrections may follow an expedited process, but must receive retrospective review within five business days.

## Which branch is authoritative?

The `main` branch is authoritative.

Only content merged into `main` is considered approved. Content in feature branches, pull requests, forks, local workspaces, or draft branches is not approved knowledge.

Production indexing and chatbot retrieval should use a specific commit from `main`, and the commit SHA should be recorded for traceability.

## How frequently must documents be reviewed?

| Document type | Minimum review frequency |
|---|---|
| Business rules | Every 3 months |
| Systems and integrations | Every 3 months |
| Sizing rules | Every 3 months |
| Operational workflows | Every 6 months |
| Domain overviews | Every 6 months |
| Stakeholder and ownership records | Every 6 months |
| Glossary content | Every 12 months |
| Architecture decision records | When the decision or its assumptions change |

Each active document must include:

- `owner`
- `last_reviewed`
- `next_review_due`
- `status`

Documents must also be reviewed when a related system, vendor, interface, business process, policy, contract, owner, or architecture decision changes. They must also be reviewed after relevant incidents or when estimates repeatedly differ from actual delivery outcomes.

Overdue documents should be flagged automatically and treated as potentially stale until reviewed.

## Which information must not be committed?

Do not commit:

- Passwords, API keys, tokens, certificates, private keys, or connection strings.
- Customer personal information or personally identifiable information.
- Payment card numbers, gift card numbers, bank details, or transaction-level sensitive data.
- Production credentials or privileged access instructions.
- Confidential employee information.
- Unremediated security vulnerabilities or sensitive attack details.
- Internal network information that creates material security risk.
- Production database extracts, logs, or screenshots containing sensitive data.
- Proprietary vendor information that cannot be redistributed.
- Legally privileged material.
- Confidential contracts, commercial terms, or unapproved financial information.
- Large binary files better stored in an approved document or asset repository.
- Content copied from another system without permission or source attribution.

## Who owns each domain, system, integration, and sizing rule?

Ownership must be declared in the YAML front matter of every knowledge document.

```yaml
---
id: system-paydock
title: Paydock
document_type: system
status: active
owner: Cart & Payments
business_owner: Cart Product
technical_owner: Cart Lead Engineer
last_reviewed: 2026-07-22
next_review_due: 2026-10-22
---
```

| Knowledge type | Accountable owner | Required reviewer |
|---|---|---|
| Domain | Product or business owner | Domain subject matter expert |
| System | Technical owner | Engineering lead or service owner |
| Integration | Owners of both connected systems | Integration or architecture representative |
| Workflow | Business process owner | Technical owner for affected systems |
| Business rule | Product or business owner | Relevant operational or compliance representative |
| Sizing rule | Product and engineering jointly | Delivery lead or estimation governance owner |
| Architecture decision | Decision owner | Architecture or technical governance group |
| Stakeholder record | Product or delivery owner | Relevant team lead |

The repository should maintain `.github/CODEOWNERS` so the correct reviewers are automatically requested.

```text
/knowledge/domains/            @organisation/ba-team
/knowledge/systems/            @organisation/engineering-team
/knowledge/integrations/       @organisation/engineering-team
/knowledge/workflows/          @organisation/product-team @organisation/engineering-team
/knowledge/sizing/             @organisation/product-team @organisation/im-team
/knowledge/arch-decisions/     @organisation/architecture-team
```

Use team aliases instead of individual usernames wherever possible.

If ownership is unknown, mark the document `status: draft`. Draft documents must not be indexed as approved knowledge.

## How are deprecated or superseded documents handled?

Do not delete deprecated or superseded documents solely to remove them from view.

Use one of these statuses:

- `deprecated`: No longer recommended, but may still describe a supported legacy state.
- `superseded`: Replaced by a newer document or decision.
- `archived`: Retained for historical reference and no longer operationally relevant.

A deprecated or superseded document must identify its replacement and effective date.

```yaml
status: superseded
superseded_by: system-new-order-service
deprecated_on: 2026-07-22
```

It must also include a visible notice near the top:

> **Superseded:** This document has been replaced by [New Order Service](../systems/new-order-service.md). Do not use this document for current-state decisions.

Handling rules:

- Deprecated, superseded, and archived documents are excluded from normal chatbot indexing and search results.
- They may be used only when historical context is explicitly requested.
- Existing links should be updated to the replacement document.
- The replacement document must explain material differences.
- Decision records should preserve the rationale for the change.
- Permanent deletion is allowed only when required by legal, security, privacy, or records-management policy.
- Deleted content should remain recoverable through Git history unless policy requires complete removal.

## Enforcement

These rules should be enforced through:

- Branch protection on `main`
- Required pull-request reviews
- `CODEOWNERS`
- Automated front-matter validation
- Review-date checks
- Broken-link checks
- Secret scanning
- Knowledge indexing only after merge to `main`
- Audit records containing the indexed commit SHA

Content that fails validation must not be merged or indexed.
