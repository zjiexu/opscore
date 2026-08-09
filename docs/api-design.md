# OpsCore API Design

## 1. Overview

This document defines the initial REST API design for OpsCore.

The API will allow the frontend client to communicate with the Spring Boot backend using HTTP and JSON.

## 2. API Principles

OpsCore APIs should follow these principles:

- Use RESTful resource naming
- Use JSON for request and response bodies
- Use clear HTTP methods
- Use proper HTTP status codes
- Keep controller logic thin
- Use DTOs for API input and output
- Validate request data before processing business logic

## 3. Product APIs

### List Products

GET /api/products

Returns a list of products.

### Get Product By ID

GET /api/products/{id}

Returns one product by ID.

### Create Product

POST /api/products

Creates a new product.

Example request:

```json
{
  "name": "Milk",
  "sku": "MILK-001",
  "description": "Whole milk 1 gallon",
  "category": "Dairy",
  "unitPrice": 4.99
}
```

### Update Product

PUT /api/products/{id}

Updates an existing product.

### Delete Product

DELETE /api/products/{id}

Deletes or deactivates a product.

## 4. Vendor APIs

### List Vendors

GET /api/vendors

### Get Vendor By ID

GET /api/vendors/{id}

### Create Vendor

POST /api/vendors

Example request:

```json
{
  "name": "ABC Wholesale",
  "contactName": "John Smith",
  "email": "john@example.com",
  "phone": "312-555-1234"
}
```

### Update Vendor

PUT /api/vendors/{id}

### Delete Vendor

DELETE /api/vendors/{id}

## 5. Inventory APIs

### List Inventory

GET /api/inventory

### Get Inventory By Product ID

GET /api/inventory/products/{productId}

### Adjust Inventory

POST /api/inventory/products/{productId}/adjust

Example request:

```json
{
  "movementType": "INCREASE",
  "quantityChange": 10,
  "reason": "Manual stock adjustment"
}
```

## 6. Purchase Order APIs

### List Purchase Orders

GET /api/purchase-orders

### Get Purchase Order By ID

GET /api/purchase-orders/{id}

### Create Purchase Order

POST /api/purchase-orders

Example request:

```json
{
  "vendorId": 1,
  "expectedDeliveryDate": "2026-09-01"
}
```

### Add Item To Purchase Order

POST /api/purchase-orders/{id}/items

Example request:

```json
{
  "productId": 1,
  "quantity": 20,
  "unitCost": 3.50
}
```

### Submit Purchase Order

POST /api/purchase-orders/{id}/submit

### Receive Purchase Order

POST /api/purchase-orders/{id}/receive

## 7. License APIs

### List Licenses

GET /api/licenses

### Get License By ID

GET /api/licenses/{id}

### Create License

POST /api/licenses

Example request:

```json
{
  "name": "Retail Business License",
  "licenseNumber": "LIC-12345",
  "issuingAuthority": "City of Chicago",
  "issueDate": "2026-01-01",
  "expirationDate": "2026-12-31"
}
```

### Update License

PUT /api/licenses/{id}

### List Expiring Licenses

GET /api/licenses/expiring-soon

## 8. Common HTTP Status Codes

OpsCore APIs should use:

- 200 OK: Request succeeded
- 201 Created: Resource created successfully
- 400 Bad Request: Invalid request data
- 401 Unauthorized: User is not authenticated
- 403 Forbidden: User does not have permission
- 404 Not Found: Resource does not exist
- 409 Conflict: Request conflicts with current state
- 500 Internal Server Error: Unexpected server error

## 9. Future API Features

Future versions may include:

- Pagination
- Sorting
- Filtering
- Authentication
- Role-based authorization
- Audit history
- File upload APIs
