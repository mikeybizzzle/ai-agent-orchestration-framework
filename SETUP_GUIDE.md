# Environment Setup Guide

## Prerequisites
- Claude Code CLI installed
- Git configured with worktrees enabled
- Node.js/Python/[Your stack]
- VS Code or preferred IDE

## Initial Setup

### 1. Install Claude Code
```bash
npm install -g @anthropic/claude-code
claude-code auth
```

### 2. Configure MCPs
Create `.claude/mcp_settings.json`:
```json
{
  "mcps": [
    {
      "name": "playwright-mcp",
      "command": "npx",
      "args": ["playwright-mcp"]
    },
    {
      "name": "github-mcp",
      "command": "github-mcp"
    }
  ]
}
```

### 3. Set Up Context Structure
```bash
mkdir -p context/{business,technical,templates}
mkdir -p workflows
mkdir -p standards
cp CONTEXT_TEMPLATE.md context/PROJECT_CONTEXT.md
```

### 4. Initialize Git Worktrees
```bash
git worktree add ../project-agent-1 -b agent-1-work
git worktree add ../project-agent-2 -b agent-2-work
git worktree add ../project-agent-3 -b agent-3-work
```

### 5. Create CLAUDE.md
```bash
echo "# Project Assistant Instructions

Read /context/PROJECT_CONTEXT.md for full context.
Follow /AGENT_INSTRUCTIONS.md for operating procedures.
Use MCPs listed in /MCP_REGISTRY.md.
Validate work per /VALIDATION_FRAMEWORK.md.
" > CLAUDE.md
```

## Daily Workflow

### Morning Setup
1. Pull latest changes
2. Review CHANGELOG.md
3. Update context files if needed
4. Check CI/CD status

### During Development
1. Use planning mode for complex tasks
2. Run agents in parallel with worktrees
3. Validate continuously with MCPs
4. Document decisions immediately

### End of Day
1. Merge completed work
2. Update CHANGELOG.md
3. Push to remote
4. Review tomorrow's tasks

## Troubleshooting

### Agent Can't Find Context
- Verify CLAUDE.md exists in root
- Check context file paths
- Ensure markdown formatting is valid

### MCP Not Working
- Verify MCP installed correctly
- Check command/args in settings
- Review MCP logs for errors

### Parallel Work Conflicts
- Use atomic commits
- Separate concerns between agents
- Merge frequently to avoid drift