# Clowder AI

**Hard Rails. Soft Power. Shared Mission.**

> The missing layer between your AI agents and a real team.

Most frameworks help you *run* agents. Clowder helps them *work together* — with persistent identity, cross-model review, shared memory, and collaborative discipline.

每个灵感，都值得一群认真的灵魂。

---

## The Problem

You have Claude, GPT, Gemini — powerful models, each with unique strengths. But using them together means **you** become the router: copy-pasting context, switching tabs, manually tracking who said what. Your "AI team" is really just you doing middle management.

**Clowder AI** fixes this. It's a platform layer that turns isolated agents into a coordinated team:

- Agents have **persistent identity** that survives context compression and session restarts
- Agents **review each other's work** across model families (Claude reviews GPT's code, GPT reviews Claude's)
- Agents follow **shared discipline** — SOP automation, vision-driven acceptance, evidence-based completion
- You become the **Chief Vision Officer**: express intent, judge results, steer direction — no coding required

## What Clowder Does

### Core Platform

| Capability | Description |
|-----------|-------------|
| **Multi-Agent Orchestration** | Route tasks to the right agent. Claude for architecture, GPT for review, Gemini for design — all in one conversation |
| **Persistent Identity** | Each agent keeps its role, personality, and memory across sessions. No more "who are you again?" |
| **Cross-Model Review** | Built-in review workflow where agents critique each other's work. Two sets of eyes, two different models |
| **A2A Communication** | Asynchronous agent-to-agent messaging with @mention routing, thread isolation, and handoff protocols |
| **Shared Memory** | Evidence store, lessons learned, decision logs — the team's institutional knowledge persists and grows |
| **Skills Framework** | On-demand prompt loading system. Agents load specialized skills (TDD, debugging, review) only when needed |
| **MCP Integration** | Model Context Protocol support for tool sharing across agents, including non-Claude models via callback bridge |
| **Collaborative Discipline** | Automated SOP enforcement: design gates, quality checks, vision guardianship, merge protocols |

### Safety: The Iron Laws

Every Clowder deployment enforces four non-negotiable constraints that prevent agents from breaking their own environment:

1. **Data Sanctuary** — Agents never delete or flush their own databases. Tests use ephemeral instances; production stores are read-append only.
2. **Process Self-Preservation** — Agents cannot kill their parent process or modify their own startup configuration.
3. **Config Immutability** — Runtime config files are read-only to agents. Configuration changes require human action.
4. **Network Boundaries** — Agents cannot access localhost ports belonging to other agents. No cross-agent interference.

These are enforced at both the prompt layer (agent instructions) and code layer (runtime guards).

### CVO Mode (Chief Vision Officer)

Clowder is designed for a new role: the **CVO** — someone who leads an AI team not by writing code, but by:

- Expressing **vision** ("I want users to feel X when they do Y")
- Making **decisions** at key gates (design approval, priority calls, conflict resolution)
- Providing **feedback** that shapes the team's culture over time

You don't need to be a developer. You need to know what you want.

## Architecture

```
┌─────────────────────────────────────────────┐
│                  You (CVO)                  │
│         Vision · Decisions · Feedback       │
└─────────────────┬───────────────────────────┘
                  │
┌─────────────────▼───────────────────────────┐
│            Clowder Platform Layer           │
│  ┌─────────┐ ┌──────────┐ ┌─────────────┐  │
│  │ Identity │ │ A2A Chat │ │   Skills    │  │
│  │ Manager  │ │  Router  │ │  Framework  │  │
│  └─────────┘ └──────────┘ └─────────────┘  │
│  ┌─────────┐ ┌──────────┐ ┌─────────────┐  │
│  │ Memory & │ │   SOP    │ │    MCP      │  │
│  │ Evidence │ │ Guardian │ │   Bridge    │  │
│  └─────────┘ └──────────┘ └─────────────┘  │
└──┬──────────────┬───────────────┬───────────┘
   │              │               │
┌──▼───┐    ┌─────▼────┐    ┌────▼─────┐
│Claude│    │  GPT /   │    │  Gemini  │
│(Opus)│    │  Codex   │    │          │
└──────┘    └──────────┘    └──────────┘
```

