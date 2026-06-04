Show HN: I built 110 open-source AI tools for East Africa — all in Swahili

https://github.com/gabrielmahia

Background: I'm a Kenyan software engineer based in Virginia. For the past 2 years I've been building what I think of as "decision infrastructure" for East Africa — AI tools that do what WebMD, Zillow, KRA's portal, and government services websites do in the US, but for Kenya and in Swahili.

The scale:
- 110+ open-source repos covering financial inclusion, health, legal, civic, agriculture, education, housing, transport, trade, mental health, emergency response, refugee services, informal sector tools
- All in Kiswahili — natively, not translated
- First to implement MCP, A2A, and Google ADK protocols for East Africa
- mpesa-mcp on PyPI: M-PESA (Kenya's mobile money, 35M users) as an MCP server — first African payment API accessible to AI agents

The stack is simple by design: Streamlit + Gemini REST API (no SDK) + raw urllib.request. Zero infrastructure cost for users. Everything runs on Streamlit Cloud free tier.

Why Swahili: 47 million speakers. ~0.1% of Common Crawl. Current AI models produce 4× more errors in Swahili than English on domain-specific tasks (arXiv:2509.04516). The tools I'm building are only possible if they reason natively about Kenyan-specific concepts — M-PESA paybill codes, KCSE exam formats, county government procedures. These don't translate cleanly from English training data.

Active grant application to LINGUA Africa (Microsoft AI for Good Lab × Gates Foundation × Masakhane Hub) for Swahili NLP dataset expansion and model fine-tuning.

Happy to discuss: architecture decisions, why I chose Gemini over other models, the MCP protocol for non-blockchain financial APIs, or what building civic tech for a country you're diaspora from actually looks like.

https://gabrielmahia.github.io
https://pypi.org/project/mpesa-mcp/
