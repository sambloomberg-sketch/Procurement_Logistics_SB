---
description: 'Security best practices and OWASP guidelines for all code'
applyTo: '**'
---

# Security Instructions

## Input Validation

- Validate all user inputs at API boundaries using Pydantic models
- Sanitize inputs before use in database queries or external calls
- Use parameterized queries; never concatenate user input into SQL strings
- Validate file uploads: check type, size, and content

## Authentication & Authorization

- Verify authentication on all API endpoints (except explicitly public ones)
- Check authorization (role/permission) before executing business logic
- Use short-lived tokens with proper expiration
- Never expose internal IDs that could be enumerated

## Secrets Management

- Never commit secrets, API keys, or credentials to the repository
- Use environment variables or a secrets manager for sensitive configuration
- Rotate secrets regularly; support multiple active keys during rotation

## Data Protection

- Encrypt sensitive data at rest (supplier contracts, pricing agreements)
- Use HTTPS for all external communications
- Mask PII in logs (email addresses, phone numbers, tax IDs)
- Follow data retention policies; purge data when no longer needed

## Dependency Security

- Keep dependencies up to date
- Review dependency changelogs before upgrading major versions
- Use `pip-audit` or similar tools to scan for known vulnerabilities
- Pin dependency versions in production

## Common Vulnerabilities to Avoid

- SQL Injection: always use parameterized queries
- XSS: sanitize all user-generated content before rendering
- CSRF: use anti-CSRF tokens for state-changing operations
- IDOR: validate object ownership before granting access
- Mass Assignment: use explicit allow-lists for accepted fields
