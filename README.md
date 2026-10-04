# Flavio

I work on enterprise AI adoption and governance: moving AI from pilots to governed, measurable
services in large organisations. These repositories show how I approach it in practice: a
framework that makes AI services consistent, and the working systems it is built from. Small,
tested, auditable, explicit about what they measure and what they cost, and able to run
entirely on open-weight models on an organisation's own infrastructure.

## Start here: five minutes

1. **See a governed agent run end to end.** The
   [platform's screenshots](https://github.com/flam7791/governed-ai-platform#see-it-running):
   an agent's email waiting for a person, the audit trail with every policy decision and its
   cost, and one OpenTelemetry trace across the agents, the LLM gateway and the MCP server.
2. **Check that it is tested, not described.** Every repository's CI badge is green; the
   platform's CI starts the whole stack and walks a run through a human approval, and a
   [Kubernetes workflow](https://github.com/flam7791/governed-ai-platform/blob/main/docs/kubernetes.md)
   deploys it to a cluster and checks that the network policies block what they should.
3. **See the numbers.** [Measured results](#local-and-open-weight-by-design) with a local
   open-weight model next to Claude, recorded and replayed in CI.
4. **See how a new project starts.** The framework's
   [use-case intake and service template](https://github.com/flam7791/ai-engineering-framework):
   a proposal scored on sensitivity, cost and risk, then a service generated local-first with
   its evaluation already wired in.

## The framework

**[ai-engineering-framework](https://github.com/flam7791/ai-engineering-framework)**: how an
organisation identifies, builds, industrialises and operates AI solutions the same way every
time. A reference architecture with on-premises, hybrid and cloud topologies; six solution
patterns, each with a working reference implementation below; engineering standards that run as
checks in CI (`aief check`); a use-case intake that scores proposals on feasibility, information
sensitivity, security, cost, scalability, interoperability and sustainability and recommends a
pattern and topology (`aief intake`); lifecycle gates and a handover pack; and a service
template that starts every new project local-first, evaluated and production-ready.

## Reference implementations, by stage

| Stage | Repository | What it shows |
|---|---|---|
| **Identify** | [governed-agents](https://github.com/flam7791/governed-agents) (use-case triage desk) | Agents that register a proposed AI use case, assess risk and cost, choose a pattern and submit a decision record for sign-off |
| **Build** | [policy-evidence-mcp](https://github.com/flam7791/policy-evidence-mcp) | An MCP server giving assistants cited access to official statistics (SDMX) and policy documents: hybrid RAG with a sensitivity ceiling, per-caller access from bearer tokens or Entra ID app roles, SharePoint libraries synced through Microsoft Graph with Purview labels as the classification, retrieval evaluation as a CI gate |
| | [reference-resolver-agent](https://github.com/flam7791/reference-resolver-agent) | Deterministic scoring first; the model chooses only among records actually retrieved; a bounded search agent; uncertain cases to a human review queue; measured on a gold set |
| | [oecd-data-pipeline](https://github.com/flam7791/oecd-data-pipeline) | Python computes every figure, a model (Microsoft 365 Copilot or a local open-weight model) writes only the wording, and a validator rejects any note with a number not in the data |
| | [copilot-team-knowledge](https://github.com/flam7791/copilot-team-knowledge) | A verified knowledge layer that Microsoft 365 Copilot answers from: only active cards at or below a classification ceiling are published, to SharePoint through Microsoft Graph; also answerable by a local model |
| **Industrialise** | [governed-llm-gateway](https://github.com/flam7791/governed-llm-gateway) | One door to every model: routes each request to the cheapest adequate model (Claude, Azure OpenAI with Entra ID, or local), masks personal data, enforces budgets, chargeback without storing content, OpenTelemetry traces |
| | [governed-agents](https://github.com/flam7791/governed-agents) | Multi-agent runtime where a policy engine decides every tool call: least privilege, autonomy levels, four-eyes approval for external actions, audit trail, kill switch, trajectory evaluation with a planted prompt injection, one OpenTelemetry trace per run |
| **Operate** | [governed-ai-platform](https://github.com/flam7791/governed-ai-platform) | The components as one operable service, on Docker Compose or Kubernetes (restricted pod security, default-deny network policies): Prometheus alerts, one trace per agent run across the services, pinned versions, runbook, an end-to-end test in CI, and a sovereign mode in which no external model exists |

## Local and open-weight by design

Every system runs without a commercial API: Ollama on a laptop, or any OpenAI-compatible server
(vLLM on a GPU server, for example), with commercial models as a governed choice through the
gateway. Measured with Llama 3.1 8B on a laptop CPU, answers recorded and replayed in CI: the
resolver matched Claude (precision and recall 1.00) at zero cost; a service generated from the
framework passed 10 of 10 cases, including one where the model followed a planted instruction and
the validator withheld the answer; the knowledge layer passed 11 of 12 with no blocking failure.
The first runs also exposed two integration bugs, now fixed and tested
([details](https://github.com/flam7791/ai-engineering-framework/blob/main/docs/model-selection.md)).

## How I build

- Deterministic where possible, models where they add value, people where it matters
- Guardrails enforced in code, not only in prompts
- Every system ships with an evaluation, a cost figure and a way to run it locally
- Standards that run: each repository is checked against the framework's standards in CI

The design decisions behind each project are documented in its `docs/` folder.

`Python` · `MCP` · `RAG` · `AI agents` · `FastAPI` · `pandas` · `SDMX` · `Claude API` · `Azure OpenAI` · `Microsoft 365 Copilot` · `SharePoint` · `Ollama` · `open-weight models` · `Microsoft Graph` · `Entra ID` · `Docker Compose` · `Kubernetes` · `Prometheus` · `OpenTelemetry` · `GitHub Actions` · `Copier`

Paris · English, Italian, Spanish, French (working knowledge)
