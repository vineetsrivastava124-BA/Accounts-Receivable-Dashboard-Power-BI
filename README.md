# AR Dashboard (Accounts Receivable)

## Overview
This Power BI report (`AR_Dashboard_New.pbix`) provides visibility into a company's accounts receivable performance — tracking invoicing, collections, and outstanding balances by customer and region. It is designed to help finance and credit teams monitor cash flow health, identify overdue accounts, and analyze payment behavior trends.

## Report Pages

### 1. Welcome
A landing page introducing the dashboard, with a title and supporting visual elements.

### 2. AR DB (Main Dashboard)
The primary analytics page, containing:
- **7 KPI cards** summarizing top-line receivables metrics
- **Bar chart** – likely a breakdown by customer, region, or status
- **Donut chart** – proportional view (e.g., invoice status mix)
- **2 Clustered column charts** – comparative metrics across categories
- **Area chart** – trend over time (e.g., rolling sales or outstanding balance)
- **Table** – detailed invoice/customer-level records
- **Slicer** – interactive filter (e.g., by region, customer, or date)

### 3. DT Analysis (Decomposition Tree)
An interactive drill-down page for root-cause and ad hoc analysis, containing:
- **Decomposition tree** – explore what's driving a selected metric across dimensions
- **KPI cards** – supporting context metrics
- **Bar chart** and **pie chart** – supplementary breakdowns
- **Action buttons (x2)** – navigation or filter-reset controls

## Data Model

**Source tables:**
- `Sheet1` — primary data table
- `LocalDateTable_*` — auto-generated Power BI date table

**Key fields & measures:**

| Category | Fields |
|---|---|
| Collections / Aging | DSO (Days Sales Outstanding), Avg Days to Pay, Late Payments, Overdue Amount, Total Outstanding Amount |
| Invoicing | Total Invoices, Total Invoice, InvoiceAmount, Avg Invoice Value, Max Invoice, DueDate |
| Payments | PaidAmount / Paid Amount, PaymentDate, PaymentTerms, Status, Status Color |
| Customer & Region | Customer, Total Customer, Region |
| Trends | Rolling 3M Sales, Month, Date |

> **Note:** The `Status Color` field suggests conditional formatting is used (e.g., red/amber/green indicators for overdue vs. on-time invoices).

## Suggested Use Cases
- Monitor overall receivables health via DSO and overdue amounts
- Identify high-risk customers or regions with late payments
- Track collections trends month-over-month
- Drill into root causes of outstanding balances using the decomposition tree

## Requirements
- Power BI Desktop (to open and edit `.pbix`)
- Data refresh requires access to the original `Sheet1` data source

## File Info
- **File name:** AR_Dashboard_New.pbix
- **Pages:** 3 (Welcome, AR DB, DT Analysis)
- **Report canvas size:** 1280 x 720 (16:9)
