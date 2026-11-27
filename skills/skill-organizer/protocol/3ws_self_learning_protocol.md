# The 3 Ws Self-Learning Protocol (Single Source of Truth)

This document specifies the standard feedback, adaptation, and continuous improvement protocol for all skills in the ecosystem. No skill redefines this protocol; skills reference and implement it.

---

## 1. The 3 Ws Architecture

Every autonomous or human-guided run of a skill must capture three vectors of operational intelligence:

```json
{
  "self_learning": {
    "engine_version": "1.0.0",
    "protocol_ref": "skills/skill-organizer/protocol/3ws_self_learning_protocol.md",
    "what_worked": [
      {
        "pattern_id": "WW-01",
        "description": "Clear description of successful prompt, hyperparameter, or execution flow",
        "positive_anchors": ["key terms", "parameters", "seed ranges"],
        "confidence_score": 0.98
      }
    ],
    "what_failed": [
      {
        "failure_id": "WF-01",
        "failure_mode": "Hallucination, drift, schema mismatch, or execution crash",
        "root_cause": "Exact analysis of why the step failed",
        "drift_vector": "e.g., character identity drift, neckline bleeding"
      }
    ],
    "what_to_adapt": [
      {
        "adaptation_id": "WA-01",
        "target_component": "prompt_contract.json | execution_guardrails | parameter_contract",
        "rule_addition": "Exact negative constraint or parameter clamping to prevent future failures",
        "status": "active"
      }
    ]
  }
}
```

---

## 2. Dynamic Learning Lifecycle

### Phase 1: Pre-Flight Prior Consultation
Before executing any generation or task, the agent inspects `self_learning.json` and the skill's `prompt_contract.json`:
1. Injects all active `what_worked` positive anchors into prompt directives.
2. Injects all active `what_to_adapt` rules into the negative constraints.
3. Clamps parameters to boundaries that avoided previous `what_failed` triggers.

### Phase 2: Post-Flight Drift & Quality Audit
Immediately following task execution:
1. **Compare output against acceptance criteria**:
   - For image/video: Check character identity, garment physics, seam integrity, and background fidelity.
   - For code/prompts: Check schema adherence, syntax validity, and token budget.
2. If successful $\rightarrow$ Record winning prompt/seed/parameters into `what_worked`.
3. If defective $\rightarrow$ Record root cause into `what_failed` and formulate a new defensive rule in `what_to_adapt`.

---

## 3. Strict Rules
- **No Manual Duplication**: Child skills do not write custom learning engines.
- **Append-Only Memory**: Do not delete prior lessons unless proven obsolete by schema major version increments.
- **Actionable Assertions**: Every `what_to_adapt` entry must translate directly into machine-testable conditions or negative prompt tokens.
