# AI Agent Orchestration Framework

A knowledge-based orchestration system designed to achieve **10x productivity gains** with AI coding agents through parallel execution, context-driven development, and systematic friction elimination.

## Overview

This framework transforms how teams work with AI coding agents by shifting from individual contributor mindset to **orchestrator of AI agent systems**. Rather than a traditional code library, it's a comprehensive operational system that treats context and specifications as primary artifacts—the real "source code"—while actual code becomes the compiled output.

**Key Philosophy:** Context is operational infrastructure. Orchestration logic is your competitive advantage.

### Why This Framework?

Working with a single AI agent is helpful. **Orchestrating 3-4 agents in parallel is transformational.**

This framework provides:
- Battle-tested orchestration principles from production environments
- Multi-layer validation ensuring quality at every step
- Structured workflows for parallel agent execution
- Context management systems that eliminate friction
- Integration patterns for essential AI tools (MCPs)

## Features

### Core Capabilities

- **Parallel Agent Orchestration** - Coordinate 3-4 agents simultaneously on different aspects of features
- **Context as Infrastructure** - Hierarchical, actionable context structure (global → domain → feature → task)
- **Friction Elimination** - Systematic removal of barriers to autonomous agent operation
- **Multi-Layer Validation** - Automated quality assurance across syntax, unit, integration, UI, and business logic
- **MCP Integration** - Built-in support for Model Context Protocol tools (Playwright, GitHub, FireCrawl, etc.)
- **Communication Through Code** - Emphasis on working prototypes over written explanations
- **Atomic Operations** - Conventional commits, CHANGELOG documentation, traceability

### Success Metrics

The framework is working when:
- ✅ Agents work 45+ minutes uninterrupted
- ✅ Non-technical team members achieve technical outcomes
- ✅ Communication happens through working prototypes
- ✅ You're orchestrating 3+ agents simultaneously

## Quick Start

### Prerequisites

