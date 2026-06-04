# Product Hunt Submission — mpesa-mcp

## Tagline
M-PESA Daraja API as MCP tools — the first African payment API for AI agents

## Description
mpesa-mcp is a Model Context Protocol server that wraps Kenya's M-PESA Daraja API, enabling any AI agent (Claude, GPT-4, Gemini) to initiate M-PESA payments, check balances, and query transaction status natively — without custom API integration.

**Why it matters:**
- M-PESA processes $314B+ annually (50%+ of Kenya's GDP flows through it)
- 35M+ registered users across 7 East African countries
- Before mpesa-mcp, building AI agents on M-PESA required understanding the full OAuth + SOAP/REST hybrid API. Now it's `claude mcp add mpesa -- mpesa-mcp`

**Tools included:**
- `mpesa_stk_push` — Lipa Na M-PESA payment initiation
- `mpesa_b2c` — Business-to-customer disbursements  
- `mpesa_balance` — Account balance query
- `mpesa_transaction_status` — Transaction confirmation
- `mpesa_register_url` — C2B callback registration

**What makes this different:**
First African financial infrastructure in the MCP ecosystem. Available as a PyPI package (pip install mpesa-mcp). MIT licensed.

## Links
- GitHub: https://github.com/gabrielmahia/mpesa-mcp
- PyPI: https://pypi.org/project/mpesa-mcp/
- Portfolio: https://gabrielmahia.github.io

## Maker tagline
Building AI infrastructure for 47 million Swahili speakers. One protocol at a time.
