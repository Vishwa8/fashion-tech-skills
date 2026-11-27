---
name: virtual-tryon-lock
description: Executes high-fidelity virtual try-on of garments onto canonical influencer base plates with 0.0000% character and environmental drift. Preserves exact face geometry, skin tone, hair parting/bun, hands, jewelry, and champagne pleated silk backdrop while transferring intricate garment embroidery, silhouettes, and drapes.
---

# Virtual Try-On Identity & Scene Lock Specification

## Purpose
This skill governs the faithful transfer of complex ethnic and luxury garments onto locked canonical influencer base plates (`base_front.png`, `base_back.png`). It enforces strict inpainting and prompt conditioning constraints to prevent identity drift, skin tone shifts, hand distortions, and background alterations.

---

## Non-Negotiable Lock Matrix

```text
┌───────────────────────┬──────────────────────────────────────────┐
│ Feature               │ Enforcement                              │
├───────────────────────┼──────────────────────────────────────────┤
│ Face & Features       │ ZERO DRIFT: Exact jawline, nose, eyes    │
│ Hair & Styling        │ EXACT: Right-side part, textured low bun │
│ Skin Tone & Hands     │ UNCHANGED: Natural warm undertone, 5 fing│
│ Accessories & Jewelry │ PRESERVED: Antique gold jhumkas, rings   │
│ Studio Backdrop       │ LOCKED: Champagne pleated silk fabric    │
│ Garment Replacement   │ 100% FAITHFUL: Silhouette, zari, drapes  │
└───────────────────────┴──────────────────────────────────────────┘
```

---

## Canonical Prompt Template

```text
Use the base image as the identity, pose, body, lighting, and scene source of truth. Replace only the masked model's garment with the uploaded garment reference keeping everything else the same.

Preserve the exact same woman, face, skin tone, hair, expression, jewelry, hands, pose, body proportions, camera angle, full-body framing, cream satin draped background, floor drape, and sandals.

Transfer the garment faithfully: [[GARMENT_SPECIFICATIONS]]

Do not change identity, hairstyle, background, lighting, composition, or accessories. Photorealistic fashion catalog image.
```

---

## ComfyUI Node Execution Graph
- Driven by `VishwaGeminiNanoBananaImage` or masked inpainting workflows.
- Input 1: `base_image` (Base influencer portrait).
- Input 2: `garment_reference` (Front/Back master or 4-quadrant detail sheet).
- Input 3: `mask` (Strict torso and skirt garment bounding box, excluding head, arms, jewelry, and background).
- Output: Photorealistic composite retaining 100% base identity.

---

## The "3 Ws" Persistent Failure Ledger

### INC-001: Face & Hairstyle Drift on Inpainting
- **WHAT**: The model subtly altered the influencer's hairline and softened facial features during full-body garment transfer.
- **WHEN**: Triggers when inpaint masks loosely overlap the neck or shoulder lines without explicit facial bounding anchors.
- **WHY**: Diffusion models attempt to harmonize unmasked context with new clothing colors. Remediation: Dilate mask downward from collarbones; reinforce "Preserve the exact same woman, face, skin tone, hair, expression" in the invariant prompt clause.
