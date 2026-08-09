# OpsCore Data Model

## 1. Overview

This document defines the initial data model for OpsCore.

The goal is to identify the core business entities, their responsibilities, and their relationships before implementing database tables and JPA entities.

## 2. Core Entities

### User

Represents a person who uses the system.

Example fields:

- id
- firstName
- lastName
- email
- role
- createdAt
- updatedAt

### Product

Represents an item sold or managed by the retail business.

Example fields:

- id
- name
- sku
- description
- category
- unitPrice
- active
- createdAt
- updatedAt

### Vendor

Represents a supplier that provides products.

Example fields:

- id
- name
- contactName
- email
- phone
- address
- active
- createdAt
- updatedAt

### Inventory

Represents the current stock state of a product.

Example fields:

- id
- productId
- quantityOnHand
- reorderLevel
- updatedAt

### PurchaseOrder

Represents a purchase order sent to a vendor.

Example fields:

- id
- vendorId
- status
- orderDate
- expectedDeliveryDate
- createdByUserId
- createdAt
- updatedAt

### PurchaseOrderItem

Represents a product line inside a purchase order.

Example fields:

- id
- purchaseOrderId
- productId
- quantity
- unitCost

### InventoryMovement

Represents a historical record of inventory changes.

Example fields:

- id
- productId
- movementType
- quantityChange
- reason
- createdByUserId
- createdAt

### LicenseRecord

Represents a license, permit, or compliance-related document.

Example fields:

- id
- name
- licenseNumber
- issuingAuthority
- issueDate
- expirationDate
- status
- createdAt
- updatedAt

## 3. Entity Relationships

Vendor 1 → many PurchaseOrders

PurchaseOrder 1 → many PurchaseOrderItems

Product 1 → many PurchaseOrderItems

Product 1 → 0 or 1 Inventory

Product 1 → many InventoryMovements

User 1 → many PurchaseOrders

User 1 → many InventoryMovements

## 4. Notes

The first version will use a relational database model with PostgreSQL.

JPA and Hibernate will later map Java entity classes to database tables.

Foreign keys will be used to represent relationships between entities.

## 5. Future Considerations

Future versions may include:

- Business locations or stores
- Document uploads
- Audit history
- Notifications
- Multi-store inventory
- Advanced reporting
