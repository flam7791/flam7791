# Flavio

I build AI products for large organisations, the product way: start from the people who do the
work, decide what to build and what to leave out, and prove with evidence whether it worked. These
repositories are that work in public: four product MVPs, each taken from discovery to a pilot a
team could run, and the governed AI platform they are built on, tested, measured and able to run
entirely on an organisation's own infrastructure.

## Start here: ten minutes on the product work

1. **Evidence overturning a sponsor's priority.** In feedback-to-roadmap's
   [worked example](https://github.com/flam7791/feedback-to-roadmap/blob/main/docs/product/07-worked-example.md),
   eight weeks of feedback, counted in people rather than rows, move the sponsor's top item
   (outdated content) to fourth of eight problems, behind one that 30 people raised and that had
   made 22 of them stop using the assistant.
2. **Decision rules fixed before the pilot.** ai-adoption-tracker's
   [PRD](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/02-prd.md) and
   [decision log](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/06-decision-log.md):
   what counts as scale, iterate or stop for an AI pilot, and how a committee's override is
   recorded rather than hidden.
3. **A process redesigned AI-first, with its investment case.** agentic-procurement-intake's
   [service blueprint](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/02-service-blueprint.md)
   gives every step an owner and an autonomy level; the
   [options case](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/03-options-and-investment-case.md)
   weighs building against buying, reusing, partnering or stopping.
4. **A weak result published, not patched.** obligations-register's
   [held-out evaluation](https://github.com/flam7791/obligations-register/blob/main/eval/EVALS.md)
   (deadline accuracy 0.64) and why it was not tuned away.
5. **A team could pick it up on Monday.** Each MVP ships a team pack (brief and RACI, backlog,
   iteration plan, working agreement), and CI fails if a story marked Done has no test proving
   it, as in ai-adoption-tracker's
   [traceability](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/team/traceability.md).

## Four product MVPs

Each starts from a problem a large organisation has with AI, or with work AI could take on. Its
hypotheses and non-goals are written before any code, its pilot's decision rules are fixed before
launch, and its README opens with a ten-minute reading path through the product case.

| Product | The problem, and for whom | What it does | Worth a look |
|---|---|---|---|
| [feedback-to-roadmap](https://github.com/flam7791/feedback-to-roadmap) | The product owner of an internal AI assistant: plenty of feedback, still prioritised by whoever argued best in the last meeting | Counts people, not rows, across four channels, with verbatim quotes, silent segments and spikes; proposes RICE changes with their rules; the product owner accepts, rejects or pins, each with a note | The [worked example](https://github.com/flam7791/feedback-to-roadmap/blob/main/docs/product/07-worked-example.md), the [decision log](https://github.com/flam7791/feedback-to-roadmap/blob/main/docs/product/06-decision-log.md), the [held-out result](https://github.com/flam7791/feedback-to-roadmap/blob/main/evals/EVALS.md) (precision 0.69, recall 0.24) and what it changed |
| [ai-adoption-tracker](https://github.com/flam7791/ai-adoption-tracker) | An AI review committee with a dozen pilots and no comparable view of which ones are used and worth what they cost | A review pack from the use-case register and usage events: scale, iterate or stop, with every check's value and threshold; the tool recommends, the committee decides | The [PRD](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/02-prd.md), the [decision log](https://github.com/flam7791/ai-adoption-tracker/blob/main/docs/product/06-decision-log.md), how overrides are flagged |
| [agentic-procurement-intake](https://github.com/flam7791/agentic-procurement-intake) | Staff and procurement officers: buying a service starts with an email and weeks of questions | An agent turns a purchase request into a package procurement can approve on first review (method with its rule, framework reuse, split-purchase check, draft TOR); people confirm, approve and sign off, enforced in code | The [service blueprint](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/02-service-blueprint.md), the [build, buy, reuse or stop case](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/03-options-and-investment-case.md), the WSJF [roadmap](https://github.com/flam7791/agentic-procurement-intake/blob/main/docs/product/05-roadmap-and-prioritisation.md) |
| [obligations-register](https://github.com/flam7791/obligations-register) | Teams who must know who must do what, by when, from contracts and policies tracked late, by hand, or not at all | A draft register in which every line is the exact sentence from the source, with its location; what it is unsure of goes to a review queue with the reason | The [held-out result](https://github.com/flam7791/obligations-register/blob/main/eval/EVALS.md) (deadline accuracy 0.64) and why it was not patched |

The four are linked: the tracker decides which assistants scale, iterate or stop; feedback-to-roadmap
plans the iterate cycle for one of them, from the same users; and the register, the intake desk and
the feedback tool log their own usage in the tracker's event format, so their scale-or-stop reviews
rest on evidence.

## How I run a product

- **Discovery before delivery.** Personas, jobs to be done and falsifiable hypotheses, each with
  the result that would kill it, written before anything is built.
- **Scope with non-goals.** The PRD says what the product will not do as clearly as what it will.
- **Prioritisation in the open.** RICE or WSJF, with the cut line visible and the calls worth
  explaining written down.
- **Pilot rules decided in advance.** Success metrics and the scale, iterate or stop rules are
  fixed before launch, so a result cannot be argued into a win afterwards.
- **Evidence over anecdote.** Usage counted in people, held-out evaluations, and results published
  when they disappoint.
- **People decide.** The tool recommends; approvals and sign-offs stay with people, enforced in
  code rather than in a prompt.
- **Ready for a team.** Backlog, iteration plan, working agreement, and traceability from every
  story to the test that proves it.

## The platform underneath

A product reaches its users only if the AI inside it can be governed, measured and operated.
**[ai-engineering-framework](https://github.com/flam7791/ai-engineering-framework)** makes that
repeatable: a use-case intake that scores proposals on feasibility, information sensitivity,
security, cost, scalability, interoperability and sustainability and recommends a pattern
(`aief intake`); seven solution patterns, each with a working reference implementation; a reference
architecture for on-premises, hybrid and cloud; lifecycle gates and a handover pack; engineering
standards that run as checks in CI (`aief check`); and a service template that starts every new
project local-first, with its evaluation wired in.

| Stage | Repository | What it gives a product team |
|---|---|---|
| **Identify** | [governed-agents](https://github.com/flam7791/governed-agents) (use-case triage desk) | A proposed use case registered, assessed for risk and cost, matched to a pattern and submitted for sign-off |
| **Build** | [policy-evidence-mcp](https://github.com/flam7791/policy-evidence-mcp) | Cited answers from official statistics (SDMX) and documents for any assistant, within each caller's clearance (Entra ID app roles, Purview labels from SharePoint), served to Microsoft 365 Copilot through Copilot Studio; retrieval evaluation as a CI gate |
| | [reference-resolver-agent](https://github.com/flam7791/reference-resolver-agent) | Deterministic scoring first; the model chooses only among records actually retrieved; uncertain cases go to a person; measured on a gold set |
| | [oecd-data-pipeline](https://github.com/flam7791/oecd-data-pipeline) | Python computes every figure, a model writes only the wording, and a validator rejects any note with a number not in the data |
| | [copilot-team-knowledge](https://github.com/flam7791/copilot-team-knowledge) | A verified knowledge layer Microsoft 365 Copilot answers from, published only at or below a classification ceiling; also answerable by a local model |
| **Industrialise** | [governed-llm-gateway](https://github.com/flam7791/governed-llm-gateway) | One door to every model: each request goes to the cheapest adequate model (Claude, Azure OpenAI with Entra ID, Mistral AI, or local) within the team's data policy and budget, personal data masked, chargeback without storing content, OpenTelemetry traces |
| | [governed-agents](https://github.com/flam7791/governed-agents) | A multi-agent runtime where a policy engine decides every tool call: least privilege, autonomy levels, four-eyes approval for external actions, audit trail, kill switch, trajectory evaluation with a planted prompt injection |
| **Operate** | [governed-ai-platform](https://github.com/flam7791/governed-ai-platform) | The components as one operable service on Docker Compose, Kubernetes (restricted pod security, default-deny network policies) or Azure Container Apps in Bicep: alerts, one trace per agent run across the services, a runbook, an end-to-end test in CI, and a sovereign mode in which no external model exists |

To see it running, the platform's [screenshots](https://github.com/flam7791/governed-ai-platform#see-it-running)
show an agent's email waiting for a person, the audit trail with every policy decision and its
cost, and one OpenTelemetry trace across the agents, the LLM gateway and the MCP server.

## Measured, including where it lost

Every system runs without a commercial API, on Ollama on a laptop or any OpenAI-compatible server,
with commercial models as a governed choice through the gateway. Measured on a laptop CPU, with
answers recorded and replayed in CI: Llama 3.1 8B and Qwen 2.5 7B matched Claude on the resolver
(precision and recall 1.00) at zero cost; they and Mistral's Ministral 3 8B each passed 10 of 10
cases on a service generated from the framework, including one where the model followed a planted
instruction and the validator withheld the answer; and all three completed the five multi-agent
cases through human approvals with every safety check held, Ministral also getting right the
sensitivity and risk judgements the other two missed. No model was better everywhere, which is
why each service is measured on its own cases
([details](https://github.com/flam7791/ai-engineering-framework/blob/main/docs/model-selection.md)).

Where software needs a decision rather than a paragraph, the model answers from a closed set,
anything else counts as no decision, and code checks the answer before it acts:

| Where | Result | What decided it |
|---|---|---|
| [Reference resolver](https://github.com/flam7791/reference-resolver-agent): choose among retrieved records | Precision 1.00 with Claude, Llama 3.1 8B and Qwen 2.5 7B | Qwen's wrong choices came with confidence 0.95 and 0.80; code-side checks sent both to a person |
| [Evidence server](https://github.com/flam7791/policy-evidence-mcp): rerank passages | hit@3 0.90 to 0.95 on 40 paraphrased questions, no leak | Most replies for 20 passages were incomplete and became "no decision"; on the first 13 questions the gain had looked twice as large |
| [Gateway](https://github.com/flam7791/governed-llm-gateway#judged-routing-04): judge request difficulty | 14/24 (Llama 3.1 8B) and 17/24 (Ministral 3 8B) against the rules' 22/24; stays off | Both judges called most hard tasks simple, with confidence 0.9 to 1.0 |

The lesson, written into the framework's
[pattern P7](https://github.com/flam7791/ai-engineering-framework/blob/main/docs/patterns.md): a
model's stated confidence carried no information; the closed answer set and the checks in code did
the work. A model step that does not beat the baseline stays off, and the README says so.

## How I build

- Deterministic where possible, models where they add value, people where it matters
- Guardrails enforced in code, not only in prompts
- Every system ships with an evaluation, a cost figure and a way to run it locally
- Standards that run: each repository is checked against the framework's standards in CI
- Ready for coding agents: every repository has an `AGENTS.md` with its commands and the
  invariants nobody may weaken; the design decisions are in each project's `docs/` folder

**Product:** discovery · jobs to be done · PRD · RICE · WSJF · pilot design · success metrics · decision logs · team packs

**Tech:** `Python` · `MCP` · `RAG` · `AI agents` · `FastAPI` · `pandas` · `SDMX` · `Claude API` · `Azure OpenAI` · `Mistral AI` · `Microsoft 365 Copilot` · `SharePoint` · `Ollama` · `open-weight models` · `Microsoft Graph` · `Entra ID` · `Copilot Studio` · `Azure Container Apps` · `Bicep` · `Docker Compose` · `Kubernetes` · `Prometheus` · `OpenTelemetry` · `GitHub Actions` · `Copier`

Paris · English, Italian, Spanish, French (working knowledge)
