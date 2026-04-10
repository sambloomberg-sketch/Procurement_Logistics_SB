---
description: 'Generic code review guidelines for pull request reviews'
applyTo: '**'
---

# Code Review Instructions

## Review Priorities

### CRITICAL (Block merge)
- Security vulnerabilities or exposed secrets
- Logic errors that could cause data corruption
- Breaking API changes without versioning
- Financial calculation errors (rounding, currency handling)

### IMPORTANT (Requires discussion)
- Missing tests for critical paths
- N+1 queries or obvious performance issues
- Violations of architectural patterns
- Inadequate error handling for external service calls

### SUGGESTION (Non-blocking)
- Naming improvements
- Minor readability enhancements
- Performance optimizations without functional impact

## Review Principles

1. **Be specific**: Reference exact lines and provide concrete examples
2. **Provide context**: Explain WHY something is an issue
3. **Suggest solutions**: Show corrected code, not just what's wrong
4. **Be constructive**: Focus on improving code, not criticizing the author
5. **Be pragmatic**: Not every suggestion needs immediate implementation

## Checklist

- [ ] Code follows project conventions and style guide
- [ ] Functions are small, focused, and well-named
- [ ] No code duplication
- [ ] Appropriate error handling
- [ ] No sensitive data in code or logs
- [ ] All user inputs validated
- [ ] New code has test coverage
- [ ] Tests cover edge cases
- [ ] No obvious performance issues
- [ ] API changes are documented
