# Conceptual Model

> **Status:** draft vocabulary for discussion and prototyping.

The purpose of this model is to give implementations a common language without prematurely defining a database schema.

## Core entities

### Experience

A record of something that happened during agent work.

An experience may include:

- task and relevant context;
- agent and runtime identity;
- decisions and actions;
- tools used;
- outputs;
- errors and exceptions;
- objective metrics;
- evaluator feedback;
- human feedback;
- environmental conditions;
- timestamps and trace references.

An experience is **evidence**, not knowledge.

### Evaluation

An assessment of an experience or outcome. Evaluations should identify their evaluator and method so that model judgment, deterministic measurement, and human review are not conflated.

### Reflection

An interpretation of one or more experiences that attempts to explain outcomes, patterns, causes, or opportunities for improvement.

A reflection may produce zero or more learning candidates.

### Learning Candidate

A proposition that might be useful beyond the experience from which it was derived.

A candidate should normally contain:

```text
statement
scope
conditions
provenance
initial evidence
rationale
```

It has not yet earned the status of validated knowledge.

### Evidence

A relationship between an observation and a proposition.

Evidence may:

- support;
- contradict;
- contextualize;
- weaken;
- narrow;
- strengthen.

Evidence should preserve provenance.

### Knowledge Item

A governed learning that has passed the validation required for its current state and scope.

Possible properties:

```yaml
id:
statement:
state:
confidence:

scope:
  level: agent | domain | organization
  domain:
  conditions: []

evidence:
  supporting: []
  contradicting: []

provenance:
  discovered_by:
  source_experiences: []
  validators: []

lifecycle:
  version:
  created_at:
  last_validated_at:
  supersedes:
  superseded_by:

application:
  authority:
  uses: []
  observed_utility:
```

### Application

A record that knowledge was used to influence a future execution. Tracking application makes it possible to ask whether promoted knowledge actually improved outcomes.

## Relationships

```text
Experience ──evaluated_by──> Evaluation
     │
     └──interpreted_by─────> Reflection
                                │
                                └──proposes──> Learning Candidate
                                                  │
Experience ─────────────evidence_for/against──────┤
                                                  ↓
                                            Validation
                                                  ↓
                                           Knowledge Item
                                                  │
                                                  ├──supersedes──> Knowledge Item
                                                  │
                                                  └──applied_in──> Experience
```

The last relationship closes the learning loop.

## Knowledge vs behavior authority

A knowledge item can be valid without being allowed to autonomously alter behavior.

Possible authority levels might eventually include:

```text
informational
recommendation
context injection
workflow influence
policy influence
automatic enforcement
```

The exact model remains open, but the separation is intentional.

## Confidence

KnowEvolve should not assume that one universal numeric confidence formula works across all domains. Confidence may combine:

- quantity of evidence;
- quality of evidence;
- recency;
- evaluator reliability;
- contradiction;
- replication across contexts;
- observed utility.

Domain adapters should be able to contribute their own calibration logic.

## Scope

Scope answers **where a learning is expected to hold**.

It may include:

- agent;
- team/domain;
- organization;
- task type;
- model/model version;
- tool version;
- workflow;
- environment;
- temporal validity;
- other domain-specific conditions.

Scope should be refinable as new evidence arrives.

## Provenance

Every promoted item should make it possible to reconstruct:

```text
Where did this come from?
Which experiences support it?
Who/what evaluated it?
Who/what validated it?
What changed over time?
What knowledge did it replace?
Where has it been applied?
```

Provenance is therefore part of the domain model, not optional observability metadata.
