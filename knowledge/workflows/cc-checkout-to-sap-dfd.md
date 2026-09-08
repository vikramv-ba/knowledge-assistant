---
id: workflow-cc-checkout-to-sap-dfd
title: Credit card checkout to SAP data flow
document_type: workflow
status: draft
owner: Cart & Payments
business_owner: Cart Product
technical_owner: Cart Lead Engineer
last_reviewed: 2026-09-08
next_review_due: 2026-12-08
source: User-provided swimlane process diagram (CC checkout, 3DS, CommerceTools, DOM/OMFP, Order Master, B2B, SAP)
---

# Credit card checkout to SAP — data flow diagram

**Status: draft.** This is a data-flow view of a supplied swimlane process diagram. It is not approved knowledge until merged to `main` and reviewed by process and system owners.

It describes **what data moves between systems**, not every UI click. Process names and stores below are taken from the source diagram and aligned to known Cart assets where those names already exist (`Paydock`, `CommerceTools`, `OMFP`, `Order Master`).

## Notation

| Symbol | Meaning |
|---|---|
| Stadium | External entity (person or system outside the process boundary) |
| Circle | Process that transforms data |
| Cylinder | Data store |
| Document | File or batch artefact |
| Solid arrow | Data flow (labelled with the payload) |
| Dotted arrow | Async, scheduled, or exception flow |

## Level 0 — context

The checkout-to-finance process sits between the customer, the issuing bank, and SAP.

```mermaid
flowchart LR
    customer([Customer])
    bank([Issuing Bank])
    sap([SAP])
    ctx(("P0 Checkout to finance"))

    customer -->|"Fulfilment, address, card, 3DS response"| ctx
    ctx -->|"Order success or payment cancelled"| customer
    ctx -->|"3DS challenge"| bank
    bank -->|"3DS result and payment commit"| ctx
    ctx -->|"Enriched sales and account mapping"| sap
```

## Level 1 — data flows

```mermaid
flowchart LR
    subgraph externals ["External entities"]
        customer([Customer])
        bank([Issuing Bank])
        sap([SAP])
    end

    subgraph checkout ["Online checkout"]
        p1(("P1 Capture checkout"))
        p2(("P2 Orchestrate payment"))
        p3(("P3 Authorise card"))
        p4(("P4 Convert cart to order"))
        d1[("D1 Cart and order")]
        d2[("D2 Payment records")]
    end

    subgraph fulfilment ["Fulfilment and finance"]
        p5(("P5 Receive confirmed order"))
        p6(("P6 Transform and aggregate sales"))
        p7(("P7 Enrich and schedule transfer"))
        d3[("D3 Confirmed orders")]
        salesFile[/"D4 Aggregated sales file"/]
    end

    customer -->|"Delivery method and address"| p1
    customer -->|"Card details"| p2
    p1 -->|"Checkout session"| p2
    p1 -->|"Cart contents"| d1
    p2 -->|"Card payload"| p3
    p3 -->|"3DS challenge"| bank
    customer -->|"3DS response"| bank
    bank -->|"Auth success and commit"| p3
    bank -.->|"Auth failed"| p3
    p3 -->|"Authorisation result"| d2
    p3 -->|"Payment confirmed"| p4
    p3 -.->|"Cancel payment"| p2
    p2 -.->|"Payment cancelled"| customer
    p4 -->|"Write order"| d1
    p4 -->|"Order confirmation"| customer
    p4 -->|"Confirmed order"| p5
    p5 -->|"Order for fulfilment"| d3
    d3 -->|"Order data"| p6
    p6 -->|"Sales, returns, cancellations, accruals"| salesFile
    salesFile -->|"S3 upload"| p7
    p7 -->|"Enriched payment file on schedule"| sap

    style externals fill:#C2E5FF,stroke:#3DADFF
    style checkout fill:#CDF4D3,stroke:#66D575
    style fulfilment fill:#FFECBD,stroke:#FFC943
```

## Process dictionary

| ID | Process | System | Data in | Data out |
|---|---|---|---|---|
| P1 | Capture checkout | Cart UI / CommerceTools | Fulfilment method, delivery address, cart | Checkout session, cart snapshot |
| P2 | Orchestrate payment | Paydock | Invoke CC method, card details, cancel events | Hosted CC capture, payment cancelled message |
| P3 | Authorise card | MPGS and issuing bank | Card payload, 3DS response | Authorisation result, commit or cancel |
| P4 | Convert cart to order | CommerceTools | Payment confirmed, cart | Order record, customer success message, confirmed order to DOM/OMFP |
| P5 | Receive confirmed order | DOM / OMFP | Confirmed order | Fulfilment order store |
| P6 | Transform and aggregate sales | Order Master | Order id, account, product, transaction price (ECB or local) | Aggregated sales file covering invoiced, processed, returned, cancelled, accruals |
| P7 | Enrich and schedule transfer | B2B | Sales file | Account-enriched payment file transferred on schedule to SAP |

## Data stores and artefacts

| ID | Store / artefact | Held by | Contents |
|---|---|---|---|
| D1 | Cart and order | CommerceTools | Cart, converted order |
| D2 | Payment records | Paydock / MPGS | Card authorisation, commit, cancel |
| D3 | Confirmed orders | DOM / OMFP | Fulfilment-ready order |
| D4 | Aggregated sales file | Object storage (S3 upload) | CSV/doc of aggregated sales data |

SAP receives transactions and account mapping and updates accounting entries. That ledger sits inside SAP, outside this process boundary.

## Control notes from the source diagram

- Customer success is shown when CommerceTools converts cart to order. DOM/OMFP confirmation is **async** and is not required before the success message.
- 3DS failure cancels payment in MPGS and Paydock and shows a cancelled message to the customer.
- B2B transfer to SAP is **scheduled** (batch), not real-time checkout.

## Assumptions and open questions

These items are inferred from the diagram or named in Cart knowledge; they are not independently verified here.

1. CT in the source diagram is treated as CommerceTools.
2. DOM/OMFP is treated as the AU fulfilment handoff (`OMFP Order Transfer` in Cart systems). NZ DOM transfer is not shown in the source diagram.
3. Whether Order Master reads from DOM/OMFP, CommerceTools, or both is not specified beyond “receive order data”.
4. File format is shown as CSV in some labels and “doc” in others; treat the artefact as an aggregated sales file until the B2B contract is confirmed.
5. Sale returned / cancelled / accruals paths are transformations inside P6; they are not expanded as separate checkout journeys.

## Related knowledge

- `knowledge/systems/checkout-systems.md` — Paydock, CommerceTools, OMFP Order Transfer, Order Master
- `knowledge/domains/checkout-domains.md` — credit/debit card payment recorded on Paydock
