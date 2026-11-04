# Flavio

I help large, regulated organisations move AI from scattered pilots to governed services that
people use: choosing what to build, keeping it within the EU AI Act and the organisation's own
rules, driving adoption, and proving with evidence whether it was worth it. The repositories below
are that work in miniature: five product MVPs, each taken from discovery to a pilot a team could
run, and the governed AI platform they run on.

## Start here: ten minutes, five questions a transformation lead asks

1. **Which AI uses must stop, and which obligations are already late?** ai-act-readiness's
   [sample executive pack](https://github.com/flam7791/ai-act-readiness/blob/main/docs/sample-report.md)
   for a fictional insurer: a prohibited use, an overdue disclosure, a derogation claim sent to
   counsel, and the high-risk programme to fund before December 2027.
2. **Which pilots to scale, and which to stop?** ai-adoption-tracker's
   [PRD](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/02-prd.md) and
   [decision log](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/06-decision-log.md),
   with decision rules fixed before the pilot and committee overrides recorded, not hidden.
3. **Is this process worth redesigning AI-first?** agentic-procurement-intake's
   [service blueprint](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/02-service-blueprint.md)
   and [build, buy, reuse or stop case](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/03-options-and-investment-case.md).
4. **What do users actually need next?** feedback-to-roadmap's
   [worked example](https://github.com/flam7791/feedback-to-roadmap/blob/main/docs/product/07-worked-example.md)
   counts feedback in people, not rows, and moves the sponsor's top item to fourth of eight.
5. **Does it work, honestly measured?** obligations-register's
   [held-out evaluation](https://github.com/flam7791/obligations-register/blob/main/eval/EVALS.md),
   a weak result published, not patched.

## From strategy to operation

| Stage | What it answers | Where |
|---|---|---|
| Decide | Which use cases, which pattern, build or buy, what it costs | [ai-engineering-framework](https://github.com/flam7791/ai-engineering-framework) intake; [agentic-procurement-intake](https://github.com/flam7791/agentic-procurement-intake) investment case |
| Govern | Which uses the AI Act prohibits or makes high-risk, which duties are due when, who approves what an agent may do | [ai-act-readiness](https://github.com/flam7791/ai-act-readiness); [governed-agents](https://github.com/flam7791/governed-agents); [governed-llm-gateway](https://github.com/flam7791/governed-llm-gateway) |
| Adopt | Whether people use it, what they ask for, where AI literacy falls short | [ai-adoption-tracker](https://github.com/flam7791/ai-adoption-tracker); [feedback-to-roadmap](https://github.com/flam7791/feedback-to-roadmap); ai-act-readiness literacy view |
| Prove value | Scale, iterate or stop on measured use and value against cost | [ai-adoption-tracker](https://github.com/flam7791/ai-adoption-tracker) |
| Run | One operable, observable service, on cloud or entirely in-house | [governed-ai-platform](https://github.com/flam7791/governed-ai-platform) |

## Five product MVPs

Hypotheses and non-goals are written before any code, pilot decision rules before launch, and
each repository ships a team pack (brief and RACI, backlog, plan for the next sprints) with CI failing if a
story marked Done has no test proving it.

| Product | The problem, and for whom |
|---|---|
| [ai-act-readiness](https://github.com/flam7791/ai-act-readiness) | An executive committee asked to fund AI Act readiness with no joined view of classification, obligations, evidence and deadlines. It proposes a category for each use case with the articles behind it, separates provider and deployer duties, and opens with the decisions the committee owns; counsel confirms |
| [ai-adoption-tracker](https://github.com/flam7791/ai-adoption-tracker) | An AI review committee with a dozen pilots and no comparable view of use and value. It recommends scale, iterate or stop, showing every check; the committee decides |
| [agentic-procurement-intake](https://github.com/flam7791/agentic-procurement-intake) | Staff and procurement officers losing weeks between a need and an approvable request. An agent prepares the package; people confirm, approve and sign off, enforced in code |
| [feedback-to-roadmap](https://github.com/flam7791/feedback-to-roadmap) | The product owner of an internal AI assistant, prioritising by whoever argued best in the last meeting. It counts people across four channels and proposes explained roadmap changes; the product owner decides |
| [obligations-register](https://github.com/flam7791/obligations-register) | Teams tracking contract obligations late or by hand. A draft register in which every line is the exact source sentence; anything uncertain goes to a review queue |

In each, the tool recommends and a named person decides: governance is designed in, not added after.

## The platform underneath

[ai-engineering-framework](https://github.com/flam7791/ai-engineering-framework) makes governed
AI repeatable: a use-case intake that scores feasibility, sensitivity and cost, seven solution
patterns with working reference implementations, engineering standards checked in CI, and a
local-first service template. The reference implementations:

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

Every model-backed system runs on open-weight models on a laptop, with answers recorded and
replayed in CI. Llama 3.1 8B, Qwen 2.5 7B and Mistral's Ministral 3 8B each held every safety
check; no model was better everywhere, which is why each service is measured on its own cases
([details](https://github.com/flam7791/ai-engineering-framework/blob/main/docs/model-selection.md)).
Where a model step did not beat a simple rule, as with the gateway's
[difficulty judge](https://github.com/flam7791/governed-llm-gateway#judged-routing-04), it stays
off and the README says so.

**Strategy and product:** AI strategy and roadmap · use-case portfolio · business case · discovery · PRD · RICE · WSJF · pilot design · success metrics · decision logs

**Governance and adoption:** Responsible AI · EU AI Act · ISO/IEC 42001 · human oversight · AI literacy · adoption metrics · value realisation

**Tech:** `Python` · `MCP` · `RAG` · `AI agents` · `FastAPI` · `Claude API` · `Azure OpenAI` · `Mistral AI` · `Microsoft 365 Copilot` · `Copilot Studio` · `Entra ID` · `Ollama` · `Kubernetes` · `OpenTelemetry` · `GitHub Actions`

Paris · English, Italian, Spanish, French (working knowledge)
