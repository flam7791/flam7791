# Flavio 

I work on enterprise AI adoption and governance: moving AI from pilots to governed, measurable
services in large organisations. These repositories show how I approach it in practice: small
systems, tested, auditable, and explicit about what they measure and what they cost.

## Projects

**[governed-ai-platform](https://github.com/flam7791/governed-ai-platform)**: the reference
deployment that brings the three components below together as one operable service: hardened
containers, secrets, Prometheus monitoring with alert rules, pinned component versions, a runbook,
and an end-to-end test on every change that starts the whole stack and walks an agent run
through a human approval.

**[governed-agents](https://github.com/flam7791/governed-agents)**: a reference architecture
for governed multi-agent systems. Specialist agents use real tools (Python and MCP), and a
policy engine decides every tool call: least privilege, autonomy levels, allowed recipients.
External actions wait for a named person's approval (four eyes, from a web page or the command
line), every step lands in an audit trail, and agents are evaluated on what they did, including
a planted prompt-injection test.

**[governed-llm-gateway](https://github.com/flam7791/governed-llm-gateway)**: an internal LLM
gateway that routes each request to the cheapest adequate model (Claude, Azure OpenAI with
Entra ID, or a local open-weight model), masks personal data before it leaves, enforces team
budgets and produces chargeback reports without storing content. OpenAI-compatible (chat and
embeddings), with Prometheus metrics, evaluated for quality and cost.

**[reference-resolver-agent](https://github.com/flam7791/reference-resolver-agent)**: an
agentic workflow using Claude to resolve messy bibliographic references to DOIs. Deterministic
scoring comes first; the model only chooses among records actually retrieved, a bounded search
agent handles the rest, and uncertain cases go to a human review queue. Measured on a gold set.

**[policy-evidence-mcp](https://github.com/flam7791/policy-evidence-mcp)**: an MCP server
that gives AI assistants cited access to official statistics (SDMX) and policy documents
(hybrid RAG: keywords plus embeddings), with a sensitivity ceiling. Read-only by design,
rate-limited, with a retrieval evaluation as a CI gate.

**[copilot-team-knowledge](https://github.com/flam7791/copilot-team-knowledge)**: a curated
knowledge layer that Microsoft 365 Copilot answers from. A team keeps verified knowledge cards
in SharePoint; a validator and a publisher release only active cards at or below a classification
ceiling to the folder Copilot reads, so drafts, replaced decisions and restricted content never
reach it. Runs as a declarative agent or, where agents are not available, as saved Copilot Chat
prompts, and is evaluated on the failures that matter, including prompt injection.

**[oecd-data-pipeline](https://github.com/flam7791/oecd-data-pipeline)**: turns OECD Data
Explorer indicators into checked, plain-English country notes. Python fetches the data with its
provenance, cleans it by rules and computes every figure; Microsoft 365 Copilot only writes the
wording, from a saved prompt on small batches. A validator then rejects any note that skips a
row, contradicts the figures or mentions a number not in the data, and sends it to a person for
review. No API costs; tested offline in CI.

## How I build

- Deterministic where possible, models where they add value, people where it matters
- Guardrails enforced in code, not only in prompts
- Every system ships with an evaluation and a cost figure

Built with AI-assisted development. The design decisions behind each project are documented in
its `docs/` folder.

`Python` · `pandas` · `SDMX` · `FastAPI` · `MCP` · `RAG` · `AI agents` · `Claude API` · `Azure OpenAI` · `Microsoft 365 Copilot` · `SharePoint` · `Ollama` · `Docker Compose` · `Prometheus` · `GitHub Actions`

Paris · English, Italian, Spanish, French (working knowledge)
