# KnowEvolve

> **Turning AI agent experience into validated, evolving, and shared knowledge.**

**Agents shouldn't just remember. They should learn.**

KnowEvolve is an experimental, framework-agnostic knowledge evolution layer for AI agents. Its purpose is to turn operational experience — successful runs, failures, feedback, metrics, and observations — into knowledge that can be evaluated, validated, versioned, reused, challenged, superseded, and shared.

KnowEvolve is **not primarily an agent-memory framework**. Memory answers *what should an agent remember?* KnowEvolve focuses on a different question:

> **What has an agent actually learned, how trustworthy is that learning, where does it apply, and who else should be able to benefit from it?**

## The idea

```text
EXECUTE → OBSERVE → EVALUATE → REFLECT
                         ↓
                  LEARNING CANDIDATE
                         ↓
                      EVIDENCE
                         ↓
                     VALIDATE
                  ↙      ↓       ↘
              reject  retain   promote
                                ↓
                            KNOWLEDGE
                                ↓
                 ┌──────────────┼──────────────┐
                 ↓              ↓              ↓
               Agent          Domain      Organization
             Knowledge       Knowledge      Knowledge
                 └──────────────┼──────────────┘
                                ↓
                         FUTURE BEHAVIOR
                                ↓
                         new experience ↺
```

The loop does not end when knowledge is promoted. Validated knowledge remains subject to new evidence and may be strengthened, challenged, scoped more narrowly, deprecated, or superseded.

## Core principles

- **Experience is not knowledge.** Execution traces are evidence, not truth.
- **Memory is not learning.** Remembering an event does not mean deriving a reusable lesson from it.
- **Knowledge is contextual.** A learning should carry scope, conditions, provenance, evidence, confidence, and lifecycle.
- **Knowledge is mutable, history is not.** New evidence may supersede a conclusion without erasing how it was reached.
- **Learning must affect behavior.** Useful knowledge should be consumable by prompts, context, skills, workflows, policies, or tool selection.
- **Collective learning is explicit.** Knowledge may progress from an individual agent to a domain and, where appropriate, to an organization.
- **Governance is part of learning.** Promotion, contradiction, deprecation, access, and provenance are first-class concerns.
- **Framework agnostic by design.** Agent runtimes, LLM providers, memory systems, vector stores, and orchestration frameworks should integrate through adapters.

## Knowledge lifecycle

A possible initial lifecycle:

```text
observation
    ↓
hypothesis
    ↓
candidate
    ↓
validated
    ↓
best practice

validated → challenged → deprecated
                    ↘→ superseded
```

The exact lifecycle is intentionally still open for experimentation.

## Three scopes of knowledge

**Agent knowledge** belongs to an individual agent and may reflect specialized experience.

**Domain knowledge** is useful beyond one agent within a bounded field, workflow, team, or application.

**Organizational knowledge** represents learning that has passed the governance required to influence broader organizational behavior.

Promotion between these scopes is not automatic simply because a statement has been observed repeatedly.

## Conceptual data model

A knowledge item may eventually resemble:

```yaml
id: knowledge-item-id
statement: "A reusable learning derived from experience"

state: validated
confidence: 0.91

scope:
  domain: example-domain
  conditions:
    - relevant-condition

evidence:
  supporting: []
  contradicting: []

provenance:
  discovered_by: agent-id
  derived_from: []

lifecycle:
  created_at: ...
  last_validated_at: ...
  supersedes: null
```

This is illustrative, not yet a stable schema.

## Architecture direction

KnowEvolve separates four concepts that are often collapsed into a single memory layer:

```text
Experience Store
"What happened?"
      ↓
Memory
"What should be remembered?"
      ↓
Knowledge
"What have we learned?"
      ↓
Policy / Skill / Context
"How should behavior change?"
```

KnowEvolve intends to own primarily the transition from **experience to governed knowledge**, while allowing external systems to provide storage, memory, evaluation, orchestration, and runtime capabilities.

See [Architecture](docs/architecture.md) and [Knowledge Lifecycle](docs/knowledge-lifecycle.md).

## Reference integrations

The initial concept is intended to be tested against real agentic systems rather than only synthetic benchmarks:

- **Cine Toaster** — audiovisual production agents can learn about workflows, models, prompting, consistency, quality, and rendering trade-offs.
- **KDP Studio** — editorial agents can learn from research, writing, revision, translation, layout, cover, publishing, and marketing outcomes.
- **Bionic Company** — a broader validation case for domain and organizational learning, governance, and interaction with organizational digital twins.

These are reference integrations, not dependencies. KnowEvolve should remain independently usable.

## Initial roadmap

### Phase 0 — Foundation
- Define vocabulary and lifecycle.
- Define experience, evidence, learning-candidate, and knowledge contracts.
- Define provenance and scope semantics.
- Survey related work and reusable infrastructure.

### Phase 1 — Minimal learning loop
- Capture an agent execution.
- Produce a reflection.
- Extract a candidate learning.
- Attach and aggregate evidence.
- Validate or reject the candidate.
- Store validated knowledge.
- Retrieve relevant knowledge for a later execution.

### Phase 2 — Knowledge evolution
- Contradiction detection.
- Confidence revision.
- Knowledge versioning.
- Challenge, deprecation, and supersession.
- Context- and scope-aware retrieval.

### Phase 3 — Collective learning
- Agent → domain promotion.
- Shared domain knowledge.
- Knowledge Steward workflows.
- Human and agent validation policies.

### Phase 4 — Organizational learning
- Domain → organization promotion.
- Organizational governance and access.
- Auditability and policy integration.
- Digital-twin integration and simulation feedback.

## Non-goals — for now

KnowEvolve is not intended to become:
- a general-purpose LLM orchestration framework;
- another agent runtime;
- a replacement for every memory/vector database;
- an autonomous prompt rewriter that silently changes agent behavior;
- a system that treats repeated correlation as universal truth.

## Status

**Early concept / research stage.**

The architecture, terminology, APIs, schemas, and implementation strategy are expected to evolve as the idea is tested. The repository intentionally distinguishes current hypotheses from settled design decisions.

## Related work

KnowEvolve builds on ideas from persistent agent memory, reflection, experience-driven learning, self-evolving agents, knowledge graphs, and organizational memory. See [Related Work](docs/related-work.md).

## License

To be decided.
