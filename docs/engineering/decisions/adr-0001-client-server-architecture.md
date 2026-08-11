# ADR-0001: Use Client-Server Architecture for Version 1

## Status

Accepted

## Context

OpsCore is planned as a cross-platform retail operations and compliance management application.

The long-term product vision includes a desktop application for macOS and Windows. However, the first version needs to keep the architecture simple enough to build, test, and maintain while still supporting multiple clients in the future.

The main architectural options considered were:

1. Package the frontend, backend, and database together inside a desktop application.
2. Build a desktop client that connects to a central backend API and PostgreSQL database.

## Decision

OpsCore will use a client-server architecture for Version 1.

The desktop application will act as a client. It will package the React frontend using Electron and communicate with a central Spring Boot backend through REST APIs.

The Spring Boot backend and PostgreSQL database will not be bundled inside the desktop installer in Version 1.

## Consequences

Positive consequences:

- Keeps the desktop application simpler
- Allows multiple clients to connect to the same backend
- Keeps backend deployment and database management separate from desktop packaging
- Avoids early complexity around local databases and synchronization
- Makes the architecture closer to common business software systems

Negative consequences:

- Requires network access to use the application
- Requires backend hosting or a local backend environment
- Does not support offline workflows in Version 1
- Desktop packaging depends on backend API availability

## Alternatives Considered

### Bundle Backend and Database Inside Desktop App

This option would make OpsCore more self-contained.

It was not selected for Version 1 because it would require additional complexity around local process management, embedded database setup, backups, upgrades, and troubleshooting.

### Offline-First Desktop App

This option would allow the app to work without network access.

It was not selected for Version 1 because it would require local storage, synchronization, conflict resolution, and more complex testing.

## Revisit Criteria

This decision should be revisited if:

- Offline usage becomes a core product requirement
- Customers need single-machine deployments
- Backend hosting becomes a blocker
- Multi-client synchronization requirements change
