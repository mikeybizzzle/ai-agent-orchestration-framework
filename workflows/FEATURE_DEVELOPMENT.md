# Feature Development Workflow

## Phase 1: Context Gathering (30 minutes)
1. Review requirements in Notion/docs
2. Understand acceptance criteria
3. Check existing patterns in codebase
4. Identify required MCPs
5. Create feature-specific context file

## Phase 2: Planning (15 minutes)
1. Break into parallel-executable tasks
2. Identify dependencies
3. Create git worktree for feature
4. Set up test structure
5. Document approach in DECISIONS.md

## Phase 3: Parallel Implementation (2-4 hours)
Run multiple agents simultaneously:

### Agent 1: Core Logic
```bash
claude-code --model opus-4 --task "Implement core business logic for [feature]"
```

### Agent 2: Tests
```bash
claude-code --model sonnet-4 --task "Write comprehensive tests for [feature]"
```

### Agent 3: UI Components
```bash
claude-code --model sonnet-4 --task "Build UI components for [feature]"
```

### Agent 4: Documentation
```bash
claude-code --task "Update docs and README for [feature]"
```

## Phase 4: Integration (30 minutes)
1. Merge parallel work
2. Run full test suite
3. Verify with Playwright screenshots
4. Update CHANGELOG.md
5. Create pull request

## Phase 5: Validation (15 minutes)
1. Automated CI/CD checks
2. Visual regression testing
3. Performance benchmarks
4. Security scanning
5. Human review if needed

## Success Checklist
- [ ] All acceptance criteria met
- [ ] Tests passing with >80% coverage
- [ ] Documentation updated
- [ ] No performance regression
- [ ] Screenshots verify UI correctness
- [ ] CHANGELOG.md updated
- [ ] Conventional commits used