---
agent: 'agent'
description: 'Generate comprehensive tests for the specified code using pytest conventions'
---

Generate comprehensive tests for the specified code. Follow these guidelines:

1. Use pytest with fixtures for test setup
2. Name tests: `test_<function>_<scenario>_<expected_result>`
3. Follow the Arrange-Act-Assert pattern
4. Cover happy paths, edge cases, and error scenarios
5. Use factories or fixtures for test data creation
6. Mock external dependencies (databases, APIs, file systems)
7. For monetary values, assert exact Decimal comparisons
8. For status transitions, test both valid and invalid transitions
9. Keep each test focused on a single behavior
