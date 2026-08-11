# OpsCore System Design

## 1. Architecture Overview

OpsCore will start as a web application with a Java Spring Boot backend, a PostgreSQL database, and a React TypeScript frontend.

After the core web application is stable, the React frontend will be packaged as a desktop application using Electron.

Initial architecture:

React + TypeScript
→ REST API
→ Spring Boot
→ PostgreSQL

Final desktop architecture:

Electron Desktop App
→ React + TypeScript
→ REST API
→ Spring Boot
→ PostgreSQL

## 2. Architecture Decision

OpsCore will use a client-server architecture.

The desktop app will act as a client. It will not include the Spring Boot backend or PostgreSQL database inside the desktop installer in the first version.

This keeps the first version simpler and closer to real-world business software, where multiple clients connect to a central backend.

## 3. Why Not Offline Mode in Version 1

Offline mode is out of scope for the MVP.

Supporting offline mode would require:

- Local database inside the desktop app
- Data synchronization
- Conflict resolution
- More complex error handling
- More complex testing

These are valuable features, but they add too much complexity for the first version.

## 4. Backend Architecture

The backend will use Java and Spring Boot.

The backend will follow a layered architecture:

Controller
→ Service
→ Repository
→ Database

### Controller Layer

The Controller layer receives HTTP requests from the frontend and returns HTTP responses.

Example responsibilities:

- Receive request body
- Validate request format
- Call the correct service method
- Return response with proper HTTP status code

### Service Layer

The Service layer contains business logic.

Example responsibilities:

- Create products
- Update inventory quantities
- Receive purchase orders
- Check license expiration status

### Repository Layer

The Repository layer communicates with the database.

In Spring Boot, repositories will use Spring Data JPA.

### Entity Layer

Entities represent database tables.

Example entities:

- Product
- Vendor
- Inventory
- PurchaseOrder
- PurchaseOrderItem
- InventoryMovement
- LicenseRecord
- User

### DTO Layer

DTO means Data Transfer Object.

DTOs are used to transfer data between the frontend and backend without exposing internal database entities directly.

## 5. Frontend Architecture

The frontend will use React and TypeScript.

The frontend will be responsible for:

- Pages
- Forms
- Tables
- Search and filtering
- User interactions
- Calling backend REST APIs

Initial frontend pages:

- Dashboard
- Products
- Vendors
- Inventory
- Purchase Orders
- Compliance
- Users

## 6. Database

OpsCore will use PostgreSQL.

PostgreSQL will store:

- Product data
- Vendor data
- Inventory data
- Purchase order data
- Inventory movement history
- License and compliance records
- User data

Spring Boot will communicate with PostgreSQL using Spring Data JPA and Hibernate.

## 7. Desktop Application Design

Electron will be added after the web application is stable.

Electron will package the React frontend into a desktop application.

The desktop app will call the same Spring Boot REST API used by the web frontend.

Version 1 desktop app responsibilities:

- Launch from macOS or Windows desktop
- Display React UI
- Call backend APIs
- Store minimal local settings if needed

Version 1 desktop app will not:

- Run PostgreSQL locally
- Run Spring Boot locally
- Support offline mode
- Handle automatic updates

## 8. Module Boundaries

Initial backend modules:

- product
- vendor
- inventory
- purchaseorder
- compliance
- user

Each module should contain its own:

- Controller
- Service
- Repository
- Entity
- DTOs

This keeps the modular monolith organized without introducing microservices.

## 9. Non-Goals

OpsCore will not use the following in the MVP:

- Microservices
- Kubernetes
- Kafka
- RabbitMQ
- Redis
- Offline sync
- Mobile apps

These may be considered later only if the project has a real need.

## 10. Engineering Principles

OpsCore should follow these principles:

- Start simple
- Use clear naming
- Keep business logic in services
- Keep controllers thin
- Use DTOs for API input and output
- Add tests gradually
- Prefer readability over clever code
- Avoid unnecessary infrastructure