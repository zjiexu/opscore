# OpsCore

OpsCore is a retail operations and compliance management platform for small and medium-sized retail businesses.

It is designed to centralize products, vendors, inventory, purchase orders, inventory movements, and compliance records into one maintainable system.

## Project Status

OpsCore is in early development.

The MVP goal is to deliver a usable desktop application for macOS and Windows that can be downloaded from GitHub releases and used to manage core retail operations.

Development will start with the backend and database foundation, then add the web frontend, and finally package the application as a desktop app.

## MVP Goal

The first usable MVP should allow a user to:

- Download and launch OpsCore on macOS or Windows
- Manage products and vendors
- Track inventory
- Create and receive purchase orders
- Record inventory movement history
- Track licenses and compliance records

## Architecture Direction

OpsCore is planned as a client-server application:

```text
macOS / Windows Desktop App
-> Backend API
-> Relational Database
```
