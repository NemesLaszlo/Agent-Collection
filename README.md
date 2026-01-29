# Agent Collection

A curated library of specialized Claude AI agents designed for production software development workflows. Each agent is optimized for specific tasks and can work independently or in collaborative pipelines.

## Overview

This collection provides **12 specialized agents** across three domains:
- **Engineering Core** (4 agents) - Code quality, investigation, implementation, security
- **Engineering Specialists** (6 agents) - Backend, frontend, mobile, AI, DevOps, prototyping
- **Design** (2 agents) - UI design, UX research

All agents use **Claude Opus** for maximum capability.

## Quick Start

### Using Agents in Your Project

1. Copy the desired agent files to your project's `.claude/agents/` directory
2. Reference agents in your project's `CLAUDE.md` file
3. Invoke agents through Claude Code CLI

```bash
# Example project structure
your-project/
├── .claude/
│   └── agents/
│       ├── engineering/
│       │   └── clean-code-architect.md
│       └── design/
│           └── ui-designer.md
└── CLAUDE.md
```

### Example CLAUDE.md Configuration

```markdown
# Project Agents

## Active Agents

### Engineering
- [Clean Code Architect](.claude/agents/engineering/clean-code-architect.md) — Quality code implementation

### Design
- [UI Designer](.claude/agents/design/ui-designer.md) — Visual design and components
```

## Agent Catalog

### Engineering Core

| Agent | Purpose | Best For |
|-------|---------|----------|
| **[Clean Code Architect](engineering/clean-code-architect.md)** | Quality code with DRY, SOLID principles | Feature implementation, refactoring, creating reusable modules |
| **[DeepDive](engineering/deepdive.md)** | Deep investigation and root cause analysis | Bug investigation, performance issues, architectural problems |
| **[DeepCode](engineering/deepcode.md)** | Implementation partner for DeepDive | Executing fixes based on investigation findings |
| **[Security Vulnerability Scanner](engineering/security-vulnerability-scanner.md)** | Security audits and vulnerability assessment | OWASP Top 10, penetration testing, security reviews |

### Engineering Specialists

| Agent | Purpose | Best For |
|-------|---------|----------|
| **[Backend Architect](engineering-additional/backend-architect.md)** | System design, APIs, databases, scaling | API design, database architecture, microservices |
| **[Frontend Developer](engineering-additional/frontend-developer.md)** | Modern web UI, accessibility, performance | React/Angular/Vue development, Core Web Vitals |
| **[Mobile App Builder](engineering-additional/mobile-app-builder.md)** | iOS/Android, cross-platform apps | React Native, Flutter, native integrations |
| **[AI Engineer](engineering-additional/ai-engineer.md)** | LLM integration, RAG, Claude MCP | AI features, embeddings, agentic workflows |
| **[DevOps Automator](engineering-additional/devops-automator.md)** | CI/CD, infrastructure, deployment | Pipelines, Kubernetes, IaC, monitoring |
| **[Rapid Prototyper](engineering-additional/rapid-prototyper.md)** | Fast MVP development | Hackathons, proof-of-concepts, quick validation |

### Design

| Agent | Purpose | Best For |
|-------|---------|----------|
| **[UI Designer](design/ui-designer.md)** | Visual design, component libraries | Design systems, component specs, visual polish |
| **[UX Researcher](design/ux-researcher.md)** | User research, usability testing | User interviews, journey maps, research synthesis |

## Agent Collaboration Patterns

Agents are designed to work together in pipelines:

```
Bug Investigation → Fix
┌──────────┐     ┌──────────┐
│ DeepDive │ ──► │ DeepCode │
└──────────┘     └──────────┘
   (analyze)      (implement)

Security Audit → Remediation
┌───────────────┐     ┌──────────┐
│ Security      │ ──► │ DeepCode │
│ Scanner       │     └──────────┘
└───────────────┘

Full Design Pipeline
┌─────────────┐     ┌─────────────┐     ┌───────────────┐
│ UX          │ ──► │ UI          │ ──► │ Frontend      │
│ Researcher  │     │ Designer    │     │ Developer     │
└─────────────┘     └─────────────┘     └───────────────┘

Architecture → Implementation
┌─────────────┐     ┌─────────────────┐
│ Backend     │ ──► │ Clean Code      │
│ Architect   │     │ Architect       │
└─────────────┘     └─────────────────┘

Prototype → Production
┌─────────────┐     ┌─────────────────────────────────┐
│ Rapid       │ ──► │ Frontend Dev / Backend Architect│
│ Prototyper  │     └─────────────────────────────────┘
└─────────────┘
```

## Technology Coverage

### Backend
- **Languages:** C#, Python, Node.js, Go, Java, Rust
- **Frameworks:** .NET, Entity Framework Core
- **Databases:** SQL Server, PostgreSQL, MongoDB, Redis
- **Messaging:** RabbitMQ, Kafka, Azure Service Bus

### Frontend
- **Frameworks:** Angular, React, Vue, Svelte, Next.js
- **Styling:** Tailwind CSS, CSS Modules, Styled Components
- **Testing:** Jest, Playwright, Cypress

### DevOps
- **CI/CD:** Azure DevOps, GitHub Actions, GitLab CI
- **IaC:** Terraform, Pulumi, ARM/Bicep
- **Containers:** Docker, Kubernetes, Azure Container Apps
- **Cloud:** Azure, AWS, GCP

### Mobile
- **Cross-platform:** React Native, Flutter
- **Native:** SwiftUI, Kotlin/Compose

## Creating Custom Agents

Use the provided template to create new agents:

```bash
cp agent-template.md .claude/agents/your-domain/your-agent.md
```

See [agent-template.md](agent-template.md) for the full template structure.

## Project Structure

```
Agent-Collection/
├── engineering/                    # Core engineering agents
│   ├── clean-code-architect.md
│   ├── deepcode.md
│   ├── deepdive.md
│   └── security-vulnerability-scanner.md
├── engineering-additional/         # Specialist engineering agents
│   ├── ai-engineer.md
│   ├── backend-architect.md
│   ├── devops-automator.md
│   ├── frontend-developer.md
│   ├── mobile-app-builder.md
│   └── rapid-prototyper.md
├── design/                         # Design agents
│   ├── ui-designer.md
│   └── ux-researcher.md
├── agent-template.md               # Template for new agents
├── CLAUDE.md                       # Project configuration
└── README.md
```

## Recommended Setups by Project Type

### .NET + Angular Full-Stack

```markdown
## Recommended Agents
- Backend Architect — API design, EF Core, Azure services
- Frontend Developer — Angular components, RxJS, accessibility
- Clean Code Architect — C# best practices, SOLID principles
- DevOps Automator — Azure DevOps pipelines, ARM templates
- Security Vulnerability Scanner — OWASP compliance
```

### Startup/MVP

```markdown
## Recommended Agents
- Rapid Prototyper — Quick iteration, shipping fast
- Backend Architect — Scalable foundation
- UI Designer — Design system from day one
```

### Enterprise

```markdown
## Recommended Agents
- DeepDive — Analyze legacy code
- Backend Architect — Modern architecture planning
- Security Vulnerability Scanner — Compliance audit
- DevOps Automator — CI/CD modernization
```

## License

See [LICENSE](LICENSE) for details.
