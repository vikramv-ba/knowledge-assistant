# Systems Catalog

This reference points to the approved systems knowledge base. Do not duplicate system definitions here.

**Source of truth:** `knowledge/systems/checkout-systems.md`

## Known Cart assets

| ID | System | Complexity | Role |
|---|---|---|---|
| AST-001 | Paydock | High | SaaS payments platform; records all transaction types |
| AST-002 | CommerceTools Service | Medium | Abstraction layer between Cart UI and Commerce Tools |
| AST-003 | Shipping rate calculator | High | Applies business rules for shipping fees |
| AST-004 | Order Transfer | Medium | Lambda transferring NZ orders to DOM |
| AST-005 | OMFP Order Transfer | Medium | Lambda transferring AU orders to OMFP middleware |
| AST-006 | Cart availability API | Medium | Stock on hand for 1P and 3P items |
| AST-007 | Vii | NA | Gift card provider |
| AST-008 | Refund service | Medium | Calculates refund amounts; triggers Paydock |
| AST-009 | Gift card refund registry | Low | Records gift card refunds for CSC |
| AST-010 | Experian/QAS | Low | Address validation SaaS |
| AST-011 | Order Master | High | Orchestrates order information to downstream systems |
| AST-012 | SendGrid | Low | Post-purchase email comms |
| AST-013 | Fintech reporting pipeline | High | Lambdas for financial reporting |
| AST-013 | Cart UI | Low | Web checkout front end |

For touchpoints and integration roles, also read `knowledge/integrations/system-touchpoints.md`.

When a system is not listed, mark impact as **Unknown** and add an open question for discovery.
