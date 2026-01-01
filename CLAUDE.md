# CLAUDE.md - AI Assistant Guide for 16detector

## Repository Overview

**Repository Name:** 16detector
**Current State:** Initial setup phase
**Last Updated:** 2026-01-01

This document provides comprehensive guidance for AI assistants working on the 16detector codebase.

## Project Structure

```
16detector/
├── README.md           # Project documentation
├── CLAUDE.md          # This file - AI assistant guidance
└── .git/              # Git version control
```

### Current Status
This is a newly initialized repository. The project structure will evolve as development progresses.

## Development Workflows

### Git Branch Strategy

**Main Development Branch:** To be determined based on first code commit
**Feature Branches:** Use descriptive names prefixed with the feature type
- `feature/` - New features
- `bugfix/` - Bug fixes
- `refactor/` - Code refactoring
- `docs/` - Documentation updates

**Claude AI Branches:** When working through Claude Code interface:
- Branch pattern: `claude/claude-md-{session-id}`
- Always develop on the designated branch provided in the task context
- Never push to branches without explicit permission

### Commit Conventions

**Commit Message Format:**
```
<type>: <subject>

<body (optional)>
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation changes
- `refactor` - Code refactoring
- `test` - Adding or updating tests
- `chore` - Maintenance tasks
- `style` - Code style/formatting changes

**Best Practices:**
- Use imperative mood ("add feature" not "added feature")
- Keep subject line under 50 characters
- Capitalize subject line
- Don't end subject with period
- Provide context in body for non-trivial changes

### Git Operations

**Pushing Changes:**
```bash
# Always use -u flag for new branches
git push -u origin <branch-name>

# Retry logic for network failures (up to 4 times with exponential backoff)
# 2s, 4s, 8s, 16s intervals
```

**Fetching Updates:**
```bash
# Prefer specific branch fetches
git fetch origin <branch-name>

# For pulls
git pull origin <branch-name>
```

## Code Standards and Conventions

### General Principles

1. **Simplicity Over Complexity**
   - Avoid over-engineering solutions
   - Only make changes that are directly requested or clearly necessary
   - Keep solutions focused and minimal
   - Don't add features beyond what was asked

2. **Security First**
   - Always check for security vulnerabilities
   - Validate input at system boundaries
   - Avoid common vulnerabilities (XSS, SQL injection, command injection, etc.)
   - Follow OWASP Top 10 guidelines

3. **Code Quality**
   - Write self-documenting code
   - Add comments only where logic isn't self-evident
   - Don't add unnecessary error handling for scenarios that can't happen
   - Trust internal code and framework guarantees

4. **Avoid Premature Optimization**
   - Don't create abstractions for one-time operations
   - Three similar lines are better than a premature abstraction
   - Don't design for hypothetical future requirements

### Language-Specific Guidelines

#### Python (if used)
- Follow PEP 8 style guide
- Use type hints where appropriate
- Prefer list comprehensions over map/filter when readable
- Use virtual environments for dependencies

#### JavaScript/TypeScript (if used)
- Follow established linting rules
- Use modern ES6+ features
- Prefer async/await over raw promises
- Use TypeScript strict mode when applicable

#### Go (if used)
- Follow official Go style guide
- Use gofmt for formatting
- Handle errors explicitly
- Keep functions focused and small

#### Java (if used)
- Follow Java naming conventions
- Use meaningful variable names
- Prefer composition over inheritance
- Follow SOLID principles

## File Operations Best Practices

### Reading Files
- **Always read files before modifying them**
- Use the Read tool, not bash commands like `cat`
- Understand existing code before suggesting modifications

### Editing Files
- Use Edit tool for modifications, not `sed/awk`
- Preserve exact indentation
- Make surgical changes - modify only what's needed
- Never include line number prefixes in edits

### Creating Files
- **Prefer editing existing files over creating new ones**
- Only create files when absolutely necessary
- Use Write tool, not bash redirects or heredocs
- Don't proactively create documentation files unless requested

## Testing Strategies

### Test-Driven Development (when applicable)
1. Write failing test first
2. Implement minimum code to pass
3. Refactor while keeping tests green

### Testing Checklist
- [ ] Unit tests for core logic
- [ ] Integration tests for component interaction
- [ ] Edge cases and error conditions
- [ ] Security test cases for input validation
- [ ] Performance tests for critical paths (if applicable)

## Common Tasks and Patterns

### Analyzing the Codebase
1. Start with README and documentation
2. Identify entry points and main modules
3. Understand dependency structure
4. Map out data flow
5. Review tests to understand expected behavior

### Implementing New Features
1. Read and understand related existing code
2. Plan the implementation (use TodoWrite for complex tasks)
3. Make minimal necessary changes
4. Test the implementation
5. Commit with clear message
6. Push to designated branch

### Debugging Issues
1. Reproduce the issue
2. Identify the root cause (don't just treat symptoms)
3. Fix the underlying problem
4. Add tests to prevent regression
5. Verify fix works in context

### Refactoring Code
1. Ensure tests exist and pass
2. Make small, incremental changes
3. Keep tests passing after each change
4. Don't change behavior while refactoring
5. Commit frequently with descriptive messages

## AI Assistant Specific Guidelines

### Tool Usage
- **Use specialized tools** over bash commands when available
- **Read tool** for reading files (not cat/head/tail)
- **Edit tool** for editing (not sed/awk)
- **Write tool** for creating files (not echo/cat with heredoc)
- **Grep tool** for searching code (not bash grep)
- **Glob tool** for finding files (not find/ls)

### Task Management
- Use TodoWrite tool for complex multi-step tasks
- Mark todos as completed immediately after finishing
- Keep exactly ONE task in_progress at a time
- Break down complex tasks into smaller steps

### Communication
- Be concise and direct
- Output text directly to communicate with users
- Never use bash echo or comments to communicate
- Avoid emojis unless explicitly requested
- Focus on facts and problem-solving

### Exploration and Research
- Use Task tool with Explore agent for codebase exploration
- Don't run search commands directly for open-ended queries
- Gather context before making changes
- Verify understanding before implementation

## Project-Specific Notes

### 16detector Specific Conventions

*This section will be updated as project-specific patterns emerge.*

**Naming Conventions:**
- TBD based on first code contributions

**Architecture Patterns:**
- TBD based on project requirements

**Dependencies and Tools:**
- TBD based on technology stack chosen

**Build and Deployment:**
- TBD based on infrastructure setup

## Resources and Documentation

### Internal Documentation
- [README.md](README.md) - Project overview and setup instructions

### External Resources
- Git Documentation: https://git-scm.com/doc
- OWASP Top 10: https://owasp.org/www-project-top-ten/

## Changelog

### 2026-01-01
- Initial CLAUDE.md creation
- Established basic structure and conventions
- Awaiting project-specific patterns to emerge

---

**Note for AI Assistants:** This document should be updated as the project evolves. When you identify new patterns, conventions, or important information, update this file to help future AI assistants work more effectively on this codebase.
