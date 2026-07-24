---
title: "Cart systems"
confluence_page_id: "5691834501"
source_url: "https://kmartau.atlassian.net/wiki/spaces/~6302fcc5a29ccf493838087e/pages/5691834501/Cart+assets"
last_modified: "2026-05-13"
---

Document Title: Cart assets  
Description: Aimed to highlight key assets under use by Cart  
Version: v1.0  
Owner: Vikram Visweswara  
Last Updated: 23/04/2026

### 🔸 AST-001 — Paydock

| Field | Details |
| --- | --- |
| **Definition** | SaaS payments platform |
| **Notes** | Payment aggregator that records all types of transactions. All payment methods are integrated to Paydock |
| **Complexity** | High |
|  |  |

---

### 🔸 AST-002 — CommerceTools Service

| Field | Details |
| --- | --- |
| **Definition** | Abstraction layer between Cart UI and Commerce Tools |
| **Notes** | Used by Cart, Wishlist, Order transfer, etc. |
| **Complexity** | Medium |

---

### 🔸AST-003 — Shipping rate calculator

| Field | Details |
| --- | --- |
| **Definition** | Has logic that applies business rules to provide accurate shipping fee based on items in the cart. |
| **Notes** | Considers 1P, 3P, Big and Bulky, Standard and flat rate products. |
| **Complexity** | High |

---

### 🔸AST-004 — Order Transfer

| Field | Details |
| --- | --- |
| **Definition** | Lamdba that transfers order details to downstream systems |
| **Notes** | Transfers order data to DOM for all NZ orders |
| **Complexity** | Medium |

---

### 🔸AST-005 — OMFP Order Transfer

| Field | Details |
| --- | --- |
| **Definition** | Lamdba that transfers order details to downstream systems |
| **Notes** | Transfers order data to OMFP middleware for all AU orders |
| **Complexity** | Medium |

---

### 🔸AST-006 — Cart availability API

| Field | Details |
| --- | --- |
| **Definition** | API that provides available stock on hand for all 1P and 3P items in Cart. |
| **Notes** | Retrieves stock on hand information from OMFP middleware for 1P. Retrieves stock on hand information from Mirakl for 3P items in Cart |
| **Complexity** | Medium |

---

### 🔸AST-007 — Vii

| Field | Details |
| --- | --- |
| **Definition** | Gift card provider |
| **Notes** | 3rd party vendor that provides the gift cards for redemption at checkout |
| **Complexity** | NA |

---

### 🔸AST-008 — Refund service

| Field | Details |
| --- | --- |
| **Definition** | Calculate amount to be refunded to customers and send to Paydock |
| **Notes** | Actual refund is triggered on Paydock. |
| **Complexity** | Medium |

---

### 🔸AST-009 — Gift card refund registry

| Field | Details |
| --- | --- |
| **Definition** | Table where gift card refunds are recorded |
| **Notes** | Gift cards payments are to be refunded as gift cards only. This table is updated with customer information and gift card amount to be refunded which the CSC uses to order gift cards as refunds to send to customers. |
| **Complexity** | Low |

---

### 🔸AST-010 — Experian/QAS

| Field | Details |
| --- | --- |
| **Definition** | SaaS for address validation |
| **Notes** | Used to validate the address provided in the delivery address section in Cart |
| **Complexity** | Low |

---

### 🔸AST-011 — Order Master

| Field | Details |
| --- | --- |
| **Definition** | Manage and orchestrate order information to upstream and downstream systems |
| **Notes** | Passes data to multiple streams - Finance reconciliation, Post purchase comms, Order tracking, SMS and Sophia |
| **Complexity** | High |

---

### 🔸AST-012 — SendGrid

| Field | Details |
| --- | --- |
| **Definition** | Comms tool |
| **Notes** | All post purchase comms as sent to the customer as email using Sendgrid. All email templates are maintained here. |
| **Complexity** | Low |

---

### AST-013 — Fintech reporting pipeline

| Field | Details |
| --- | --- |
| **Definition** | Bunch of lambdas that translate sales, cancellations and returns data for financial reporting purposes |
| **Notes** |  |
| **Complexity** | High |

---

### AST-013 — Cart UI

| Field | Details |
| --- | --- |
| **Definition** | Front end experience of Kmart’s checkout page (web only) |
| **Notes** |  |
| **Complexity** | Low |
