# Flavio

I build AI products for large organisations: start from the people who do the work, decide what
to build and what to leave out, and prove with evidence whether it worked. Here are four product
MVPs, each taken from discovery to a pilot a team could run, and the governed AI platform they run
on, measured and able to run entirely on an organisation's own infrastructure.

## Start here: ten minutes on the product work

1. **Evidence overturning a sponsor's priority:** feedback-to-roadmap's
   [worked example](https://github.com/flam7791/feedback-to-roadmap/blob/main/docs/product/07-worked-example.md)
   counts feedback in people, not rows, and moves the sponsor's top item to fourth of eight.
2. **Decision rules fixed before the pilot:** ai-adoption-tracker's
   [PRD](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/02-prd.md) and
   [decision log](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/06-decision-log.md),
   with committee overrides recorded, not hidden.
3. **A process redesigned AI-first, with its investment case:** agentic-procurement-intake's
   [service blueprint](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/02-service-blueprint.md)
   and [build, buy, reuse or stop case](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/03-options-and-investment-case.md).
4. **A weak result published, not patched:** obligations-register's
   [held-out evaluation](https://github.com/flam7791/obligations-register/blob/main/eval/EVALS.md).

## Four product MVPs

Hypotheses and non-goals are written before any code, pilot decision rules before launch, and
each repository ships a team pack (brief and RACI, backlog, iteration plan) with CI failing if a
story marked Done has no test proving it.

| Product | The problem, and for whom |
|---|---|
| [feedback-to-roadmap](https://github.com/flam7791/feedback-to-roadmap) | The product owner of an internal AI assistant, prioritising by whoever argued best in the last meeting. It counts people across four channels and proposes explained roadmap changes; the product owner decides |
| [ai-adoption-tracker](https://github.com/flam7791/ai-adoption-tracker) | An AI review committee with a dozen pilots and no comparable view of use and value. It recommends scale, iterate or stop, showing every check; the committee decides |
| [agentic-procurement-intake](https://github.com/flam7791/agentic-procurement-intake) | Staff and procurement officers losing weeks between a need and an approvable request. An agent prepares the package; people confirm, approve and sign off, enforced in code |
| [obligations-register](https://github.com/flam7791/obligations-register) | Teams tracking contract obligations late or by hand. A draft register in which every line is the exact source sentence; anything uncertain goes to a review queue |

The four share one event format, so the tracker's scale-or-stop reviews rest on the others' usage.

## The platform underneath

[ai-engineering-framework](https://github.com/flam7791/ai-engineering-framework) makes governed
AI repeatable: a use-case intake that recommends a pattern, seven solution patterns with working
reference implementations, engineering standards checked in CI, and a local-first service template.
The reference implementations:

- [governed-llm-gateway](https://github.com/flam7791/governed-llm-gateway): one door to every
  model (Claude, Azure OpenAI, Mistral AI or local), routed by cost within each team's data policy
  and budget, personal data masked, chargeback without storing content
- [governed-agents](https://github.com/flam7791/governed-agents): a multi-agent runtime where a
  policy engine decides every tool call, with four-eyes approval for external actions and an audit trail
- [policy-evidence-mcp](https://github.com/flam7791/policy-evidence-mcp),
  [reference-resolver-agent](https://github.com/flam7791/reference-resolver-agent),
  [oecd-data-pipeline](https://github.com/flam7791/oecd-data-pipeline) and
  [copilot-team-knowledge](https://github.com/flam7791/copilot-team-knowledge): cited retrieval,
  matching, data-to-text and a verified knowledge layer for Microsoft 365 Copilot
- [governed-ai-platform](https://github.com/flam7791/governed-ai-platform): all of it as one
  operable service on Docker Compose, Kubernetes or Azure, including a sovereign mode in which no
  external model exists ([screenshots](https://github.com/flam7791/governed-ai-platform#see-it-running))

## Measured, including where it lost

Every system runs on open-weight models on a laptop, with answers recorded and replayed in CI.
Llama 3.1 8B, Qwen 2.5 7B and Mistral's Ministral 3 8B each held every safety check; no model was
better everywhere, which is why each service is measured on its own cases
([details](https://github.com/flam7791/ai-engineering-framework/blob/main/docs/model-selection.md)).
Where a model step did not beat a simple rule, as with the gateway's
[difficulty judge](https://github.com/flam7791/governed-llm-gateway#judged-routing-04), it stays
off and the README says so.

**Product:** discovery · jobs to be done · PRD · RICE · WSJF · pilot design · success metrics · decision logs · team packs

**Tech:** `Python` · `MCP` · `RAG` · `AI agents` · `FastAPI` · `Claude API` · `Azure OpenAI` · `Mistral AI` · `Microsoft 365 Copilot` · `Copilot Studio` · `Entra ID` · `Ollama` · `Kubernetes` · `OpenTelemetry` · `GitHub Actions`

Paris · English, Italian, Spanish, French (working knowledge)
