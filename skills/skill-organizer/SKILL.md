---
name: skill-organizer
description: Central governance authority, taxonomy registry, and single source of truth for all skills across the ecosystem. Defines universal skill anatomy, the 3 Ws self-learning protocol, modular separation of concerns, and cross-skill registries.
---

# `skill-organizer` — Universal Skill Governance & Taxonomy Engine

`skill-organizer` is the **Single Source of Truth (SSOT)** for all skills across `agent-skills`, `fashion-tech-skills`, and local OpenCode environments. No skill re-invents taxonomy, directory layouts, contract formats, or self-learning loops; all skills implement and reference the standards established here.

---

## 1. Universal Skill Taxonomy & Architecture

Every skill in the ecosystem belongs to an unambiguous category and complies with strict modular separation:

```
[skill-directory]/
├── SKILL.md                 # Human & agent operational manual (YAML frontmatter + instructions)
├── prompt_contract.json     # Machine-executable prompt schema + parameters + 3 Ws bindings
├── self_learning.json       # Dynamic 3 Ws memory ledger (What Worked, Failed, To Adapt)
└── (optional workflows)     # Workflow JSONs, scripts, or domain-specific templates
```

### Taxonomy Classification (`skills/skill-organizer/taxonomy.json`)
- **`meta-governance`**: `skill-organizer`, `self-learning-skill-creator`
- **`orchestration`**: `orchestrate`, `autopilot`, `behave-rules`, `tele-message`, `telegram`
- **`engineering`**: `architect`, `develop`, `test`, `debug`, `check`, `scope`, `audit`, `sync`, `document`
- **`browser-automation`**: `use-chrome`, `browser`
- **`generative-fashion`**: `virtual-tryon-lock`, `4-view-garment-sheet`, `dual-view-and-quad-details`, `editorial-pose-matrix`, `fashion-upscale-refine`, `luxury-catalog-copy`, `social-grid-syndication`, `video-turnaround-veo`
- **`infrastructure`**: `deployment-discipline`, `oci-vm-2-12`, `modal-qwen`, `tailscale`, `neon`

---

## 2. The 3 Ws Self-Learning Protocol

Every execution of any skill must update or consult the 3 Ws feedback loop:

1. **What Worked (`what_worked`)**:
   - Synthesizes validated prompts, exact parameter ranges (temperature, CFG, steps), positive conditioning tags, and proven execution sequences.
   - Prevents regressions and locks in high-quality configurations.

2. **What Failed (`what_failed`)**:
   - Explicitly records hallucinations, drift points, rate-limit triggers, broken paths, and incompatible node configurations.
   - Translates directly into negative prompt constraints or runtime assertion gates.

3. **What to Adapt (`what_to_adapt`)**:
   - Dynamic rules generated automatically from failures to prevent future errors.
   - Defines auto-healing adjustments, parameter compensations, and retry fallbacks.

---

## 3. Separation of Concerns & DRY Enforcement

- **Zero Duplication**: Skills do not restate overarching rules, logging mechanisms, or taxonomy. They state their domain-specific purpose and reference `skill-organizer`.
- **Contract Driven**: Prompts and inputs are strictly decoupled from code/workflow engines via standardized JSON contracts.
- **Idempotency & Isolation**: Every skill operates within explicit input/output boundaries without uncontrolled side effects.

---

## 4. Operational Commands for Agents
- Inspect taxonomy: Read `skills/skill-organizer/taxonomy.json`
- Consult 3 Ws rules: Read `skills/skill-organizer/protocol/3ws_self_learning_protocol.md`
- Scaffold a new skill: Invoke `self-learning-skill-creator`
