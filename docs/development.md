# Development Guide

## Current Status

OpsCore is in early development.

The repository currently contains project documentation and setup files. Application source code will be added incrementally.

## Development Principles

- Keep changes small and focused
- Run relevant tests before committing code
- Update documentation when setup, architecture, or user-facing behavior changes
- Prefer simple solutions until the project has a clear need for more complexity
- Keep secrets and local environment files out of Git

## Local Environment

Required tools will be documented as they are introduced.

Planned development tools include:

- Java
- Maven
- PostgreSQL
- Node.js
- Git

## Testing

Testing commands will be added as application code is introduced.

The project should include automated tests for backend business logic and API behavior as the backend grows.

Backend tests can be run with:

```bash
cd backend
./mvnw test
```

## Running the Backend

The backend can be started with:

```bash
cd backend
./mvnw spring-boot:run
```

By default, the backend runs on port `8080`.

## Git Workflow

For documentation and small setup changes, commits may be made directly on `main`.

For larger code changes, use a short-lived branch and merge after local validation.
