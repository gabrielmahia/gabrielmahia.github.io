# LinkedIn Content Series — 10 Posts

---
## POST 1 — mpesa-mcp launch story
The first time an AI agent called M-PESA was a weird Tuesday morning in Virginia.

I'd been building civic tech tools for Kenya for months — but they all had the same gap: they could explain how M-PESA works, but they couldn't DO anything with it.

So I built mpesa-mcp. A Model Context Protocol server that wraps Kenya's Daraja API. Now Claude can initiate an STK push, check a balance, or query a transaction status — natively, as a tool call.

Six months later: v0.1.9, PyPI, 400+ downloads, 12 countries.

First African payment API in the MCP ecosystem.

That weird Tuesday was worth it.
→ pip install mpesa-mcp

---
## POST 2 — The 110 repos story
I set out to build one AI tool for Kenya. One became ten. Ten became a hundred.

Today: 110+ open-source repositories covering:
💰 Financial inclusion (M-PESA, SACCOs, microfinance)
🏥 Health (medicine info, mental health, nutrition)
⚖️ Legal (Constitution RAG, document explainer, employment rights)
🌾 Agriculture (crop disease, livestock, markets)
📚 Education (KCSE tutoring, Swahili translation)
🏠 Housing, transport, trade, environment
👥 Youth employment, refugees, emergency response

All in Kiswahili. All open-source. All deployable today.

The goal was never 110 repos. The goal was: every Kenyan with a smartphone should have access to the same information quality that any American with internet access has.

We're getting there.
→ gabrielmahia.github.io

---
## POST 3 — Why Swahili matters technically
GPT-4 makes 4× more errors in Swahili than in English.

Not because Swahili is harder. Because Swahili represents ~0.1% of Common Crawl while English represents ~50%.

The result: every AI assistant built for Kenya runs on a model that's seen 500× more English training data than Swahili. In financial and civic domains — where precision matters — that's not a small gap.

This is why every tool I build starts with Swahili, not with English translation. And why the LINGUA Africa grant (Microsoft AI for Good Lab × Gates Foundation × Masakhane) targets 100,000+ labeled Swahili sentences for model fine-tuning.

Technical problem. Solvable with data and engineering.

---
## POST 4 — The protocol trifecta
MCP. A2A. Google ADK.

Three competing AI agent protocols. Most developers picked one. I implemented all three — for East Africa.

MCP: wraps Kenya's APIs (M-PESA, DHIS2, KRA eTims) as tool calls
A2A: multi-agent coordination for civic monitoring
ADK: complex Swahili advisory pipelines

First documented implementation of all three for the region. That positioning matters — when the ecosystem converges on a standard, East Africa's infrastructure is already there, already battle-tested, already open-source.

First-mover in protocols. Not just in products.

---
## POST 5 — dawa-ai story
50% of Kenyans self-medicate.

Drug package inserts are in English. Pharmacists are scarce in rural areas. Drug interaction information requires a medical degree to interpret.

So we built dawa-ai.

Type the name of any medicine. Get:
- What it does
- How to take it  
- What it interacts with
- A cheaper generic alternative
- When to go to the hospital immediately

In Swahili. Free. On your phone.

WebMD exists for Americans. dawa-ai exists for Kenyans.
→ github.com/gabrielmahia/dawa-ai

---
## POST 6 — The Jua Kali angle
3 million Jua Kali artisans in Kenya generate KES 500B+ annually.

They have no business bank accounts. No digital registration. No access to formal supply chains or government contracts. Not because they lack skills — because the formalization process is opaque, expensive, and conducted in English.

jua-kali-ai changes that.

KIE registration, NITA certification, cooperative formation, export market guidance — all in Swahili, all step-by-step.

The informal economy isn't informal by choice. Sometimes all it takes is the right information in the right language.

---
## POST 7 — Land fraud angle (nyumba-ai)
Kenya loses KES 10B+ per year to land fraud.

Double-titling. Ghost sellers. Fraudulent transfer documents. It's a documented epidemic that ruins families and takes years to resolve in court.

nyumba-ai helps you:
- Verify a title deed before purchasing
- Understand your tenant rights
- Identify red flags in a transaction
- Know when to walk away

The tools to protect yourself from land fraud have always existed — in legal offices, in English. nyumba-ai puts them in Swahili, on your phone, before you sign anything.

---
## POST 8 — Grant application angle
Currently applying to LINGUA Africa — Microsoft AI for Good Lab × Gates Foundation × Masakhane Hub. Up to $250,000 + $400,000 in compute credits.

The application covers:
- Scaling swahili-civic-nlp to 100,000+ labeled pairs
- Fine-tuning Aya-101 (13B) on Kenya financial, civic, and educational domains
- Community evaluation with real M-PESA agents, students, and civic journalists

But the tools don't wait for the grant. 110 repos are already live.

The grant would let us do it at the scale that matches the problem.

---
## POST 9 — wakimbizi-ai angle
Kenya hosts 560,000 registered refugees.

Most don't know their legal rights under the Refugee Act 2021. Most don't know which NGOs offer free legal aid. Most don't know how to navigate the UNHCR registration process.

wakimbizi-ai provides:
- UNHCR registration guidance
- Refugee Act rights explained
- NGO services directory (DRC, IRC, NRC, Kituo cha Sheria)
- Legal aid contacts

Nobody else built this. So we did.

---
## POST 10 — The mission statement
What Alexander did with territory, I'm doing with technology.

A strategic position in every critical domain — financial, health, legal, civic, agricultural, educational, environmental, housing, transport, trade, mental health, refugee services, informal sector.

All interconnected. All in Swahili. All open-source. All verifiable.

110+ repos on GitHub. 4 datasets on HuggingFace. Live on PyPI.

The mission: every Kenyan, regardless of language or geography, should have access to the same quality of AI-powered information that any English speaker in a wealthy country takes for granted.

We're building that. One tool at a time.
→ gabrielmahia.github.io
