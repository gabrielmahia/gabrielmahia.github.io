# Research Foundation

The East Africa coordination stack is informed by peer-reviewed research and
publicly available data. This page documents the academic and institutional
sources that shape architectural decisions across the portfolio.

---

## Multi-Agent Coordination

**arXiv:2601.11595** (Jayanti et al., January 2026)  
*Enhancing MCP with Context-Aware Server Collaboration*  
CA-MCP introduces a Shared Context Store (SCS) that reduces LLM calls and
response failures in multi-server workflows. Validates the event bus coordination
architecture used in `africa-coord-bus`.

**arXiv:2504.21030** (Krishnan, 2025)  
*Advancing Multi-Agent Systems Through Model Context Protocol*  
Identifies the "disconnected models problem" — stateless MCP servers lack global
context. Coordination buses are structurally necessary for multi-domain agents.

**arXiv:2602.15055** (2026)  
*Beyond Context Sharing: A Unified ACP for Secure, Federated A2A Orchestration*  
A2A/ACP convergence under Linux Foundation AAIF (December 2025). Informs
protocol compatibility decisions across `africa-coord-bus`, `kenya-a2a`.

---

## MCP Security

**MCPTox Benchmark** (ITECS, 2025-2026)  
45 live MCP servers tested: attack success rates >60%, highest 72%.  
Claude-3.7-Sonnet/Sonnet 5 most resistant (<3% compliance with poisoned calls).  
Validates model selection in `ops-shield` and agent routing design.

**arXiv:2601.17548** (January 2026)  
*Prompt Injection Attacks on Agentic Coding Assistants*  
78 studies synthesized, 42 attack techniques. Multi-layer defenses reduce
attacks from 73.2% to 8.7%. Architecture basis for ops-shield defense design.

**OWASP MCP Top 10** (v0.1 Beta, 2025)  
Standard security framework for MCP deployments. Used as deployment checklist
across all 31 MCP servers in this portfolio.

---

## African NLP & Language AI

**AfricaNLP 2025/2026 Workshop Proceedings**  
Only 4 African languages receive consistent NLP support (Amharic, Swahili,
Afrikaans, Malagasy). 98%+ of African languages have no AI coverage.
Civic and healthcare domains have the most critical accuracy requirements
and the most data gaps. Frames the strategic value of `swahili-civic-nlp`.

**Hussen et al., arXiv:2506.02280** (2025)  
*The State of LLMs for African Languages: Progress and Challenges*  
Systematic assessment of LLM capability across African languages. Documents
the inequality and the scale of the gap.

---

## Offline-First AI

**arXiv:2603.03339** (2026)  
*Offline-First LLM Architecture for Adaptive Learning in Low-Connectivity Environments*  
Validates hardware-aware model selection and local-first inference for
bandwidth-constrained environments. Design basis for `offline-mcp`.

---

## Agricultural AI

**AgriIR** (Springer 2026)  
Configurable RAG framework for agricultural knowledge retrieval. Validates
domain-specific retrieval approach used in `kilimo-mcp` + `shamba`.

**arXiv:2401.08406** (2024)  
*RAG vs Fine-tuning: A Case Study on Agriculture*  
RAG outperforms fine-tuning for dynamic agricultural knowledge.
Supports data-first architecture across agricultural coordination tools.

---

## Financial Inclusion & AI

**Springer Nature, 2025**  
*AI for Financial Inclusion and Sustainable Development: A Systematic Review*  
70 peer-reviewed studies (2017-2025). Confirms AI transformative potential for
financial inclusion with the caveat: requires ethical safeguards and contextual
understanding. Frames the responsible design requirements across `mpesa-mcp`,
`mkopo-mcp`, `faida-mcp`.

---

## DPGA & Digital Public Infrastructure

**DPGA 2025 DPG Ecosystem Report**  
DPG Standard updated 2025 to include AI systems. 2026 focus: sourcing AI DPGs
for SDG-relevant domains including agriculture and climate. Directly informs
`mpesa-mcp` (GID0093741), `swahili-civic-nlp` (GID0093743) submissions.

**Stanford HAI 2026 AI Index**  
AI agent deployment still in single digits across business functions globally.
70% of organizations use genAI in at least one function. US AI adoption: 28.3%
(ranked 24th). East Africa coordination stack is infrastructure-layer work
in a world where agentic deployment is just beginning.

**World Bank Digital Public Infrastructure White Paper** (2025)  
Documents Kenya Big Data Platform for agriculture, DPI for financial inclusion,
and lessons from India AgriStack. Frames the institutional context for
coordination infrastructure.

---

*This page is updated as new research informs the portfolio. Last updated: July 1, 2026.*
