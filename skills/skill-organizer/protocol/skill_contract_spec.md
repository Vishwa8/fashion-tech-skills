# Universal Skill Contract Specification (SSOT)

This document defines the machine-executable JSON schema and validation rules for all `prompt_contract.json` files across the ecosystem.

---

## 1. Schema Definition

Every skill must maintain a root `prompt_contract.json` conforming to this layout:

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "contract_version": "1.0.0",
  "skill_id": "string (kebab-case)",
  "skill_name": "string",
  "category": "meta-governance | orchestration | engineering | browser-automation | generative-fashion | infrastructure",
  "governance_ref": "skills/skill-organizer/SKILL.md",
  "learning_ref": "skills/skill-organizer/protocol/3ws_self_learning_protocol.md",
  
  "task_metadata": {
    "description": "string",
    "primary_model": "string (e.g. gemini-3.1-flash-image, veo-3.1-generate-preview)",
    "execution_engine": "comfyui | n8n | api_direct | bash",
    "zero_waste_token_policy": true
  },

  "system_prompt": "string (Immutable role, precision criteria, operational posture)",

  "user_prompt_template": "string (Structured user directives with dynamic {{VARIABLES}})",

  "dynamic_variables": {
    "VARIABLE_NAME": {
      "type": "string | number | boolean | array",
      "description": "Meaning and source of variable",
      "default": "optional fallback"
    }
  },

  "negative_prompt_constraints": [
    "Array of prohibited artifacts, drift vectors, anatomy defects, or logic errors"
  ],

  "parameter_contracts": {
    "aspect_ratio": "1:1 | 3:4 | 9:16 | 16:9",
    "resolution": "string (e.g. 1024x1024, 2048x2048)",
    "temperature": "number (0.0 - 1.0)",
    "seed_lock": "boolean | integer"
  },

  "self_learning": {
    "engine": "3ws_framework",
    "active_rules_injected": [
      "Dynamic negative constraints inherited from what_to_adapt"
    ]
  }
}
```

---

## 2. Validation Constraints
1. **Dynamic Variables**: All placeholders formatted as `{{VARIABLE_NAME}}` in `user_prompt_template` must be declared in `dynamic_variables`.
2. **References**: `governance_ref` and `learning_ref` must point to `skill-organizer` paths to prevent rule fragmentation.
3. **Idempotence**: Contracts must be independently testable via mock JSON inputs.
