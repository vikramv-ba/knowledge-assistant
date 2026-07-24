# BPMN Notation

Generate workflows in BPMN 2.0 style, not generic step lists.

## Elements to use

| Element | Use when |
|---|---|
| Start Event | Process begins |
| End Event | Process completes or terminates |
| User Task | Human action required |
| Service Task | Automated system action |
| Business Rule Task | Rule evaluation or decision logic |
| Sub-process | Reusable or nested flow |
| Exclusive Gateway | Single path decision (XOR) |
| Parallel Gateway | Concurrent paths (AND) |
| Intermediate Message Event | Async message between participants |
| Intermediate Timer Event | Wait, timeout, or scheduled trigger |

## Pools and swimlanes

Use pools or swimlanes where useful:

- Customer / User
- Product / Business
- Digital Platform
- Backend Services
- Vendor System
- Operations / Support
- Squad / Delivery Team

## What to show

- Main process flow
- System interactions
- Team and vendor handoffs
- Decision points and approvals
- Exception flows and rework loops
- Manual workarounds
- Failure states

## Output format

```text
Process name: [name]
Purpose: [why this process exists]

Participants / pools:
- [pool 1]
- [pool 2]

Main BPMN flow:
[Start Event] -> [Task/Gateway] -> ... -> [End Event]

Exception / alternate flows:
- [condition] -> [alternate path]

Dependencies and control points:
- [dependency or approval gate]

Open questions / assumptions:
- [item]
```

Use BPMN element names in square brackets. For complex flows, use indented sub-flows under each gateway branch.

## Cart examples

When modelling Cart workflows, cross-reference `knowledge/workflows/checkout-flows.md` and `knowledge/domains/checkout-domains.md` for known scenarios such as payment methods, fulfilment methods, and shipping fee calculation.
