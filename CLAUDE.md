# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository implements a multi-agent development team framework for building SaaS products. It uses Claude Code's agent system to coordinate specialized AI agents that work together on different aspects of product development.

## Agent Architecture

The system is built around five specialized agents located in `.claude/agents/`:

1. **saas-architect** (red) - Defines system architecture, technology stack, security protocols, and scalability design
2. **backend-lead-engineer** (blue) - Designs APIs, database schemas, server-side logic, and third-party integrations
3. **frontend-lead-engineer** (green) - Designs frontend architecture, component libraries, and state management
4. **ui-ux-designer** (yellow) - Creates user research, wireframes, mockups, and design specifications
5. **development-team-lead** (purple) - Orchestrates the development process, sprint planning, and team coordination

### Agent Workflow

The agents follow a hierarchical workflow:
- **saas-architect** creates the architectural blueprint first
- **backend-lead-engineer** and **frontend-lead-engineer** work from this blueprint
- **ui-ux-designer** collaborates with frontend-lead-engineer on interface design
- **development-team-lead** synthesizes all outputs into a cohesive project plan

## Working with Agents

To invoke an agent for a specific task, use the Task tool with the appropriate `subagent_type`:

```
Task tool with subagent_type: "saas-architect"
Task tool with subagent_type: "backend-lead-engineer"
Task tool with subagent_type: "frontend-lead-engineer"
Task tool with subagent_type: "ui-ux-designer"
Task tool with subagent_type: "development-team-lead"
```

### Agent Coordination

When working on a new SaaS product:
1. Start with saas-architect for overall system design
2. Parallelize backend-lead-engineer, frontend-lead-engineer, and ui-ux-designer tasks when possible
3. Use development-team-lead to create the final integrated plan and manage execution

## Key Principles

- Agents can be run in parallel when there are no dependencies
- Each agent produces outputs that feed into subsequent phases
- The system is designed for greenfield SaaS product development
- All agents use the sonnet model for consistency
