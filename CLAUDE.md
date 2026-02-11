# Project Agents

This project uses the following agents:

## Active Agents

All agents use **model: opus** for maximum capability.

### Engineering Core
- [Feature Planner](.claude/agents/engineering/feature-planner.md) — Three-phase validation before implementation (specs, tasks, plan)
- [Clean Code Architect](.claude/agents/engineering/clean-code-architect.md) — Quality code implementation with DRY, SOLID principles
- [DeepDive](.claude/agents/engineering/deepdive.md) — Deep investigation and root cause analysis (research only)
- [DeepCode](.claude/agents/engineering/deepcode.md) — Implementation partner for DeepDive findings
- [Security Vulnerability Scanner](.claude/agents/engineering/security-vulnerability-scanner.md) — Security audits and vulnerability assessment

### Engineering Specialists
- [Backend Architect](.claude/agents/engineering-additional/backend-architect.md) — System design, APIs, databases, scaling
- [Frontend Developer](.claude/agents/engineering-additional/frontend-developer.md) — Modern web UI, Angular, React/Vue, accessibility
- [Mobile App Builder](.claude/agents/engineering-additional/mobile-app-builder.md) — iOS/Android, React Native/Flutter
- [AI Engineer](.claude/agents/engineering-additional/ai-engineer.md) — LLM integration, RAG, Claude MCP
- [DevOps Automator](.claude/agents/engineering-additional/devops-automator.md) — CI/CD, infrastructure, deployment
- [Rapid Prototyper](.claude/agents/engineering-additional/rapid-prototyper.md) — Fast MVP development

### Design
- [UI Designer](.claude/agents/design/ui-designer.md) — Visual design, component libraries, design systems
- [UX Researcher](.claude/agents/design/ux-researcher.md) — User research, usability testing, insights

### Agent Collaboration Patterns

| Workflow | Agents | Description |
|----------|--------|-------------|
| **Bug Investigation → Fix** | DeepDive → DeepCode | DeepDive investigates, DeepCode implements |
| **Security Audit → Remediation** | Security Scanner → DeepCode | Scanner finds issues, DeepCode fixes |
| **Design → Implementation** | UI Designer → Frontend Developer | Design specs to production code |
| **Research → Design → Build** | UX Researcher → UI Designer → Frontend Developer | Full design workflow |
| **Architecture → Implementation** | Backend Architect → Clean Code Architect | Design then quality implementation |
| **Prototype → Production** | Rapid Prototyper → Frontend Developer / Backend Architect | Validate then scale |
| **Feature Planning → Implementation** | Feature Planner → Clean Code Architect / Frontend Developer / Backend Architect | Validate specs, tasks, plan → then implement |
| **Feature Planning → Investigation → Fix** | Feature Planner → DeepDive → DeepCode | Plan reveals unknowns, investigate, then implement |
| **Exploratory → Plan → Implementation** | DeepDive → Feature Planner → Implementation agents | Investigate unfamiliar code first, then plan with full context |

### Recommended Feature Workflow

Choose the right planning approach based on feature size:

| Feature Size | Approach | Example |
|---|---|---|
| **Small** (single task, clear scope) | Normal plan mode — skip the Feature Planner | Add a tooltip, fix a typo, rename a field |
| **Medium-to-large** (multiple tasks, touches data/auth/APIs) | Feature Planner agent — run all 3 phases | New CRUD module, auth flow, payment integration |
| **Exploratory** (unknowns, need to spike first) | DeepDive first → then Feature Planner | Unfamiliar legacy code, unknown API behavior, perf investigation |

For medium-to-large features:

```
1. Feature Idea
   ↓
2. Feature Planner (3 validation phases)
   Phase 1: Domain & Spec Validation
   Phase 2: Task Validation (edge cases, security, data, rollback)
   Phase 3: Implementation Plan Validation
   ↓
3. Validated plan with refined tasks
   ↓
4. /task for each validated task
   ↓
5. Implementation (using assigned subagents)
```

**Triggering the Feature Planner:** Use `/plan-feature [description]` or ask Claude to "use the Feature Planner agent". The agent will run all three validation phases and produce an implementation-ready plan before any code is written.

### Available Skills

| Skill | Trigger | Purpose |
|---|---|---|
| `/plan-feature` | `/plan-feature [description]` | Run 3-phase Feature Planner validation |
| `/investigate` | `/investigate [problem]` | Deep root cause analysis (DeepDive workflow) |
| `/review` | `/review [file or blank]` | Code review against Clean Code principles |
| `/security-scan` | `/security-scan [target or blank]` | Security vulnerability scan |
| `/explore` | `/explore [question]` | Quick codebase exploration and understanding |
