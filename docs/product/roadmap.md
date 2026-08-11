# OpsCore Product Roadmap

## 1. Purpose

This roadmap describes the planned product direction for OpsCore.

It communicates current priorities, near-term product capabilities, and long-term opportunities. It is not a fixed release commitment.

## 2. Roadmap Principles

OpsCore roadmap decisions should follow these principles:

- Prioritize operational workflows before advanced features
- Build the smallest useful version before expanding scope
- Prefer simple, maintainable architecture over premature complexity
- Validate core inventory, purchasing, and compliance workflows early
- Add desktop packaging after the web application is stable
- Treat long-term ideas as opportunities, not guaranteed commitments

## 3. Now

Current focus: establish the core retail operations foundation.

Planned capabilities:

- Product catalog management
- Vendor management
- Basic inventory tracking
- Initial backend API foundation
- PostgreSQL-backed data persistence

Business value:

- Centralizes core retail operations data
- Reduces reliance on spreadsheets and paper records
- Creates a foundation for purchasing and compliance workflows

Out of scope for Now:

- Desktop packaging
- Offline mode
- Mobile applications
- Advanced reporting
- Third-party integrations

## 4. Next

Upcoming focus: support purchasing workflows and inventory traceability.

Planned capabilities:

- Purchase order creation
- Purchase order item management
- Purchase order submission
- Purchase receiving workflow
- Inventory quantity updates from received goods
- Inventory movement history
- License and compliance record tracking

Business value:

- Improves visibility from vendor purchasing to inventory updates
- Reduces inventory tracking errors
- Creates a historical record of stock changes
- Helps identify upcoming compliance deadlines

Out of scope for Next:

- Accounting integration
- Payment processing
- Multi-store inventory
- Automated vendor communication
- Offline synchronization

## 5. Later

Future focus: improve security, usability, and desktop distribution.

Planned capabilities:

- Authentication
- Role-based access control
- Dashboard
- Search
- Filtering
- Sorting
- Pagination
- Audit history
- Business document management
- Notifications and reminders
- Electron desktop packaging
- macOS application build
- Windows installer build

Business value:

- Supports real multi-user workflows
- Improves operational visibility
- Makes the application easier to use in daily store operations
- Enables OpsCore to be distributed as an installable desktop application

## 6. Long-Term Opportunities

Potential future directions include:

- Multi-store support
- Offline mode
- Local desktop database
- Data synchronization
- Mobile clients
- Advanced analytics
- POS integrations
- Accounting integrations
- Automatic desktop updates
- Cloud deployment options

These items require additional product validation and technical design before implementation.

## 7. Roadmap Review Process

The roadmap should be reviewed as the product evolves.

Before adding a major feature, the following questions should be answered:

- What user problem does this solve?
- Why is this important now?
- What is the smallest useful version of this feature?
- What systems or modules will be affected?
- What risks or trade-offs does this introduce?
- How will we know the feature is successful?

## 8. Non-Goals

The current roadmap does not prioritize:

- Microservices
- Kubernetes
- Kafka
- RabbitMQ
- Redis
- Mobile applications
- Offline-first architecture

These technologies or capabilities should only be introduced if OpsCore has a clear product or engineering need that justifies the added complexity.
