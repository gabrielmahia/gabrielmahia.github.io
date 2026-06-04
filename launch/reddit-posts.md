# Reddit Posts — Ready to Post

## r/MachineLearning — [D] Cross-lingual RAG for East African civic AI — implementation notes and results

I've been building a portfolio of Swahili-language AI tools for Kenya (110+ tools total) and wanted to share implementation notes on cross-lingual RAG for low-resource language settings.

**The problem:** Kenya's civic documents (Constitution, Employment Act, county budgets) are in English. Users query in Swahili. General-purpose models hallucinate when asked about Kenyan-specific legal/civic concepts.

**The approach:** Domain-specific system prompts embedding Kenyan institutional knowledge + RAG over legal documents + Gemini Flash (lowest cost, adequate for this domain).

**Key finding:** For civic/financial domains, domain-specific prompting mattered more than model size. A well-prompted Gemini Flash with Kenyan context outperformed GPT-4-turbo with a generic system prompt on KCSE and Employment Act QA tasks.

**Dataset:** swahili-civic-nlp on HuggingFace (gmahia). Expanding via LINGUA Africa grant application.

Repos: github.com/gabrielmahia/kenya-legal-rag and github.com/gabrielmahia/kenya-rag

Happy to share specific prompting approaches or evaluation methodology.

---
## r/Kenya — AI tools for Kenya built in Swahili — free, open-source

Nimekuwa nikijengea Kenya zana za AI katika Kiswahili — zote bure na open-source.

Zana zilizopo:
- shamba-ai: Mshauri wa kilimo (ugonjwa wa mazao, bei za soko, hali ya hewa)
- dawa-ai: Habari za dawa kwa Kiswahili (mwingiliano, kipimo, mbadala wa bei nafuu)
- hati-ai: Eleza hati yoyote ya serikali kwa Kiswahili
- bajeti-ai: Fuatilia bajeti ya kaunti yako
- ajira-ai: CV, mahojiano, gig economy kwa vijana

Na zaidi ya 100 zana nyingine.

Zote: gabrielmahia.github.io

Niambie — ni zana gani ungependa zaidi? Ninafanya kazi ya LINGUA Africa grant kwa Microsoft/Gates/Masakhane kuongeza data ya Kiswahili.

---
## r/devops — Running 110 Streamlit apps at zero infra cost — architecture notes

**tl;dr:** 110 Streamlit apps, all deployed, total infra cost $0/month. Here's how.

Stack:
- Streamlit Cloud free tier (each app = separate repo, 1GB RAM, shared CPU)
- Gemini Flash via raw urllib.request (no SDK = smaller deployment, faster cold starts)
- sys.path.insert for local package imports (no pip install in app.py)
- Secrets via Streamlit secrets.toml (not env vars)
- GitHub as effective CDN for all static assets

The key architectural decision: no shared infrastructure. Each app is fully self-contained. This creates redundancy (each app re-implements the API call pattern) but eliminates shared failure modes.

For a portfolio-as-product approach (building many small tools rather than one big platform), this works better than a monolith. The 111th app is as easy to deploy as the first.

Repo: github.com/gabrielmahia
