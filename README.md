# ERP process design for a fashion retail store

Course project for IS336 (Enterprise Resource Planning), UIT Faculty of Information
Systems. We modelled how a small fashion retailer would run on Odoo: the processes, the
master data, and the debt handling that usually gets skipped.

To be clear about what this is: **process design and data preparation, not an Odoo
module**. Nothing here is custom code. The deliverable is the process map plus the data
files you would import to make a real Odoo instance match it.

## Processes covered

The BPMN diagram (`diagram (1) (1).bpmn`) ties these together across suppliers,
customers, accounting, warehouse and HR:

- **Purchasing** — requisition through to supplier invoice
- **Inbound** — receiving and putting away
- **Sales** — order, confirmation, invoicing
- **Outbound** — picking and shipping
- **Stock check** — periodic count and adjustment
- **Production** — for the store's own label items
- **Supplier debt** — payment terms, reconciliation at period close
- **Customer debt** — overdue handling, reminder escalation by email then phone
- **Customer care** — post-purchase follow-up

Individual flows are also in `.drawio` format if you want to edit them.

## Data

| File | What |
|---|---|
| `Category.xlsx` | product category master data |
| `Product.xlsx` | product master data, mapped to Odoo fields |
| `Orders_70_for_Odoo.xlsx` | 70 sample orders formatted for Odoo import |
| `DEADLINE ERP.xlsx` | working schedule for the team |
| `ERP REPORT.docx` | full write-up (Vietnamese), 60+ pages |

Between ordering and simulation we found the usual problem: Odoo's import templates
assume fields that a fashion store does not naturally track, so a chunk of the work was
deciding what to leave blank versus what to force the store to record.

## What is weak here

- **It was never fully implemented.** We prepared the master data and the import files,
  we did not run a full month of transactions through Odoo and reconcile it. So the
  process map is a design, not a verified operating procedure.
- **Accounting is shallow.** The debt flows cover reminders and period totals. Real
  accounting needs journal entries, tax treatment and period close rules, and we stopped
  short of that.
- **One store.** No multi-branch, no inter-warehouse transfer, which is where ERP starts
  paying for itself.
- **`ERP.xml` is an empty draw.io library file.** It has no content and can be deleted.

## Team

| Name | Student ID |
|---|---|
| Nguyễn Hồng Nhật Long | 22520816 |
| Lê Trần Quốc Khánh | 22520638 |
| Nguyễn Thị Hải Hà | 22520372 |
| Nguyễn Thị Thanh Hiếu | 22520443 |

Supervisors: ThS. Huỳnh Đức Huy, KS. Lê Võ Đình Kha.
