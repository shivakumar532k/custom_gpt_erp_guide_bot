# Enterprise Resource Planning (ERP): Procure-to-Pay (P2P) Process Overview

## 1. Executive Summary

The **Procure-to-Pay (P2P)** process—also referred to as Purchase-to-Pay—is an end-to-end business cycle that integrates procurement activities with accounts payable (AP) processes within an Enterprise Resource Planning (ERP) system. 

The primary goal of the P2P cycle is to acquire goods and services efficiently, at the best value, and ensure proper compliance, internal control, and timely vendor settlement.

```
       [ Procurement Phase ]                      [ Accounts Payable Phase ]
   ┌───────────────────────────┐                ┌───────────────────────────┐
   │ 1. Purchase Requisition   │                │ 5. Goods/Service Receipt  │
   │            ▼              │                │            ▼              │
   │ 2. Vendor Selection (RFQ) │ ──────────────►│ 6. Invoice Processing     │
   │            ▼              │                │            ▼              │
   │ 3. Purchase Order (PO)    │                │ 7. 3-Way Matching         │
   │            ▼              │                │            ▼              │
   │ 4. Order Confirmation     │                │ 8. Payment Settlement     │
   └───────────────────────────┘                └───────────────────────────┘
```

---

## 2. Step-by-Step P2P Process Flow

### Step 1: Purchase Requisition (PR)
* **Description:** An internal request initiated by a department or employee needing goods, materials, or services.
* **ERP System Action:** 
  * Requisitioner submits PR via employee self-service portal.
  * ERP routes the PR through automated approval workflows based on organization hierarchy, cost center, and budget threshold.
* **Key Inputs:** Item details, quantity, estimated cost, required date, account assignment/cost center.
* **Key Output:** Approved Purchase Requisition.

---

### Step 2: Vendor Selection & Request for Quotation (RFQ) *(Optional/Conditional)*
* **Description:** For non-catalog items or high-value purchases, the procurement team requests quotes from multiple approved vendors.
* **ERP System Action:**
  * System converts approved PR into an RFQ.
  * Quotes are uploaded or submitted directly by vendors via a Supplier Portal.
  * ERP facilitates commercial evaluation and side-by-side bid comparison.
* **Key Inputs:** Supplier master data, RFQ specifications, vendor bids.
* **Key Output:** Selected Vendor and agreed commercial terms.

---

### Step 3: Purchase Order (PO) Creation & Dispatch
* **Description:** A legally binding contract issued to the vendor specifying items, quantities, pricing, payment terms, and delivery schedules.
* **ERP System Action:**
  * System automatically auto-populates data from approved PR/RFQ into a formal PO.
  * Triggers final PO approval workflows.
  * Transmits PO electronically to the vendor (via EDI, email, or Vendor Portal).
* **Key Inputs:** Approved PR/RFQ details, Vendor Master record, Tax & Payment terms.
* **Key Output:** Legally binding Purchase Order (PO Number generated).

---

### Step 4: Order Confirmation & Shipping Notice
* **Description:** The vendor confirms acceptance of the order and sends an Advanced Shipping Notice (ASN) upon dispatching goods.
* **ERP System Action:**
  * System logs order acknowledgment and updates status.
  * Captures ASN data (tracking numbers, delivery estimates, batch numbers).
* **Key Inputs:** Vendor confirmation, ASN.
* **Key Output:** Confirmed PO status with scheduled delivery date.

---

### Step 5: Goods Receipt (GR) / Service Entry Sheet (SES)
* **Description:** Physical receipt and verification of delivered materials at the warehouse or sign-off on services performed.
* **ERP System Action:**
  * Warehouse team inputs physical count and quality check details against the open PO.
  * ERP updates inventory levels and creates a financial accounting posting (Debit: Inventory/Expense, Credit: Goods Receipt/Invoice Receipt Clearing Account).
* **Key Inputs:** Physical delivery, Packing slip, Delivery Note, PO Reference.
* **Key Output:** Goods Receipt Document / Service Entry Sheet (GRN / SES).

---

### Step 6: Invoice Receipt & Processing
* **Description:** Vendor sends an invoice requesting payment for the fulfilled order.
* **ERP System Action:**
  * Invoices enter via OCR scanning, e-Invoicing networks, or vendor portal entry.
  * Invoice data is logged and linked directly to the corresponding PO and GRN.
* **Key Inputs:** Vendor Invoice (Tax Invoice), PO Number, GRN reference.
* **Key Output:** System-entered Vendor Invoice Document.

---

### Step 7: 3-Way Matching & Approval
* **Description:** Internal verification to ensure consistency across the three primary P2P documents before payment processing.
* **The 3-Way Match Check:**
  1. **Purchase Order (PO):** What was ordered and agreed price.
  2. **Goods Receipt (GRN):** What was actually received.
  3. **Vendor Invoice:** What the vendor is billing.
* **ERP System Action:**
  * Automated tolerance checks for line-item pricing, quantity, and tax variations.
  * **Pass:** Invoice is approved and scheduled for payment.
  * **Fail:** Invoice is placed on hold; workflow alerts AP team/buyer for exception resolution.

---

### Step 8: Payment Settlement & Accounting Accounting
* **Description:** Disbursing payment to the vendor according to agreed terms (e.g., Net 30, Net 60) and clearing open accounting entries.
* **ERP System Action:**
  * Payment proposal run groups due invoices by payment methods (ACH, Wire, Check, Virtual Card).
  * Generates bank execution files (e.g., MT103, ISO 20022 XML) and posts financial accounting entries (Debit: AP Clearing, Credit: Cash/Bank Account).
  * System emails remittance advice to the vendor automatically.
* **Key Inputs:** Approved Invoice, Bank account details, Payment Run schedule.
* **Key Output:** Payment Remittance Advice, Cleared Ledger Accounts.

---

## 3. Core Accounting Entries in P2P Cycle

| Event | General Ledger Posting (Debit) | General Ledger Posting (Credit) |
| :--- | :--- | :--- |
| **Goods Receipt (GRN)** | Inventory Account / Expense Account | Goods Receipt / Invoice Receipt (GR/IR) Clearing |
| **Invoice Receipt (IR)** | Goods Receipt / Invoice Receipt (GR/IR) Clearing | Accounts Payable (Vendor Account) |
| **Payment Execution** | Accounts Payable (Vendor Account) | Cash / Bank Account |

---

## 4. Key Performance Indicators (KPIs) for P2P Optimization

1. **Procure-to-Pay Cycle Time:** Total time taken from PR creation to final vendor payment.
2. **First-Time Match Rate:** Percentage of vendor invoices matched on the first attempt without manual intervention.
3. **Cost per Invoice Processed:** Total operational cost divided by the number of invoices processed.
4. **Early Payment Discount Capture Rate:** Percentage of early payment discounts captured vs. total available discounts.
5. **PO Compliance Rate:** Percentage of total spend made through formal pre-approved POs vs. unapproved non-PO spend.