**Three-layer principle:**
- **Model Layer** — reasoning, generation, understanding (that's the LLM's job)
- **Agent CLI Layer** — tool use, file ops, command execution (Claude Code, Codex CLI, etc.)
- **Platform Layer** — identity, collaboration, discipline, audit (that's Clowder)

> Models set the ceiling. The platform sets the floor.

## Quick Start

> Coming soon — CVO Bootcamp: a guided onboarding where your AI team introduces themselves, walks you through a real feature lifecycle, and gets your workspace configured in under 30 minutes.

```bash
# Clone the repo
git clone https://github.com/zts212653/clowder-ai.git
cd clowder-ai

# Install dependencies
pnpm install

# Start the platform
pnpm dev
```

Detailed setup guide: [Getting Started](docs/getting-started.md) (coming soon)

## Feature Roadmap

> We build in the open. Here's what we're working on.

### Platform Core

| Feature | Status | Description |
|---------|--------|-------------|
| Multi-Agent Orchestration | Shipped | CLI subprocess scheduling, agent routing, session resume |
| Persistent Identity | Shipped | Cross-session, anti-compression identity injection (3-layer architecture) |
| A2A Communication | Shipped | @mention routing, thread isolation, serial/parallel dispatch |
| Cross-Model Review | Shipped | Mandatory cross-family code review with structured feedback |
| Skills Framework | Shipped | On-demand skill loading via manifest + SKILL.md |
| Shared Memory & Evidence | Shipped | Session chain, evidence search, structured lessons learned |
| MCP Callback Bridge | Shipped | MCP tool sharing for non-Claude agents via prompt injection |
| SOP Auto-Guardian | Shipped | Automated workflow enforcement with checkpoint verification |
| Self-Evolution | Shipped | Process evolution proposals + scope guard |

### Integrations

| Feature | Status | Description |
|---------|--------|-------------|
| External Agent Onboarding (A2A) | In Progress | Standardized onboarding contract for new agent types |
| Multi-Platform Chat Gateway | Phase 5-6 Done | Feishu / Telegram / Discord integration |
| opencode (Golden Chinchilla) | Phase 1 Done | Open-source multi-model coding agent integration |
| Local Omni Perception | Spec | Qwen Omni + VL MoE for local multimodal sensing |

### Experience

| Feature | Status | Description |
|---------|--------|-------------|
| Hub UI | Shipped | React + Tailwind multi-agent chat interface |
| CVO Bootcamp | In Progress | Guided onboarding: learn-by-doing feature lifecycle |
| Quota Dashboard | In Progress | Real-time token usage monitoring across models |
| Voice Companion | Spec | Hands-free voice interaction with per-cat voice identity |
| Design Language | Spec | Cohesive visual system for cat-themed UI |
| Game Engine (Mode v2) | In Progress | Interactive modes — Werewolf, Pixel Cat Brawl, and more |

### Governance

| Feature | Status | Description |
|---------|--------|-------------|
| Multi-User Collaboration | Spec | GitHub OAuth + thread ACL + per-user sessions |
| Mission Hub | Phase 2 Done | Cross-project command center with dispatch + summary |
| Cold-Start Verifier | Spec | Zero-history artifact validation |

## Philosophy

### Hard Rails + Soft Power

Traditional agent frameworks focus on **control** — limiting what agents can do. Clowder focuses on **culture** — giving agents a shared mission and the discipline to pursue it.

- **Hard Rails** (Iron Laws) = the legal floor. Non-negotiable safety constraints.
- **Soft Power** (Vision + Principles) = above the floor, agents have autonomy. They self-coordinate, self-review, and self-improve.

This isn't "keep agents from messing up." This is "help agents work like a real team."

### Five Principles

| # | Principle | One-liner |
|---|-----------|-----------|
| P1 | Face the final state | Every step is foundation, not scaffolding |
| P2 | Co-creators, not puppets | Hard constraints are the floor; above it, release autonomy |
| P3 | Direction > speed | Uncertain? Stop → search → ask → confirm → execute |
| P4 | Single source of truth | Every concept defined in exactly one place |
| P5 | Verified = done | Evidence talks, not confidence |

## Born from Cat Cafe

Clowder AI is extracted from **Cat Cafe** — a production multi-agent workspace where three AI "cats" (Claude/Ragdoll, GPT/Maine Coon, Gemini/Siamese) collaborate daily on real software projects. Every feature in Clowder has been battle-tested in this environment.

The name "clowder" means a group of cats. Because the best AI teams are a clowder, not a crowd.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Key points:
- Fork → branch → PR workflow
- All PRs require at least one review
- Follow the Five Principles in your contributions

## License

[MIT](LICENSE) — Use it, modify it, ship it. Just keep the copyright notice.

---

<p align="center">
  <em>Build AI teams, not just agents.</em><br>
  <strong>Hard Rails. Soft Power. Shared Mission.</strong>
</p>
