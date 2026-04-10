---
description: 'Python coding standards and conventions for the procurement logistics project'
applyTo: '**/*.py'
---

# Python Instructions

## Conventions

- Use Python 3.11+ features where appropriate (match statements, `tomllib`, etc.)
- All functions must have type hints for parameters and return values
- Use `Decimal` for all monetary values; never use `float` for currency
- Use `datetime` with timezone info (`datetime.now(UTC)`) for all timestamps
- Prefer `dataclasses` or Pydantic models for data structures
- Use `enum.Enum` for status codes and fixed value sets

## Code Style

- Follow PEP 8; use Black for formatting (line length 88)
- Use Ruff for linting
- Import ordering: stdlib, third-party, local (enforced by isort)
- Use absolute imports; avoid relative imports except within the same package

## Patterns

- Repository pattern for database access
- Service layer for business logic orchestration
- Dependency injection via FastAPI's `Depends()`
- Use `contextmanager` for resource management (DB sessions, file handles)
- Async functions for I/O-bound operations (database queries, HTTP calls)

## Error Handling

- Define custom exception classes per domain (e.g., `PurchaseOrderNotFoundError`)
- Use FastAPI exception handlers to map domain exceptions to HTTP responses
- Never catch bare `Exception` unless re-raising
- Log errors with structured context (order ID, supplier ID, etc.)

## Testing

- Use pytest with fixtures for test setup
- Name tests: `test_<function>_<scenario>_<expected_result>`
- Use factories (factory_boy) for creating test data
- Mock external services; never make real HTTP calls in unit tests

## Anti-patterns

- No global mutable state
- No `from module import *`
- No bare `except:` clauses
- No `print()` for logging; use the `logging` module
- No hardcoded database connection strings
