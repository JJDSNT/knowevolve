# Knowledge Lifecycle

KnowEvolve treats knowledge as an evolving, evidence-backed object rather than a permanent memory entry.

## From execution to learning

```text
EXECUTE
  ↓
OBSERVE
  ↓
EVALUATE
  ↓
REFLECT
  ↓
LEARNING CANDIDATE
  ↓
ACCUMULATE EVIDENCE
  ↓
VALIDATE
  ├── reject
  ├── retain as hypothesis
  └── promote
          ↓
       KNOWLEDGE
```

### Execute
An agent performs work in its native environment.

### Observe
Relevant inputs, decisions, outputs, failures, feedback, metrics, and environmental conditions are captured.

### Evaluate
The outcome is assessed. Evaluation may be objective, heuristic, model-based, human, or domain-specific.

### Reflect
The system looks beyond the outcome and attempts to explain what contributed to success or failure.

### Propose
A reusable lesson is expressed as a learning candidate with an explicit scope.

### Evidence
Future and historical experiences may support, contradict, or refine the candidate.

### Validate
A policy decides whether the candidate is sufficiently useful and trustworthy to be promoted.

### Promote
Validated learning becomes governed knowledge at an appropriate scope.

## Knowledge does not stop evolving

```text
             ┌── strengthen
validated ───┼── remain valid
             ├── narrow / rescope
             └── challenge
                    ↓
               supersede
                    or
                deprecate
```

A superseded item remains part of the historical record.

## Promotion across scopes

```text
Agent Knowledge
      ↓
   evidence
 + governance
      ↓
Domain Knowledge
      ↓
 stronger evidence
 + broader review
      ↓
Organizational Knowledge
```

Frequency alone should not imply promotion. A highly repeated local optimization may still be inappropriate outside its original scope.

## Knowledge application

A validated item is useful only if it can improve future behavior. Applications may include:

- retrieved context;
- prompt guidance;
- skill selection or refinement;
- workflow selection;
- tool selection;
- policy recommendations;
- planning constraints.

KnowEvolve should preserve the distinction between **knowing something** and **granting it authority to change behavior**.

## Epistemic metadata

Candidate fields include:

- statement;
- state;
- scope and conditions;
- provenance;
- supporting evidence;
- contradicting evidence;
- confidence;
- discovery source;
- validators;
- creation and validation timestamps;
- version;
- superseded/superseding relationships;
- application history;
- observed utility.

The final schema will be informed by implementation experiments.
