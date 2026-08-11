# Architecture Overview

## System Direction

OpsCore is planned as a client-server application.

The MVP will be developed in stages:

1. Backend API
2. Relational database
3. Web frontend
4. Desktop packaging for macOS and Windows

## High-Level Architecture

```text
macOS / Windows Desktop App
-> Web Frontend
-> Backend API
-> Relational Database
```

## Backend

The backend will provide the main business logic and API layer.

Initial backend responsibilities:

- Product management
- Vendor management
- Inventory tracking
- Purchase order workflow
- Inventory movement records
- License and compliance records

## Database

The database will store application data such as products, vendors, inventory records, purchase orders, and compliance records.

A relational database is planned for the MVP.

## Frontend

The frontend will provide the user interface for managing retail operations.

The web frontend will be developed before desktop packaging.

## Desktop Application

The desktop application will package the user interface for macOS and Windows.

The first desktop version will not be offline-first. Offline support may be considered later if it becomes a core product requirement.
