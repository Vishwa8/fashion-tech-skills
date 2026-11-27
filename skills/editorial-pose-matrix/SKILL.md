---
name: editorial-pose-matrix
description: Generates high-fashion editorial catalog poses (Front 3/4 turn, dynamic movement, close-up crop, seated elegance, rear silhouette) from locked try-on masters without altering identity, garment details, or studio lighting.
---

# Editorial Pose Matrix Specification

## Purpose
This skill produces a cohesive 5-shot e-commerce catalog editorial series from a locked virtual try-on master image. It applies standardized camera angles, focal lengths, and model postures while guaranteeing that the garment design, colors, embroidery, and model identity remain 100% consistent across all shots.

---

## The 5 Canonical Catalog Poses

```text
┌─────────┬──────────────────────┬─────────────┬──────────────────────────────┐
│ Shot ID │ Pose Type            │ Camera Shot │ Primary Focus                │
├─────────┼──────────────────────┼─────────────┼──────────────────────────────┤
│ POSE_01 │ Front Standing (0°)  │ Full Body   │ Full silhouette, length, hem │
│ POSE_02 │ Front 3/4 Turn (45°) │ Full/Cowboy │ Drape depth, side kali flare │
│ POSE_03 │ Bodice Macro Close-Up│ Medium-Close│ Neckline zari, sequin density│
│ POSE_04 │ Dynamic Walking Turn │ Full Body   │ Fluid fabric motion, flare   │
│ POSE_05 │ Rear Silhouette(180°)│ Full Body   │ Back neckline, latkan tassels│
└─────────┴──────────────────────┴─────────────┴──────────────────────────────┘
```

---

## Canonical Prompt Template

```text
Use image 1 as the identity, garment, body, lighting, and scene source of truth. Replace only the model's pose and camera angle with the pose specified below, keeping everything else strictly the same.

Preserve the exact same woman, face, skin tone, hair parting and bun, jewelry, hands, body proportions, cream satin draped background, floor drape, and sandals.
Preserve the exact garment details: deep wine maroon fabric, vertical antique gold zari and micro-sequin pinstripes, asymmetric cowl drape on the wearer's right hip, and flared circular skirt.

Transfer the pose and camera angle faithfully: [[POSE_AND_CAMERA_DIRECTIVE]]

Do not change identity, hairstyle, garment construction, background, lighting, or accessories. Photorealistic high-fashion catalog photography.
```

---

## The "3 Ws" Persistent Failure Ledger

### INC-002: Pose Re-interpretation Altering Garment Construction
- **WHAT**: During a dynamic walking pose, the model extended the gown into an open slit skirt and removed the shoulder cowl.
- **WHEN**: Triggers when prompt focuses excessively on motion dynamics ("swirling skirt", "high leg stride").
- **WHY**: Text-to-image models over-index on action verbs at the expense of structural constraints. Remediation: Mandate static structural locks ("closed flared 16-kali skirt, single-shoulder cowl anchored to hip, floor-length sweep") alongside motion descriptors.
