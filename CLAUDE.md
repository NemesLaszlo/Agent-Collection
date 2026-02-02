# Project Agents

This project uses the following agents:

## Active Agents

All agents use **model: opus** for maximum capability.

### Engineering Core
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
