---
title: How I Built an MCP Server for M-PESA in One Weekend
published: true
tags: mcp, python, africa, fintech
canonical_url: https://gabrielmahia.github.io
---

Kenya's M-PESA processes $314B annually. 35 million users. And until last year, there was no way for an AI agent to interact with it natively.

That changed when I built **mpesa-mcp** — a Model Context Protocol server that wraps the Daraja API and makes it directly available to Claude, GPT-4, and Gemini.

## What is MCP?

Model Context Protocol (MCP) is Anthropic's open standard for connecting AI agents to external tools. Think of it like REST for AI agents — instead of an LLM hallucinating what an API might return, it calls real tools with real data.

## The Problem

M-PESA's Daraja API is well-documented but non-trivial to integrate:
- OAuth 2.0 token flow with 1-hour expiry
- Request body includes base64-encoded password derived from shortcode + passkey + timestamp
- Different endpoints for STK push, B2C, balance, transaction status
- Sandbox vs production environment handling

For every developer building an AI assistant on M-PESA, this was ~2 days of integration work before writing a single line of product logic.

## The Solution: mpesa-mcp

```bash
pip install mpesa-mcp
claude mcp add mpesa -- mpesa-mcp
```

That's it. Your Claude instance can now:
- Initiate STK push payments
- Query account balances  
- Check transaction status
- Register C2B callback URLs

## How It Works

The server implements the MCP stdio protocol — it reads JSON-RPC messages from stdin and writes responses to stdout. Claude Code (or any MCP client) spawns it as a subprocess.

```python
def mcp_call_tool(name: str, arguments: dict) -> dict:
    if name == "mpesa_stk_push":
        return initiate_stk_push(
            phone=arguments["phone_number"],
            amount=arguments["amount"],
            account=arguments.get("account_reference", "Payment")
        )
```

## Results

- v0.1.9 on PyPI
- 400+ downloads across 12 countries
- Listed in awesome-mcp-servers
- First African payment API in the MCP ecosystem

## What's Next

mpesa-mcp v2.0 will add Swahili-native tool descriptions — so AI agents can receive instructions in Kiswahili and call M-PESA correctly. Part of the LINGUA Africa grant work.

GitHub: https://github.com/gabrielmahia/mpesa-mcp
