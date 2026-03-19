---
title: "M-Pesa and Africa's Talking are missing from AI agent tooling — so I built the MCP server"
published: false
tags: africa, kenya, mcp, python, ai
canonical_url: https://dev.to/gabrielmahia/mpesa-mcp
cover_image: 
series: Building for East Africa
---

M-Pesa processes tens of millions of transactions a day. Africa's Talking reaches users across 20+ African countries via SMS and USSD on basic phones. Together they are the technical backbone of East African economic life.

Neither has an MCP server.

This means that every AI agent ecosystem — Claude, GPT, Gemini, and any MCP-compatible runtime — cannot trigger an M-Pesa payment or send a Kiswahili SMS without custom integration work per project, per team, per product.

`mpesa-mcp` closes that gap.

## What MCP is, briefly

Model Context Protocol is an open standard for connecting AI models to tools and data sources. If you use Claude Desktop or Claude Code, you've probably seen it — it's what lets an AI agent call real APIs on your behalf, not just describe what it would do.

The MCP ecosystem is growing fast. There are servers for GitHub, Slack, databases, web search. There is not one for the payment system used by 40M+ Kenyans.

## What the package does

Five tools:

```
mpesa_stk_push          — trigger a payment prompt on a customer's M-Pesa phone
mpesa_stk_query         — check whether a payment was completed
mpesa_transaction_status — look up any M-Pesa transaction by receipt number
sms_send                — send SMS to 1-1,000 recipients (Kenya, Nigeria, Ghana, Uganda, 20+ more)
airtime_send            — top up airtime for any subscriber on any supported network
```

## Install and run

```bash
pip install mpesa-mcp
# or: uvx mpesa-mcp
```

Add to Claude Desktop config:

```json
{
  "mcpServers": {
    "mpesa": {
      "command": "uvx",
      "args": ["mpesa-mcp"],
      "env": {
        "MPESA_CONSUMER_KEY": "...",
        "MPESA_CONSUMER_SECRET": "...",
        "MPESA_SHORTCODE": "174379",
        "MPESA_PASSKEY": "...",
        "MPESA_CALLBACK_URL": "https://yourapp.com/callback",
        "MPESA_SANDBOX": "true",
        "AT_USERNAME": "sandbox",
        "AT_API_KEY": "..."
      }
    }
  }
}
```

Then:

> "Send KES 500 STK Push to +254712345678 for order #1234"

The agent handles it. No code.

## What this unlocks in practice

**Field data collection.** An NGO running a survey across 50 wards can prompt:
> "Send KES 200 to each of these field agents when they submit their form"

**Farmer alerts.** A drought monitoring tool can:
> "SMS these 200 Garissa farmers that the Tana River level is rising. Top up KES 20 airtime each so they can call in."

**Support reconciliation.** A customer service agent can:
> "Check if receipt OKL8M3B2HF was a successful payment and for how much"

None of these required custom integration per use case. One server. Five tools.

## Why it's MIT licensed

Developer tools should be usable. If this lives behind a commercial licence nobody will use it. The applications built on top — M-Pesa connected products — can have whatever licence makes sense for them.

## The broader context

I've been building civic and community tools for Kenya and its diaspora for the past two years:
water stress monitoring, flood intelligence, civic rights AI, chama management, remittance comparison.
Every one of them eventually runs into the same set of infrastructure problems: M-Pesa integration,
Africa's Talking SMS, USSD menus, Kiswahili bilingual handling.

`mpesa-mcp` is the result of extracting the payment and communications layer into a reusable,
AI-agent-compatible form.

The full ecosystem is documented at [nairobi-stack](https://gabrielmahia.github.io/nairobi-stack).

---

**GitHub:** [gabrielmahia/mpesa-mcp](https://github.com/gabrielmahia/mpesa-mcp)  
**Install:** `pip install mpesa-mcp`  
**Docs:** [README](https://github.com/gabrielmahia/mpesa-mcp#readme)

Feedback welcome — especially from anyone already building on the East African stack.
