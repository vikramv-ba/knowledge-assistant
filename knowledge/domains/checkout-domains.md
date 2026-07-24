---
title: "Domains in Cart"
confluence_page_id: "5691769035"
source_url: "https://kmartau.atlassian.net/wiki/spaces/~6302fcc5a29ccf493838087e/pages/5691769035/Domains+in+Cart"
last_modified: "2026-04-27"
---

Document Title: Domain in Cart  
Description: Aimed at highlighting the common scenarios under Cart.  
Version: v1.0  
Owner: Vikram Visweswara  
Last Updated: 24/04/2026

### 🔸SC-001 — Side cart

| Field | Details |
| --- | --- |
| **Scenario** | Side cart |
| **Notes** | Products added to Cart show up on the side cart. This side cart only displays product information, price and quantity. It does not calculate or display shipping fees, does not do availability checks. It is intended to provide quick view of the items in Cart |

---

### 🔸 SC-002 — Shipping fees for 1P

| Field | Details |
| --- | --- |
| **Scenario** | Different types of shipping fees |
| **Notes** | Products added to Cart show up on the side cart. This side cart only displays product information, price and quantity. It does not calculate or display shipping fees, does not do availability checks. It is intended to provide quick view of the items in Cart |

---

### 🔸 SC-003 — Shipping fees for 3P

| Field | Details |
| --- | --- |
| **Scenario** | Different types of shipping fees |
| **Notes** | Shipping fees for 3P items are decided by what is configured on Mirakl by the seller. Cart groups them a certain way on the checkout page. |

---

### 🔸 SC-004 — Pay using credit/debit card

| Field | Details |
| --- | --- |
| **Scenario** | Credit or debit card payment |
| **Notes** | Customers can choose to pay using a credit/debit card by providing their card number. It undergoes validation and payment is accepted and recorded on Paydock or credit/debit card payment. |

---

### 🔸SC-005 — Pay using gift card

| Field | Details |
| --- | --- |
| **Scenario** | Gift card payment |
| **Notes** | Customers can choose to pay using a gift card by providing their gift card number. The gift card number is validated. If it passes validation, the gift card amount is reduced from the gift card balance and payment is accepted and recorded on Paydock as a Vii payment. Currently, only Kmart and Coles Group-Myer gift cards are accepted on the Kmart website. |

---

### 🔸SC-006 — Pay using Afterpay or Zippay

| Field | Details |
| --- | --- |
| **Scenario** | Pay using Afterpay or Zippay |
| **Notes** | Customers can choose to pay using BNPL options - Afterpay or Zippay. Their widgets are embedded on the Cart UI. Customers are redirected to provide their Afterpay or Zippay credentials and once approved, payment is accepted and recorded as an Afterpay payment or Zippay payment on Paydock. |

---

### 🔸SC-007 — Pay using Paypal

| Field | Details |
| --- | --- |
| **Scenario** | Pay using Paypal |
| **Notes** | Customers can choose to pay using their Paypal account. Paypal’s widget is embedded on the Cart UI. Customers are redirected to provide their Paypal credentials and once approved, payment is accepted and recorded as an Paypal payment on Paydock. |

---

### 🔸SC-008 — Team member discounts

| Field | Details |
| --- | --- |
| **Scenario** | Team member discounts |
| **Notes** | All Kmart team members can avail a 10% discount on their cart by providing their valid Team member card number. If valid, a discount is applied automatically on the Cart. A compliance department does a regular audit to flag misuse of this benefit. This discount is available only on Kmart products on the Kmart website. No discount is provided to Target on Kmart products and Marketplace products. |

---

### 🔸SC-009 — Finance Reconciliation

| Field | Details |
| --- | --- |
| **Scenario** | Flow of order information for financial reporting |
| **Notes** | The finance reconciliation pipeline covers 4 different scenarios:<br><br>1. Sales received - Sales recorded at checkout, but not shipped yet.<br>2. Sales recognised - Sales recorded at checkout that are shipped.<br>3. Sales cancelled - Order cancellations prior to shipment<br>4. Sales returned - Order cancelled post shipment.<br><br>The treatment is different for 1P i.e. Kmart items and different for 3P i.e. Marketplace items including Target products on the Kmart website. The information pipeline involves sending data from Order Master owned by Digital to B2B to finally SAP. |

