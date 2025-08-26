# Orchestration Principles

## The Fundamental Shift
We are transitioning from individual contributors to orchestrators of AI agent systems. The orchestration layer - not the code - is our primary artifact.

## Core Principles

### 1. Context as Infrastructure
- Context is not documentation; it's operational infrastructure
- Every piece of context should be immediately actionable by agents
- Structure context hierarchically: global → domain → feature → task

### 2. Friction Elimination
Identify and systematically remove every friction point that prevents autonomous agent operation:
- Missing context → Comprehensive markdown files
- Lack of validation → Automated testing loops
- No visual feedback → Playwright MCP for UI verification
- API confusion → Clear interface documentation

### 3. The Empathy Exercise
Before any task, spend 30 seconds imagining you are the LLM with ONLY:
- The prompt given
- The context provided
- The tools available

Ask: What else would I need to complete this successfully?

### 4. Speed Through Parallelization
- Use git worktrees for parallel agent execution
- Design tasks to be independently executable
- Minimize inter-agent dependencies
- Merge results systematically

### 5. Specification as Source Code
Your specifications, context, and orchestration logic ARE your source code. The actual code is just compiled output.

## Implementation Hierarchy
1. Manual execution → Document what works
2. Documented process → Create templates
3. Templates → Build MCPs
4. MCPs → Autonomous workflows

## Success Metrics
- Can an agent work for 45+ minutes without intervention?
- Can non-technical team members achieve technical outcomes?
- Is communication happening through working prototypes?
- Are you orchestrating 3+ agents simultaneously?