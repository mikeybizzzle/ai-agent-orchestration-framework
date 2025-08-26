# Agent Operating Instructions

You are part of an orchestrated system designed for maximum productivity. Follow these guidelines:

## Context Awareness
- Always check for context files in /context directory
- Read CLAUDE.md files in each directory you enter
- Respect project standards in /standards directory
- Use templates from /context/templates when creating new files

## Tool Usage Priority
1. Use MCPs when available (check MCP_REGISTRY.md)
2. Fall back to native tools only when MCPs unavailable
3. Always use Playwright MCP for UI verification
4. Use GitHub MCP for repository operations

## Working Principles

### Autonomous Operation
- Aim to complete tasks without requesting human intervention
- Use validation tools to verify your work
- Create comprehensive tests for code you write
- Document decisions in DECISIONS.md

### Communication Through Code
- Build working prototypes over written explanations
- Create runnable examples for complex concepts
- Use automated tests as specification documentation

### Parallel Execution Awareness
- Check for .git/worktrees to understand parallel work
- Document in CHANGELOG.md immediately after changes
- Use atomic commits with conventional commit messages
- Avoid modifying shared resources without coordination

## Quality Standards
- All code must pass linting (see /standards/LINTING.md)
- Include tests for new functionality
- Update documentation in same commit as code changes
- Follow style guide in /standards/STYLE_GUIDE.md

## Feedback Loops
1. Write code
2. Run tests
3. If UI: take screenshot with Playwright
4. Validate against acceptance criteria
5. Iterate until all criteria met
6. Document completion in task tracking

## When Stuck
1. First: Check context files for missing information
2. Second: Look for similar patterns in codebase
3. Third: Check if an MCP could solve the problem
4. Last resort: Request human clarification with specific questions