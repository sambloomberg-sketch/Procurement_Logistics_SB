# Procurement Logistics SB

Procurement and logistics management system.

## GitHub Copilot Setup

This repository is configured with [GitHub Copilot](https://github.com/features/copilot) customizations following the [awesome-copilot](https://github.com/github/awesome-copilot) patterns.

### Structure

```
.github/
├── copilot-instructions.md          # Project-level Copilot instructions
├── agents/
│   ├── code-reviewer.agent.md       # Code review agent
│   ├── debug.agent.md               # Debugging agent
│   ├── plan.agent.md                # Strategic planning agent
│   └── principal-engineer.agent.md  # Principal engineer guidance
├── instructions/
│   ├── code-review.instructions.md  # Code review guidelines
│   ├── python.instructions.md       # Python coding standards
│   └── security.instructions.md     # Security best practices
└── prompts/
    ├── explain-code.prompt.md       # Explain selected code
    ├── fix-issue.prompt.md          # Analyze and fix issues
    └── test-gen.prompt.md           # Generate tests
```

### Resources

| Type | Description |
|------|-------------|
| **Agents** | Specialized Copilot agents for debugging, planning, code review, and engineering guidance |
| **Instructions** | Coding standards applied automatically by file pattern (Python, security, code review) |
| **Prompts** | Reusable prompt templates for common tasks (test generation, code explanation, issue fixing) |

### Usage

- **Agents**: Invoke from the Copilot chat agent picker (e.g., `@debug`, `@plan`)
- **Instructions**: Applied automatically when editing matching files
- **Prompts**: Use from the Copilot chat prompt picker

### Customization

Add more resources from the [awesome-copilot](https://github.com/github/awesome-copilot) collection:

```
copilot plugin install <plugin-name>@awesome-copilot
```
