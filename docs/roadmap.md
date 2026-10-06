# Research and Implementation Roadmap

This roadmap separates questions that must be answered from implementation milestones. Dates are intentionally omitted while the project is exploratory.

## Track A — Semantics

- Stabilize vocabulary.
- Define lifecycle states and transitions.
- Define evidence relationships.
- Define scope semantics.
- Define provenance requirements.
- Define knowledge/application authority separation.

## Track B — Minimal prototype

Build the smallest complete loop:

```text
execution
 → experience
 → reflection
 → candidate
 → evidence
 → validation
 → knowledge
 → retrieval
 → later execution
```

The prototype should demonstrate that a learned item can improve a later task and that its lineage can be inspected.

## Track C — Evolution

- Contradiction detection.
- Deduplication/consolidation.
- Confidence recalibration.
- Scope refinement.
- Versioning.
- Challenge/deprecation/supersession.
- Knowledge utility measurement.

## Track D — Collective learning

- Agent-local stores.
- Shared domain stores.
- Promotion policies.
- Knowledge Steward.
- Cross-agent evidence.
- Access and visibility policies.

## Track E — Organizational learning

- Organizational knowledge scope.
- Stronger promotion governance.
- Human approval workflows.
- Audit trails.
- Event integration.
- Policy integration.
- Digital-twin feedback/simulation experiments.

## Reference experiments

### Cine Toaster

Candidate experiments:

- model/workflow recommendations from repeated rendering outcomes;
- character-consistency heuristics;
- cost/quality trade-off learning;
- prompt and negative-prompt lessons;
- model-version-sensitive knowledge.

### KDP Studio

Candidate experiments:

- editorial/revision patterns;
- translation quality lessons;
- layout/export failure prevention;
- research-source strategies;
- publishing workflow improvements.

### Bionic Company

Candidate experiments:

- cross-agent/domain knowledge promotion;
- process learning;
- organizational exceptions;
- policy recommendations;
- knowledge-informed digital-twin simulation.

## Evaluation questions

The project should eventually measure more than retrieval accuracy:

- Did learned knowledge improve task outcomes?
- Did it reduce repeated failures?
- Was irrelevant knowledge correctly excluded by scope?
- Were contradictions detected?
- Could the origin of a decision be reconstructed?
- Did promoted knowledge generalize to the scope it claimed?
- Could bad knowledge be safely challenged and rolled back?
- What was the cost of reflection and validation relative to its benefit?
