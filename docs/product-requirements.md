# OpsCore Product Requirements

## 1. Overview

OpsCore is a retail operations and compliance management platform for small and medium-sized retail businesses.

## 2. Problem Statement

Small retail businesses often manage products, inventory, vendors, purchase orders, licenses, and compliance records across spreadsheets, paper documents, emails, and disconnected tools.

This creates problems such as inaccurate inventory, missed license renewals, poor purchase tracking, and limited visibility into daily operations.

## 3. Target Users

- Business Owner
- Store Manager
- Inventory Staff
- Compliance/Admin Staff

## 4. Goals

- Centralize retail operations data
- Track products, vendors, inventory, and purchase orders
- Record inventory movements
- Manage licenses and compliance records
- Provide a foundation for a future desktop application

## 5. MVP Scope

The MVP includes:

- Product management
- Vendor management
- Inventory tracking
- Purchase order workflow
- Inventory movement history
- License and compliance record tracking
- Basic user model

## 6. Out of Scope for MVP

The MVP does not include:

- Mobile app
- Offline mode
- Microservices
- Kubernetes
- Kafka
- Redis
- Payment processing
- Accounting integration
- Automatic desktop app updates

## 7. User Roles

- ADMIN
- MANAGER
- STAFF

## 8. Core Business Workflows

### Purchase Workflow

Vendor → Create Purchase Order → Add Products → Submit Purchase Order → Receive Goods → Update Inventory → Record Inventory Movement

### Inventory Workflow

Product → Inventory Record → Stock Increase/Decrease → Movement History → Low Stock Status

### Compliance Workflow

License/Permit → Issue Date → Expiration Date → Compliance Status → Renewal Tracking

## 9. Success Criteria

The MVP is successful if a user can:

- Create and manage products
- Create and manage vendors
- Track current inventory
- Create a purchase order
- Receive goods and update inventory
- View inventory movement history
- Track license or compliance expiration dates