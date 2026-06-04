---
title: All Three AI Agent Protocols for East Africa — MCP, A2A, Google ADK
published: true
tags: mcp, ai-agents, a2a, google-adk
canonical_url: https://gabrielmahia.github.io
---

In 2024-2025, three competing AI agent protocols emerged:

1. **MCP** (Model Context Protocol) — Anthropic's standard for tools and data sources
2. **A2A** (Agent-to-Agent) — Google/industry standard for agent-to-agent communication
3. **Google ADK** (Agent Development Kit) — Google's framework for building agent pipelines

Every major AI lab bet on one. Most developers implemented one or two. I implemented all three — for East Africa.

## Why All Three?

The honest answer: because the ecosystem will converge, and first-mover implementations are valuable regardless of which protocol wins. Being the reference implementation for East Africa on all three means the community's AI infrastructure isn't locked into any single vendor's choices.

The strategic answer: each protocol solves a different problem.

- **MCP** is best for wrapping existing APIs (M-PESA, DHIS2, KRA eTims) as tool calls
- **A2A** is best for multi-agent coordination (civic monitoring that involves health + legal + financial agents working together)
- **ADK** is best for complex pipelines with evaluation and observability

## What Was Built

### mpesa-mcp (MCP)
```bash
pip install mpesa-mcp
claude mcp add mpesa -- mpesa-mcp
```
First M-PESA MCP server. 400+ PyPI downloads across 12 countries.

### kenya-a2a (A2A)
Multi-agent coordination for Kenya civic AI. Agents communicate about government service queries, budget analysis, and accountability monitoring using the A2A protocol.

### kenya-adk (Google ADK)
Swahili-native agent pipelines using Google's ADK. Financial advisory agents that can call M-PESA tools, query legal documents, and return Swahili responses.

## The Pattern

All three follow the same architecture:
1. Kenya-specific knowledge is embedded in agent descriptions (not system prompts)
2. Tools are domain-specific: M-PESA, KHIS, Kenya legal corpus
3. All tool descriptions are written in Kiswahili so agents can receive Swahili instructions
4. DEMO vs REAL data is always clearly labeled

## Current Status

All three are live and open-source under MIT license. The next phase is Swahili model fine-tuning that makes the agents genuinely first-language capable — part of the LINGUA Africa grant work targeting 100,000+ labeled Swahili training pairs.

GitHub: https://github.com/gabrielmahia
MCP Hub: https://github.com/gabrielmahia/kenya-mcp-hub