---

### 🔸SC-010 — Refunds for non-gift card payments

| Field | Details |
| --- | --- |
| **Scenario** | Refunds issued to a customer when they pay using a non-gift card payment method |
| **Notes** | If an order is cancelled prior to shipment, the whole order amount is to be refunded to the customer. The trigger is from MANH (for AU orders) or DOM (for NZ orders). The refunds are processed through paydock. The refund transaction also flow through to SAP through the finance reconciliation pipeline. The treatment for 3P products are different as the refund amounts are decided by the seller and Mirakl informs MANH what the refund amount is. Refunds are always made to the original payment method. |

---

### 🔸SC-011 — Refunds for gift card payments

| Field | Details |
| --- | --- |
| **Scenario** | Refunds issued to a customer when they pay using a gift card. |
| **Notes** | If an order is cancelled prior to shipment, the whole order amount is to be refunded to the customer. The trigger is from MANH (for AU orders) or DOM (for NZ orders). The refunds are processed through a refund service which update a table called the “Giftcard refund registry table”. The Customer Service Care team refer to an extract of this table to place gift card orders on Vii’s website manually which automatically email the gift cards to customers. The refund transactions also flow through to SAP through the finance reconciliation pipeline. |

---

### 🔸SC-012 — Signed is customers

| Field | Details |
| --- | --- |
| **Scenario** | Experience for signed in customers |
| **Notes** | If customers are signed in and they have saved their address on their account, the delivery address is pre-filled. Their cart is also preserved if they have added items to their cart but not completed the purchase. |

---

### 🔸SC-013 — Fulfilment methods

| Field | Details |
| --- | --- |
| **Scenario** | Customers can choose to get their items home delivered or they may choose to click and collect. |
| **Notes** |  |

---

### 🔸SC-014 — Items unavailable

| Field | Details |
| --- | --- |
| **Scenario** | Not all items are available. |
| **Notes** | When the customer has added items to their cart, but not all items are available, they are shown a message that items are unavailable. They must either remove the items from the cart or adjust the quantity until they become available as there is a stock on hand check for all the items in cart prior to completing a payment or when there is a quantity adjustment or when the page is refreshed. |

---

### 🔸SC-015 — Marketplace items

| Field | Details |
| --- | --- |
| **Scenario** | Marketplace experience |
| **Notes** | If there are Marketplace items in the cart, they are listed in a separate component of the Cart page with their own delivery fees. |

---

### 🔸SC-016 — Post purchase experience

| Field | Details |
| --- | --- |
| **Scenario** | Post purchase comms |
| **Notes** | When an order is placed, an order confirmation email is sent. Tax invoices are also sent separately. All sellers will send their invoices independently. So if the customer has brought items from 3 sellers and Kmart too, then the customer will receive 4 tax invoices. |

---

### 🔸SC-017 — Guest experience

| Field | Details |
| --- | --- |
| **Scenario** | Experience for guest customers |
| **Notes** | If customers are not signed in and the delivery address will have to filled manually Their cart will only be preserved for as long as the session is active. |

---

### 🔸SC-018 — OnePass member experience

| Field | Details |
| --- | --- |
| **Scenario** | Customer is a Onepass members |
| **Notes** | All Onepass members get benefits such as free shipping and 365 day returns on eligible items (not all items), 5x Flybuys points for Click and Collect orders. 3P sellers who are part of the program will also offer the same benefits. |

---

### 🔸SC-019 — Flybuys

| Field | Details |
| --- | --- |
| **Scenario** | Flybuys points awarding |
| **Notes** | All customers who provide their Flybuys number get Flybuys points. 1 point for $1 for home delivery and C&C orders. 5X bonus Flybuys points for Onepass members for C&C. |
