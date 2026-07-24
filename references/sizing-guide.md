# Sizing Guide

Base t-shirt sizing on systems impacted and delivery complexity. Use `knowledge/sizing/cart-sizing-guide.md` as the primary sizing rule source. When that file is incomplete, use the provisional bands below from the approved glossary.

## Provisional t-shirt bands

| Size | Sprints | Story points |
|---|---|---|
| X-Small (XS) | <= 1 sprint | 18 |
| Small (S) | 1 - 2 sprints | 36 |
| Medium (M) | 3 - 4 sprints | 72 |
| Large (L) | 5 - 6 sprints | 108 |
| X-Large (XL) | 6+ sprints | > 120 |

Label sizing as **provisional** until `knowledge/sizing/cart-sizing-guide.md` is updated with validated historical data.

## Sizing drivers

Consider:

- Cycle time and lead time
- Throughput and story count
- Completed features of similar type
- Defects and rework history
- Systems impacted and integration count
- Squads involved
- Vendor involvement
- Dependency count and criticality
- Release complexity
- Discovery effort
- Testing complexity
- Operational change
- Compliance and security effort

## System complexity reference

Use complexity ratings from `knowledge/systems/checkout-systems.md`:

| Complexity | Typical sizing impact |
|---|---|
| High | Likely increases size by at least one band when core to the feature |
| Medium | Moderate impact; may add integration and testing effort |
| Low | Minor impact unless many systems are touched |
| NA | Assess by integration role, not asset complexity alone |

## Output requirements

For every size recommendation include:

1. Recommended size (XS / S / M / L / XL)
2. Confidence (High / Medium / Low)
3. Rationale
4. Key sizing drivers
5. What would increase the size
6. What would reduce the size

## When data is missing

Ask for historical squad delivery data. Label the size as provisional and state assumptions. Recommend the minimum data needed for stronger sizing.
