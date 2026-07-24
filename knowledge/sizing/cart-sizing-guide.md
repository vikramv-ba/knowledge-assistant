---
id: sizing-cart
title: Cart T-shirt Sizing Guide
document_type: sizing-rule
status: draft
owner: Cart & Payments
business_owner: Cart Product
technical_owner: Cart Lead Engineer
last_reviewed: 2026-07-24
next_review_due: 2026-10-24
---

# Cart T-shirt Sizing Guide

> **Draft:** This sizing guide is a placeholder. Sizing bands and system-impact rules will be updated as historical squad delivery data is validated.

## Provisional bands

Until validated sizing rules are published, use these bands from the approved glossary (`knowledge/glossary/checkout glossary.md`):

| Size | Sprints | Story points |
|---|---|---|
| X-Small (XS) | <= 1 sprint | 18 |
| Small (S) | 1 - 2 sprints | 36 |
| Medium (M) | 3 - 4 sprints | 72 |
| Large (L) | 5 - 6 sprints | 108 |
| X-Large (XL) | 6+ sprints | > 120 |

## Sizing principle

Base the recommended size primarily on **systems impacted** and integration complexity. Cross-reference `knowledge/systems/checkout-systems.md` for asset complexity ratings.

## System impact guidance (draft)

| Systems impacted | Typical size range | Notes |
|---|---|---|
| 1 low-complexity system | XS - S | Configuration or UI-only change |
| 1-2 medium-complexity systems | S - M | API or workflow change |
| 1 high-complexity system or 3+ systems | M - L | Major integration or orchestration |
| Multiple high-complexity systems or vendor dependencies | L - XL | Requires discovery and cross-squad coordination |

## Planned updates

- Validate bands against historical Cart squad delivery data
- Add per-scenario sizing examples (payments, fulfilment, refunds)
- Define adjustment factors for vendor lead time, compliance, and cross-platform dependencies
