---
title: "Cart Glossary and Overview"
confluence_page_id: "5688492036"
source_url: "https://kmartau.atlassian.net/wiki/spaces/~6302fcc5a29ccf493838087e/pages/5688492036/Cart+Glossary+and+Overview"
last_modified: "2026-05-12"
---

Document Title: Glossary and Assumptions  
Description: Aimed to outline commonly used terminology on Cart  
Version: v1.0  
Owner: Vikram Visweswara  
Last Updated: 23/04/2026

## 🔸 GL-001 — Cart

| Field | Details |
| --- | --- |
| **Definition** | The checkout page on the Kmart website and app |
| **Synonyms** | Checkout, Bag |
| **Used In** | Web, App |
| **Notes** | Exists for both guest and signed-in users |

---

### 🔸 GL-002 — SKUs

| Field | Details |
| --- | --- |
| **Definition** | Stock Keeping Unit - Unique identifier to track inventory. |
| **Synonyms** | Keycode, line item, items |
| **Used In** | Cart, PDP, PLP/SLP, Search, Web, App, Marketplace |
| **Notes** | Multiple SKUs can exist in a single cart. A single cart can have 1P and 3P SKUs in it. |

---

### 🔸 GL-003 — Guest Cart

| Field | Details |
| --- | --- |
| **Definition** | A cart associated with a non-authenticated user session |
| **Synonyms** | Anonymous cart |
| **Used In** | Web, App |
| **Notes** | Can merge into signed-in cart |

---

### 🔸 GL-004 — Side Cart

| Field | Details |
| --- | --- |
| **Definition** | A sliding panel on pre-cart pages that lists items added to cart |
| **Synonyms** | Slide cart |
| **Used In** | Web |
| **Notes** | List only product details, price and quantity. Does not do availability checks or shipping calculation. |

---

### 🔸 GL-005 — Fulfilment Method

| Field | Details |
| --- | --- |
| **Definition** | Method by which items are delivered or collected |
| **Synonyms** | Delivery options, collection methods |
| **Used In** | PDP, Cart, Web and app |
| **Notes** | Home delivery (HD), click & collect (C&C), click and collect anywhere (CNCA), Express delivery |

---

### 🔸 GL-006 — Shipping Rule

| Field | Details |
| --- | --- |
| **Definition** | Rule determining shipping eligibility or cost |
| **Synonyms** | Delivery rule |
| **Used In** | Cart, web and app |
| **Notes** | Depends on postcode, size and dimensions of item such as Big and Bulky, 1P or 3P item |

---

### GL-007 — OnePass

| Field | Details |
| --- | --- |
| **Definition** | Wesfarmer’s loyalty program |
| **Synonyms** | - |
| **Used In** | PDP, PLP, My Account, Cart, web and app |
| **Notes** | OnePass members get special benefits when purchasing on the Kmart website. |

---

### GL-007 — Flybuys

| Field | Details |
| --- | --- |
| **Definition** | Wesfarmer' partner loyalty program |
| **Synonyms** | - |
| **Used In** | Cart, PDP, PLP, web and app |
| **Notes** | Customers can get Flybuys points upon providing their Flybuys number at checkout when purchasing items on the Kmart web and app. |

---

### GL-007 — B2B

| Field | Details |
| --- | --- |
| **Definition** | An integration tool from IBM that translates order information from Digital and sends downstream to SAP |
| **Synonyms** | - |
| **Used In** | Enterprise technology |
| **Notes** | Converts order information into “idoc” that is consumable by SAP. Translates received sales, recognised sales, cancelled sales and returned sales. |

---

### GL-007 — SAP

| Field | Details |
| --- | --- |
| **Definition** | ERP tool |
| **Synonyms** | - |
| **Used In** | Corporate systems |
| **Notes** | Records received sales, recognised sales, cancelled sales and returned sales. |

---

### GL-008 — SoH

| Field | Details |
| --- | --- |
| **Definition** | Stock on hand - refers to available stock on hand |
| **Synonyms** | - |
| **Used In** | PDP, PLP/SLP, Cart, Recommenders, Google shopping feeds, Feedonomics, web, app |
| **Notes** |  |

---

### GL-009 - T-shirt sizing

| **Size** | **Sprints** | **Story points** |
| --- | --- | --- |
| X-Small (XS) | <=1 sprint | 18 |
| Small (S) | 1 - 2 sprints | 36 |
| Medium (M) | 3 - 4 sprints | 72 |
| Large (L) | 5 - 6 sprints | 108 |
| X-Large (XL) | 6+ sprints | >120 |

## 🔹 2. Canonical Naming

| Preferred Term | Avoid Using | Reason |
| --- | --- | --- |
| Cart | Bag, Checkout | Maintain consistency across systems |
| Fulfilment Method | Delivery Type, Shipment Type | Aligns business terminology |
| OnePass | Loyalty program | There are 2 loyalty programs |
| Flybuys | Loyalty program | There are 2 loyalty programs |
| Shipping rule | Shipping calc, delivery rules | Maintain consistency across systems |
