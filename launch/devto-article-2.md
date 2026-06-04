---
title: Why Swahili AI Fails — And How We're Fixing It
published: true
tags: nlp, africa, swahili, llm
canonical_url: https://gabrielmahia.github.io
---

A 2025 benchmark study (arXiv:2509.04516) confirmed what East African AI developers already knew: general-purpose language models produce **4× more errors** when reasoning in Swahili compared to English — even for simple factual tasks.

The cause isn't a mystery. Common Crawl, the primary pre-training corpus for most LLMs, is ~50% English and ~0.1% Swahili. Models don't fail at Swahili because Swahili is hard — they fail because they've never seen enough of it.

## The Compounding Problem

For civic and financial AI in Kenya, the problem compounds. It's not just that Swahili is underrepresented — it's that Kenyan-specific concepts have essentially zero representation:

- M-PESA paybill codes and USSD flows
- KCSE exam structure and grading
- County government (devolution) procedures
- Kenya Revenue Authority eTims compliance
- Land registry and title deed formats

Ask GPT-4 how to troubleshoot a failed M-PESA B2C payment in Swahili. You'll get plausible-sounding text that describes a payment flow that doesn't match how Daraja actually works.

## What We're Building

The East Africa AI portfolio (110+ tools) is built on three principles:

**1. Domain-specific knowledge, not just translation**
Every tool is built with Kenyan institutional context embedded in the system prompt. The model knows what a paybill code is, what KCSE stands for, what the Employment Act says about notice periods.

**2. Swahili as first language, not afterthought**
All user-facing text is written in Swahili. Not translated — written. There's a difference: "Angalia salio la M-PESA" is not a translation of "Check M-PESA balance" — it's the phrase a Kenyan would actually use.

**3. MCP infrastructure as multiplier**
By wrapping Kenya's APIs as MCP servers (mpesa-mcp, wapimaji-mcp, swahili-health-mcp, kenya-legal-rag), we create a layer where any AI agent inherits domain knowledge without re-implementing it.

## The Data Problem

The long-term fix is better training data. That's what the LINGUA Africa grant application targets: 100,000+ labeled Swahili sentences in financial, civic, and educational domains, followed by LoRA fine-tuning of Aya-101.

The short-term fix is already deployed: 110 tools, running today, serving real users in Swahili.

GitHub: https://github.com/gabrielmahia
