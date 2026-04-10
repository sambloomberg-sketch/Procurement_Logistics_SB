# Project: Procurement Logistics SB

## Overview

Enterprise procurement and logistics management system. This codebase handles supplier management, purchase orders, inventory tracking, shipment coordination, and supply chain analytics.

## Tech Stack

- Language: Python 3.11+
- Framework: FastAPI (backend), React (frontend where applicable)
- Database: PostgreSQL with SQLAlchemy ORM
- Package Manager: pip / npm
- Testing: pytest, vitest

## Code Standards

- Follow PEP 8 for Python code
- Use type hints on all function signatures
- Use Black for formatting, Ruff for linting
- Write docstrings for public API endpoints and domain services
- Use conventional commits for commit messages

## Architecture

- Domain-driven design with clear bounded contexts: Procurement, Inventory, Logistics, Supplier Management
- Service layer pattern: Controllers -> Services -> Repositories -> Database
- Event-driven communication between bounded contexts where applicable
- RESTful API design following OpenAPI 3.0 specification

## Development Workflow

1. Create a feature branch from `main`
2. Implement changes with tests
3. Run `pytest` and ensure all tests pass
4. Submit a pull request for review
5. Squash-merge after approval

## Important Patterns

- All monetary values use `Decimal` type, never `float`
- Dates and timestamps use UTC with timezone awareness (`datetime` with `tzinfo`)
- Supplier and inventory IDs use UUIDs
- Status transitions follow defined state machines (e.g., PO: Draft -> Submitted -> Approved -> Fulfilled -> Closed)
- All database operations go through repository classes, never raw SQL in services

## Do Not

- Use `float` for currency or financial calculations
- Commit secrets, API keys, or credentials to the repository
- Bypass the service layer by calling repositories directly from controllers
- Use mutable default arguments in function signatures
- Hardcode supplier-specific logic; use configuration or strategy patterns instead
