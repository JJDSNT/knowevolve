# Related Work

> This is a living research map, not a claim that the projects below are interchangeable with KnowEvolve.

KnowEvolve sits at the intersection of several active areas: agent memory, reflection, experience-driven learning, self-evolving agents, knowledge management, and organizational memory.

## Memory infrastructure

### Letta / MemGPT
Persistent agents, editable memory, and approaches to background/sleep-time memory processing are relevant to KnowEvolve's memory boundary.

- https://www.letta.com/
- https://github.com/letta-ai/letta

### Mem0
A mature memory layer for AI applications. KnowEvolve should investigate memory systems such as Mem0 as possible backends rather than rebuilding commodity memory infrastructure.

- https://mem0.ai/
- https://github.com/mem0ai/mem0

## Reflection and experience-driven learning

### Reflexion
An influential approach in which agents improve through linguistic feedback and reflection without requiring model-weight updates.

- https://arxiv.org/abs/2303.11366

### MUSE
Recent work on extracting reusable knowledge from agent interaction trajectories and experience.

- https://aclanthology.org/2026.findings-acl.1522/

### EvolveR
Experience-driven agent evolution, including extracting and managing reusable principles from successful and unsuccessful executions.

- https://proceedings.mlr.press/v306/wu26bf.html

### ReMe — Remember Me, Refine Me
Work on refining agent memory from experience, including success patterns and failure causes.

- https://aclanthology.org/2026.findings-acl.829/

### Experience Graphs (EXG)
Explores structured representations of accumulated agent experience rather than treating experience as a flat collection of memories.

- https://arxiv.org/abs/2605.17721

## Evolving memory and learning mechanisms

### MemEvolve
Investigates memory systems whose own strategies can evolve rather than keeping the memory mechanism fixed.

- https://proceedings.mlr.press/v306/zhang26fa.html

### MemSkill
Explores memory operations as skills that can themselves be refined.

- https://arxiv.org/abs/2602.02474

## Adjacent open-source initiatives

### Leaper Agent
A self-learning agent framework with concepts around memory evolution, validation, promotion, and consolidation.

- https://github.com/Deepleaper/leaper-agent

### Agent Lore
A Git-backed knowledge base writable by agents. Particularly relevant as an example of persistent/shared knowledge and provenance.

- https://github.com/osteele/agent-lore

### Noesis
An adjacent knowledge-engine direction involving versioned agent knowledge, provenance, lifecycle, and contradiction-related concepts.

- https://github.com/Ikey168/Noesis

### Empirica
Explores epistemic infrastructure for AI, including measurement, memory, calibration, and learning across sessions.

- https://github.com/EmpiricaAI/empirica

## KnowEvolve's working distinction

The current hypothesis is that many existing systems primarily optimize one or more of:

```text
remembering
retrieval
reflection
experience reuse
self-improvement
```

KnowEvolve is specifically exploring the full governed transition:

```text
experience
   ↓
evidence-backed learning
   ↓
validated knowledge
   ↓
knowledge evolution
   ↓
agent → domain → organization
   ↓
controlled behavioral change
```

This distinction is a research hypothesis and should be continually tested against new work rather than treated as a permanent claim of novelty.