- [Claude Code CLI](https://claude.com/claude-code) installed and authenticated
- Node.js (for npm-based MCPs)
- Git with worktree support

### Setup (5 minutes)

1. **Install Claude Code CLI**
   ```bash
   # Follow installation instructions at https://claude.com/claude-code
   claude-code --version
   ```

2. **Configure MCPs**

   Create `.claude/mcp_settings.json`:
   ```json
   {
     "mcps": [
       {
         "name": "playwright-mcp",
         "command": "npx",
         "args": ["playwright-mcp"],
         "type": "stdio"
       },
       {
         "name": "github-mcp",
         "command": "npx",
         "args": ["@modelcontextprotocol/server-github"],
         "type": "stdio"
       }
     ]
   }
   ```

3. **Create Context Structure**
   ```bash
   mkdir -p context/{business,technical,domain}
   cp CONTEXT_TEMPLATE.md context/PROJECT_CONTEXT.md
   # Edit context/PROJECT_CONTEXT.md with your project specifics
   ```

4. **Setup Git Worktrees** (for parallel agents)
   ```bash
   git worktree add ../agent-1-core main
   git worktree add ../agent-2-tests main
   git worktree add ../agent-3-ui main
   ```

5. **Create CLAUDE.md**

   In your project root:
   ```markdown
   # Agent Instructions

   ## Context
   - Always read `/context/PROJECT_CONTEXT.md` before starting work
   - Check this directory's CLAUDE.md for specific instructions

   ## Standards
   - Use conventional commits
   - Update CHANGELOG.md with all changes
   - Run tests before committing
   ```

### Your First Orchestrated Feature (30 minutes)

Follow the **Feature Development Workflow**:

**Phase 1: Context Gathering (5 min)**
```bash
# Review requirements and create feature context
cat > context/feature-auth.md <<EOF
# Feature: User Authentication
## Acceptance Criteria
- Users can register with email/password
- Sessions persist for 7 days
- Password reset via email
EOF
```

**Phase 2: Planning (5 min)**
- Break into parallel tasks
- Create worktree if needed
- Document approach

**Phase 3: Parallel Implementation (15 min)**
```bash
# Terminal 1: Core Logic (Opus 4)
cd ../agent-1-core
claude-code --model opus-4 --task "Implement auth logic per context/feature-auth.md"

# Terminal 2: Tests (Sonnet 4)
cd ../agent-2-tests
claude-code --model sonnet-4 --task "Write comprehensive auth tests per context/feature-auth.md"

# Terminal 3: UI Components (Sonnet 4)
cd ../agent-3-ui
claude-code --model sonnet-4 --task "Build auth UI components per context/feature-auth.md"
```

**Phase 4: Integration (3 min)**
```bash
# Merge all work
git merge agent-1-core/main
git merge agent-2-tests/main
git merge agent-3-ui/main

# Validate
npm test
npx playwright test
```

**Phase 5: Validation (2 min)**
- Review test results
- Check Playwright screenshots
- Update CHANGELOG.md

## Documentation Structure

| Document | Purpose | When to Use |
|----------|---------|-------------|
| [ORCHESTRATION_PRINCIPLES.md](./ORCHESTRATION_PRINCIPLES.md) | Core philosophy and approach | Understanding the "why" |
| [AGENT_INSTRUCTIONS.md](./AGENT_INSTRUCTIONS.md) | Operating procedures for AI agents | Agent configuration |
| [SETUP_GUIDE.md](./SETUP_GUIDE.md) | Detailed environment setup | Initial setup and daily workflow |
| [CONTEXT_TEMPLATE.md](./CONTEXT_TEMPLATE.md) | Standardized context structure | Creating project context |
| [MCP_REGISTRY.md](./MCP_REGISTRY.md) | Essential tools and MCPs | Tool integration |
| [VALIDATION_FRAMEWORK.md](./VALIDATION_FRAMEWORK.md) | Quality assurance system | Ensuring code quality |
| [workflows/FEATURE_DEVELOPMENT.md](./workflows/FEATURE_DEVELOPMENT.md) | Detailed feature workflow | Building new features |

## Core Concepts

### 1. Context as Infrastructure

Context isn't documentation—it's operational infrastructure. Every piece of context should be immediately actionable by an agent.

**Hierarchical Structure:**
```
Global Context (project-wide)
  └─ Domain Context (auth, payments, etc.)
      └─ Feature Context (specific feature)
          └─ Task Context (individual task)
```

### 2. The Empathy Exercise

**Before assigning work to an agent, take 30 seconds:**
- What context is missing?
- What validation tools are needed?
- What decisions can I make now to prevent interruptions?

This simple exercise eliminates 80% of friction.

### 3. Parallel Execution

Use git worktrees to run 3-4 agents simultaneously:
- **Agent 1** (Opus 4): Complex core business logic
- **Agent 2** (Sonnet 4): Comprehensive test suites
- **Agent 3** (Sonnet 4): UI components
- **Agent 4** (Default): Documentation and updates

**Key:** Design tasks to minimize inter-agent dependencies.

### 4. Multi-Layer Validation

Validation happens at 5 levels:
1. **Syntax & Linting** - ESLint, Prettier (automated)
2. **Unit Tests** - Individual functions (80% coverage minimum)
3. **Integration Tests** - Component interactions
4. **UI Verification** - Playwright screenshots
5. **Business Logic** - Acceptance criteria validation

### 5. Specification as Source Code

The real source code isn't JavaScript/Python—it's your specifications:
- Requirements documents
- API contracts
- Business rules
- Acceptance criteria

Treat them with the same rigor as code.

## MCP Integration

The framework leverages Model Context Protocol tools for enhanced agent capabilities:

### Essential MCPs

- **Playwright MCP** - Browser automation, UI verification, screenshots
- **GitHub MCP** - Repository operations, PRs, issues, CI/CD status
- **FireCrawl MCP** - Website-to-markdown conversion, data extraction
- **Context7 MCP** - Enhanced context management
- **Notion MCP** - Team documentation access

See [MCP_REGISTRY.md](./MCP_REGISTRY.md) for detailed configuration.

## Daily Workflow

### Morning Routine (5 min)
```bash
git pull
cat CHANGELOG.md | head -20  # Review recent changes
# Update context if needed
# Check CI/CD status via GitHub MCP
```

### During Development
- Use planning mode for complex tasks
- Run agents in parallel when possible
- Validate continuously (not just at end)
- Update CHANGELOG.md atomically with changes

### End of Day (5 min)
```bash
# Merge worktree work
git merge agent-*/main

# Update CHANGELOG
echo "## $(date +%Y-%m-%d)\n- Summary of changes" >> CHANGELOG.md

# Push
git push

# Plan tomorrow
cat > context/tomorrow.md <<EOF
# Tomorrow's Focus
- [ ] Task 1
- [ ] Task 2
EOF
```

## Advanced Patterns

### Custom MCP Development

Create project-specific MCPs for:
- Internal API validation
- Business rule checking
- Custom deployment workflows

See template in [MCP_REGISTRY.md](./MCP_REGISTRY.md).

### Context Hierarchy

```
/context/
  ├── PROJECT_CONTEXT.md          # Global context
  ├── business/
  │   ├── objectives.md           # Business goals
  │   └── constraints.md          # Budget, compliance, deadlines
  ├── technical/
  │   ├── architecture.md         # System design
  │   └── patterns.md             # Code patterns
  └── domain/
      ├── auth.md                 # Authentication domain
      └── payments.md             # Payments domain
```

### Friction Elimination Checklist

When an agent gets stuck, systematically ask:
- ❓ What context was missing?
- ❓ What validation could have caught this earlier?
- ❓ What decision could I have made upfront?
- ❓ What tool/MCP would prevent this in the future?

Document the answer and update your context/MCPs.

## Implementation Hierarchy

Progress through these stages:

1. **Manual Execution** - Run tasks manually to understand them
2. **Document** - Write down the process
3. **Create Templates** - Make reusable templates
4. **Build MCPs** - Automate with tools
5. **Autonomous Workflows** - Full agent autonomy

Don't skip steps—each builds understanding for the next.

## Best Practices

### For Orchestrators

- ✅ Spend 80% of time on context and specifications
- ✅ Use "The Empathy Exercise" before every agent assignment
- ✅ Design tasks for parallel execution
- ✅ Validate continuously, not just at the end
- ✅ Treat specifications as source code

### For Agent Instructions

- ✅ Always check `/context` directory first
- ✅ Use MCPs over native tools when available
- ✅ Complete tasks without interruption
- ✅ Communicate through working prototypes
- ✅ Update CHANGELOG.md with all changes
- ✅ Use conventional commits

### For Quality

- ✅ Minimum 80% test coverage
- ✅ Playwright screenshots for UI changes
- ✅ All validation layers must pass
- ✅ Performance benchmarks for critical paths
- ✅ Atomic, well-documented commits

## Examples

### Example: Bug Fix Workflow

```bash
# 1. Create failing test first
claude-code --task "Write failing test for bug #123"

# 2. Fix in parallel
claude-code --model opus-4 --task "Fix bug #123 (test exists)"

# 3. Verify with screenshots
npx playwright test --screenshot

# 4. Update CHANGELOG
echo "- Fixed bug #123: [description]" >> CHANGELOG.md
```

### Example: Refactoring

```bash
# 1. Capture current behavior
claude-code --task "Write tests capturing current behavior of auth module"

# 2. Refactor with confidence
claude-code --model opus-4 --task "Refactor auth module per context/refactor-auth.md"

# 3. Performance comparison
npm run benchmark -- auth-module

# 4. Document changes
claude-code --task "Update architecture docs for auth refactor"
```

## Troubleshooting

### Agents Keep Getting Stuck

**Solution:** Review context quality using The Empathy Exercise. Add missing information to CLAUDE.md or context files.

### Tests Failing in CI/CD

**Solution:** Ensure agents run same validation locally that CI runs. Add pre-commit hooks.

### Merge Conflicts from Parallel Work

**Solution:** Design tasks with clearer boundaries. Use separate modules/files when possible. Merge more frequently.

### Agents Asking Too Many Questions

**Solution:** Missing context. Create decision frameworks in context files. Document preferences and standards.

## Contributing

This framework improves through real-world usage. To contribute:

1. Document patterns that worked for your team
2. Share friction elimination discoveries
3. Contribute custom MCP templates
4. Submit workflow improvements

## License

This framework is provided as-is for teams to adopt and customize for their needs.

## Acknowledgments

Based on orchestration principles developed by Patrick Ellis and proven in production environments to enable 10x productivity gains with AI coding agents.

Built with [Claude Code](https://claude.com/claude-code) - demonstrating the framework's own principles in action.

---

## Next Steps

1. **Read** [ORCHESTRATION_PRINCIPLES.md](./ORCHESTRATION_PRINCIPLES.md) to understand the philosophy
2. **Follow** [SETUP_GUIDE.md](./SETUP_GUIDE.md) for detailed environment setup
3. **Review** [AGENT_INSTRUCTIONS.md](./AGENT_INSTRUCTIONS.md) to configure your agents
4. **Try** the Quick Start feature development workflow above
5. **Join** the community to share learnings and patterns

**Ready to 10x your productivity?** Start with a single feature using parallel agents and experience the difference.
