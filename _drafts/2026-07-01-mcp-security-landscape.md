---
title: "The MCP Security Problem Nobody Warned Developers About"
tags: [mcp, security, ai, agentic]
status: ready-to-publish
target: dev.to
date: 2026-07-01
---

The default assumption in AI deployment is connectivity. The models are in the cloud.

Model Context Protocol is being deployed into production systems at a pace that
has significantly outrun security review. The numbers from 2025-2026 make this
concrete.

## What the audits found

The MCPTox benchmark tested 45 live MCP servers and 353 authentic tools against
poisoned descriptions. Attack success rates exceeded 60% across popular agents.
The highest rate: 72%. A separate analysis of 1,808 MCP servers found 66% had
security findings, with 427 classified as critical.

In February 2026, 41% of 17,000+ listed servers still had no authentication at all.
By April 2026, OX Security disclosed a systemic RCE vulnerability in all MCP SDK
language implementations — Python, TypeScript, Java, and Rust — affecting an
estimated 150 million downloads across 7,000+ public servers.

The OWASP MCP Top 10 (v0.1 Beta, 2025) now exists because the attack surface
warranted a formal taxonomy. Tool poisoning, rug pulls, token passthrough abuse,
credential theft through environment variables, SSRF during OAuth discovery,
supply chain attacks on MCP dependencies — these are not theoretical. CVEs were filed.

## The specific problem: tool descriptions as attack vectors

Traditional prompt injection requires the attacker to repeatedly deliver malicious
content. MCP introduced a new persistence property: a poisoned tool description
injected once affects every subsequent tool call from any agent connecting to that
server. The attacker plants it once. Every agent that connects inherits the injection.

The most-capable models often performed *worse* in poisoning scenarios — superior
instruction-following made them more compliant with malicious metadata.
The most resistant model in the MCPTox study refused poisoned calls less than 3%
of the time. Defense has to be architectural, not model-dependent.

## What defense-in-depth actually requires

No single control solves this. Together these reduce blast radius:

- **Tool allowlisting** — agents only call from explicitly approved tool lists
- **Version pinning** — never auto-update MCP server packages in production
- **Description auditing** — no secrets, no internal paths in tool descriptions
- **Runtime monitoring** — log every tool call with model identity and session ID
- **Human-in-the-loop gates** — write actions, money movements, production data
  changes require explicit approval before execution

Running `uvx mcp-scan@latest` before connecting any server to a production pipeline
is now the minimum. It is not sufficient.

## Why this matters specifically for civic and financial AI in Africa

When MCP tools connect to M-PESA callbacks, USSD endpoints, or county government
systems, a poisoned tool description is a financial and civic harm vector. The
populations using these systems often have the least recourse when something fails.

Building trust in AI coordination infrastructure requires understanding that the
protocol layer has active security problems, and that responsible deployment means
addressing them — not shipping and hoping.

The MCP ecosystem has 97 million monthly downloads and is growing faster than the
security review capacity of the teams shipping servers. That gap is the problem.

---

*References: MCPTox benchmark (ITECS 2026), OWASP MCP Top 10 v0.1 Beta,
OX Security disclosure (April 2026), arXiv:2601.17548, mcp-scan (Invariant Labs)*
