# AGENTS.md — gabrielmahia.github.io

<!-- coverage-adaptive-reasoning:v2 -->

## What this is
Gabriel Mahia — building decision infrastructure for under-resourced systems.

## Read first
- README.md
- agent-context.json
- Portfolio reasoning standard: https://github.com/gabrielmahia/nairobi-stack/blob/main/docs/COVERAGE_ADAPTIVE_REASONING.md

## Critical rules
- Static portfolio site: claims (counts, tool names, dates) must match live sources; the weekly freshness audit in nature-ai-evolution-lab checks them. Use lower bounds ('30+') for counts.

## Coverage-Adaptive Reasoning v2

For consequential research, recommendations, investigations, analogy searches, forecasting, opportunity discovery, and canon building:

- A correct ranking inside an incomplete universe is still a failed answer.
- Separate candidate generation from candidate ranking.
- Materiality-gate the search: use the minimum useful set of orthogonal retrieval routes that could change the answer.
- Before closure ask what correct answer the current search method would be structurally incapable of finding.
- Treat aliases, language/geography, era, source class, format, genealogy, taxonomy, legal identity vs operational control/economic benefit, intermediaries, schema categories, null/failure cases, and negative space as potential blind spots when material.
- Maintain leading + competing + null explanations.
- Distinguish answer confidence from coverage confidence.
- “Nothing found” is not evidence of absence when coverage is low.
- Stop when additional independent search routes no longer materially change the candidate universe, hypotheses, decision, or next test.
- When an important miss occurs, repair the retrieval architecture via MISS → SENSOR REDESIGN; do not merely append the missed example.

## Multi-agent protocol
- Git is the memory bus.
- Read Issues and open/draft PRs before starting.
- Work from an Issue.
- Branch: `agent/<agent>/<issue>-<slug>`
- Open a draft PR immediately to claim scope.
- If another PR overlaps, review/subdivide rather than duplicate.
- Leave tests + handoff in Git.

## Commands
```bash
# test
n/a (static site; links and claims are checked by the freshness audit)
```

## Never autonomously
- change licensing
- expose credentials
- perform irreversible external actions
