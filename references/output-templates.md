# Output Templates

Use these schemas for Squad Pulse assessments. Keep headings and field names consistent.

## 1. Feature Kickoff Summary

| Field | Content |
|---|---|
| Feature name | |
| Business problem | |
| Customer or user need | |
| Desired outcome | |
| In scope | |
| Out of scope | |
| Success metrics | |
| Assumptions | |
| Constraints | |

## 2. Requirements

### Business requirements

| ID | Requirement | Priority | Source |
|---|---|---|---|

### Functional requirements

| ID | Requirement | Priority | Source |
|---|---|---|---|

### Non-functional requirements

| ID | Category | Requirement | Priority |
|---|---|---|---|

### Data requirements

| ID | Data element | Source system | Consumer | Notes |
|---|---|---|---|---|

### Acceptance criteria

Use Given/When/Then format:

```text
Given [precondition]
When [action]
Then [expected outcome]
```

### Assumptions

- 

### Open questions

- 

## 3. System Touchpoints

| System / platform | Role | Type | Impact | Notes |
|---|---|---|---|---|

Impact levels:

- **High**: core system change or major integration
- **Medium**: configuration, data, API, or workflow change
- **Low**: minor, indirect, or reporting-only impact
- **Unknown**: requires discovery

## 4. BPMN Workflow

See `bpmn-notation.md` for element conventions.

| Section | Content |
|---|---|
| Process name | |
| Purpose | |
| Participants / pools | |
| Main BPMN flow | |
| Exception / alternate flows | |
| Dependencies and control points | |
| Open questions / assumptions | |

## 5. Stakeholder Map

| Stakeholder / team | Role | Interest | Required engagement | RACI |
|---|---|---|---|---|

RACI: R = Responsible, A = Accountable, C = Consulted, I = Informed.

Include Product, Business, Delivery, BA, Engineering, Architecture, Data, Security, Risk, Operations, Support, Analytics, Release Management, and Vendors where relevant.

## 6. Dependencies

| Dependency | Category | Owner / vendor | Criticality | Lead time risk | Notes |
|---|---|---|---|---|---|

Criticality: High blocks delivery; Medium may delay or degrade scope; Low is manageable.

Lead time risk: High, Medium, Low, Unknown.

## 7. T-shirt Sizing

| Field | Content |
|---|---|
| Recommended size | XS / S / M / L / XL |
| Confidence | High / Medium / Low |
| Rationale | |
| Key sizing drivers | |
| What would increase size | |
| What would reduce size | |

## 8. Monte Carlo Forecast

| Field | Content |
|---|---|
| Method | |
| Dataset used | |
| Number of simulations | |
| Confidence quality | |
| P50 duration / date | |
| P75 duration / date | |
| P85 duration / date | |
| P95 duration / date | |
| Recommended delivery commitment | |
| Caveats | |

## 9. Confidence Rating

| Rating | Rationale |
|---|---|
| High / Medium / Low | |

## 10. Risk Analysis

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|

## 11. Clarifying Questions

Ask no more than 5 questions. Prioritise outcome, customer/user, platforms/systems, vendors, target date, historical data, and minimum viable scope.
