# Fuuz WMS Accelerator

A packaged warehouse management application built on the [FUUZ](https://fuuz.app) platform — receiving, inventory, cycle counting, picking, packing, and shipping in one importable Fuuz package.

## The Scenario

A warehouse operation needs to run receiving through shipping against a single, status-driven data model — without stitching together point solutions or writing custom flows for every process. The WMS Accelerator packages the full order-to-cash warehouse cycle: receive inbound goods, manage tracked inventory, pick and pack against configurable methods, and ship with generated carrier documentation.

## One Application, One Platform

**Package:** `WMS Accelerator - Mfg@0.0.7 1.fuuz`

| Component | Count |
|---|---|
| Data Models | 52 |
| Screens | 43 |
| Data Flows | 49 |
| Document Designs | 6 |
| Seeded Reference Data Sets | 17 |

Built against **platform version 2026.7.0**.

## 52 Data Models

| Category | Models | What They Track |
|---|---|---|
| **Inventory & Product Management** | Adjustment, Area, HandlingUnit, HandlingUnitType, Inventory, InventoryPickStep, InventoryStatus, InventoryTrace, LabelDesign, Lot, Process, Product, ProductCategory, TransactionType | The tracked unit of inventory — product, lot, quantity, and status — with a full audit trail of every move, merge, and split |
| **Order & Load Management** | BusinessPartner, BusinessPartnerAddress, Load, Order, OrderLine, OrderLineRelease, OrderLineReleaseStatus, OrderStatus, OrderType, Pick, Shipment, ShipmentLine, ShipmentLineOrderLineRelease, ShipmentType | Purchase/Sale Orders, their Order Line Releases, and the Loads and Shipments they generate |
| **Picking** | NonConformance, PickStatus, PickStep, PickStepStatus, Unpick, UnpickReason | Picks broken into Pick Steps against specific storage locations, with exception/unpick handling |
| **Receiving** | Receipt, ReceiptException, ReceiptExceptionReason, ReceiptLine, ReceiptLineOrderLineRelease, ReceiptStatus | Inbound BOL/ASN receipt headers and lines, with exception tracking |
| **Cycle Counting** | Count, CountLine, CountLineInventory, CountParameters, CountStatus | Configurable cycle counts and the inventory lines they reconcile |
| **Site Management** | ProductPreferredStorageUnit, StorageUnit, StorageUnitStatus, StorageZone | The Area / Zone / Storage Unit hierarchy that anchors every transaction |
| **Shipping & Carrier Management** | StandardCarrierAlphaCode | Seeded SCAC reference data for carrier assignment |
| **Logistics** | LoadStatus, OrderLineReleaseType | Load lifecycle and release-type classification |

## 43 Screens

- **8 Inventory & Product Screens** — Adjustment, Inventory, Merge/Move/Split Inventory, Process, Product Category, Product
- **7 Order & Business Partner Screens** — Allocate Inventory to Lines, Business Partner Address/Detail Forms, Business Partners Table, Order Line Create Widget, Select Order Releases, Shipping Mobile
- **6 Receiving Screens** — Create Exception Modal, Create Receipt Line Widget, New Receipt Widget, Receipt Line Confirmation, Receiving, Receiving Details Modal
- **5 Cycle Counting Screens** — Count Details, Count Location Selector, Count Selector, Count Table, Execute Cycle Count
- **4 Picking Screens** — Execute Pick, Pick Details, Pick Management, Unpick Modal
- **3 Inventory Widget Screens** — Basic Inventory Update Widget, Create Inventory Widget, Product Details Form
- **3 Order Processing Screens** — Create Load Form, Load Management, Orders
- **2 Shipping Screens** — SCAC, Ship Management
- **1 Packing Screen**, **1 Site Management Screen**, **1 Configuration Screen**, **1 WMS Dashboard**
- **1 Testing Screen** — placeholder/test screen not intended for production use

## 49 Data Flows

- **Shipping & Carrier Management** — Add Edit SCAC Web Flow, Create Handling Unit Web Flow, Create Load and Shipments, Get BoL Number, Get Commercial Invoice Number, Print Shipping Documents Web Flow, Ship Management Web Flow, Update Load Status
- **Cycle Counting** — Cancel/Complete/Recount Count, Count Count Line Inventory Webflow, Create Count Line Inventory, Cycle Count Web Flow, Exclude Count Line Inventory, Execute Cycle Count Scan, Start Count and Create Count Lines
- **Receiving** — Confirm Line, Confirm Line Web, Confirm Receipt Line, Create Receipt Line, Update Receipt Status
- **Picking** — Create Pick Step, Create Pick Web Flow, Execute Pick Web Flow, NonConformancePublishMessage, Pick Details Web Flow
- **Inventory & Product Management** — Create Inventory, Merge/Move/Split Inventory (+ Web variants)
- **Packing** — Packing Web Flow, Pack Inventory, Print Box Content Label, Unpack Inventory
- **Order & Load Management** — Add New Shipment Line, Update Order Status, Update Release Status, Orders Web Flow, Change Shipment Line Quantity
- **Quality (Material Review Board)** — MRB Adjust Inventory, MRB Complete Return
- **Configuration** — Configuration Web Flow, Web Flow Log
- **Dashboard** — WMS Dashboard Search v3

## Document Designs

Bill Of Lading, Box Content Label, Commercial Invoice, Packing List, Pick Sheet, Shipping Label.

## Seeded Reference Data

This package ships seeded values for `InventoryStatus`, `LoadStatus`, `HandlingUnitType`, `PickStepStatus`, `PickStatus`, `TransactionType`, `OrderLineReleaseStatus`, `OrderLineReleaseType`, `OrderStatus`, `OrderType`, `StandardCarrierAlphaCode`, `ShipmentType`, and `UnpickReason`, in addition to the standard `ApplicationConfiguration` set.

## Getting Started

### Import into FUUZ

1. Request a [free trial of FUUZ](https://forms.zohopublic.com/mfgxonlinesaas/form/TrialNotificationForm/formperma/syUyoccvUH7Ef5DaReDpfM48vuKiZtaGfYN18JPPu9k)
2. Navigate to **Fuuz Packages**
3. Upload `WMS Accelerator - Mfg@0.0.7 1.fuuz`
4. Review the import preview and confirm
5. Configure your site structure (Area → Zone → Storage Unit) and Business Partners, load Products, and set the tenant-wide Move/Pack/Pick behavior via Application Configuration

### Explore the Package

Each `.fuuz` file is a gzipped tarball containing three JSON files:

```bash
mkdir extracted && cd extracted
tar -xzf "../WMS Accelerator - Mfg@0.0.7 1.fuuz"

ls -lh
# manifest.json      - Package metadata (name, version, dependencies)
# definition.json    - Module groups, modules, and enum seed data
# package-data.json  - Data models, screens, flows, and seed data
```

## Requirements

- A Fuuz Industrial Intelligence Platform tenant, platform version 2026.7.0 or later
- The Fuuz Integration Orchestrator, if you plan to connect to an external ERP/host system

## Resources

| Resource | Link | Description |
|---|---|---|
| **Free Trial** | [fuuz.app](https://forms.zohopublic.com/mfgxonlinesaas/form/TrialNotificationForm/formperma/syUyoccvUH7Ef5DaReDpfM48vuKiZtaGfYN18JPPu9k) | Request your free trial of FUUZ |
| **Get Started** | [getstarted.fuuz.com](https://getstarted.fuuz.com) | Introductory videos and walkthroughs |
| **FUUZ Academy** | [academy.fuuz.com](https://academy.fuuz.com) | Online LMS with structured courses and certifications |
| **Support & Community** | [support.fuuz.com](https://support.fuuz.com) | Knowledge base, documentation, and customer community |

## License

© Fuuz. All rights reserved. This package is proprietary software provided for use with the Fuuz Industrial Intelligence Platform. Redistribution or use outside of a licensed Fuuz tenant is not permitted without express written permission.

## Service levels

No service level agreement applies to anything published here. It becomes a supported
deliverable only once it has been implemented by a Fuuz services professional or an
approved Fuuz partner.
