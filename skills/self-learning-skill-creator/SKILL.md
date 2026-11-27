---
name: self-learning-skill-creator
description: Universal skill generator that scaffolds, standardizes, and registers new skills with built-in 3 Ws self-learning feedback loops. Strictly references skill-organizer as the single source of truth, enforcing modular architecture, zero duplication, and machine-executable prompt contracts.
---

# `self-learning-skill-creator` — Universal Skill Factory

`self-learning-skill-creator` scaffolds new skills across the ecosystem. It strictly derives all conventions, structures, and schemas from `skill-organizer` (Single Source of Truth), ensuring that no rule or definition is ever duplicated.

---

## 1. Governance & Protocol Binding

This skill operates strictly under the authority of `skill-organizer`:
- **Taxonomy & Category Spec**: `skills/skill-organizer/taxonomy.json`
- **Universal Contract Spec**: `skills/skill-organizer/protocol/skill_contract_spec.md`
- **3 Ws Self-Learning Engine**: `skills/skill-organizer/protocol/3ws_self_learning_protocol.md`

Every generated skill is guaranteed to be:
1. **Modular**: Isolated in its own directory with dedicated `SKILL.md`, `prompt_contract.json`, and `self_learning.json`.
2. **Contract-Driven**: Clean separation between instructions, machine prompts, and runtime parameters.
3. **Self-Learning**: Pre-configured with the 3 Ws ledger to track What Worked, What Failed, and What to Adapt.
4. **Idempotent**: Zero token waste, deterministic IO, and zero unintended side-effects.

---

## 2. Skill Creation Workflow

When requested to create a new skill or convert an existing procedure into a skill:

### Step 1: Taxonomy & Namespace Validation
1. Verify the skill name uses lowercase kebab-case (`my-feature-skill`).
2. Map the skill to an official category in `skills/skill-organizer/taxonomy.json`.
3. Check for namespace collisions in the active registry.

### Step 2: Scaffolding Directory Structure
The creator generates the following atomic files:
```
skills/[skill-name]/
├── SKILL.md                 # Agent instructions & triggers (references skill-organizer)
├── prompt_contract.json     # Machine-executable prompt schema (conforming to skill_contract_spec.md)
├── self_learning.json       # Initialized 3 Ws memory ledger
└── (domain assets)          # Optional ComfyUI workflow JSONs, scripts, or dropdown options
```

### Step 3: Wire 3 Ws Self-Learning Loop
1. Instantiate `self_learning.json` with baseline priors:
   - `what_worked`: Initial positive anchors and tested configurations.
   - `what_failed`: Known negative anti-patterns or drift vectors.
   - `what_to_adapt`: Active guardrails to inject into prompts and parameter validation.
2. Link the skill's `prompt_contract.json` to consult `self_learning.json` dynamically before each turn.

### Step 4: Registry Indexing & Verification
1. Append the new skill to `skills/skill-organizer/taxonomy.json`.
2. Symlink into OpenCode's active registry (`/home/vishwa/.config/opencode/skills/`).
3. Run verification test to confirm contract parses cleanly.

---

## 3. Human & Agent Directive
To generate a new skill, provide:
- Skill name / purpose
- Target category
- Primary model / execution engine
- Core prompt directives and dynamic variables

`self-learning-skill-creator` handles scaffolding, schema validation, and ecosystem registration automatically.
