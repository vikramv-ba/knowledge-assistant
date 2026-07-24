# Dependency Taxonomy

Identify digital, cross-platform, squad, and vendor dependencies across:

- Web and app
- Backend and APIs
- Data and analytics
- Search and promotions
- Payments and inventory
- Fulfilment and customer service
- Vendors
- Security, privacy, and compliance
- Operations and release management

## Categories

| Category | Description | Examples |
|---|---|---|
| Digital | Changes within digital platforms | Cart UI, CommerceTools Service |
| Cross-platform | Dependencies on other digital squads | B2B, Analytics, OMFP |
| Squad | Internal delivery team capacity or sequencing | Cart & Payments, Checkout experience |
| Vendor | Third-party systems or SaaS | Paydock, Vii, Mirakl, Experian/QAS |
| Data | Data pipelines, quality, or reporting | Fintech reporting pipeline, Analytics |
| Integration | APIs, events, or middleware | Order Transfer, Cart availability API |
| Release | Deployment, feature flags, or sequencing | Release management, environment readiness |
| Compliance | Security, privacy, or regulatory | PCI, gift card handling, tax |

## Assessment fields

For each dependency include:

| Field | Values / guidance |
|---|---|
| Dependency | What is needed and from whom |
| Category | From table above |
| Owner / vendor | Squad, team, or vendor name |
| Criticality | High / Medium / Low |
| Lead time risk | High / Medium / Low / Unknown |
| Notes | Assumptions, sequencing, or discovery needed |

## Criticality

- **High**: blocks delivery if unresolved
- **Medium**: may delay delivery or reduce scope
- **Low**: manageable with normal planning

## Lead time risk

- **High**: long vendor lead time, unknown integration, or cross-squad contention
- **Medium**: moderate coordination or environment dependency
- **Low**: well-understood, owned by the delivery squad
- **Unknown**: requires discovery

## Sources

Cross-reference:

- `knowledge/systems/checkout-systems.md`
- `knowledge/integrations/system-touchpoints.md`
- `knowledge/stakeholders/checkout-stakeholders.md`
