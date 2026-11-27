---
name: virtual-tryon-lock
description: Executes high-fidelity virtual try-on of garments onto canonical influencer base plates with 0.0000% character and environmental drift using the Lego-Brick atomic inpainting protocol with FLUX.1 Fill and Gemini/Nano Banana.
---

# Virtual Try-On Identity & Scene Lock Specification (Lego-Brick Inpainting Architecture)

## Purpose & Commercial Mandate
This skill governs the faithful transfer of complex couture garments and accessories onto locked canonical influencer base plates (`base_front.png`, `base_back.png`) with **mathematical 0.0000% character and scene drift**.

### The Commercial Zero-Drift Law
In luxury fashion e-commerce, consistency is the direct foundation of brand equity and customer trust. If the model's identity, facial features, skin tone, hair bun/parting, studio backdrop, or accessories drift between angles or products:
1. Customers immediately detect synthetic anomalies and abandon carts.
2. Product return rates surge due to visual expectation mismatch.
3. Brand perception degrades from luxury couture to unverified dropshipper.

---

## The Canonical SSOT Clean Base Plate Standard
To eliminate conflicting elements and ensure 100% cross-catalog consistency, **all products build upon the identical clean base plates**:
- **Front Master**: `base/base_front.png` (Front 0° view).
- **Back Master**: `base/base_back.png` (Back 180° turnaround view).

### Clean Canvas Requirements:
- **Try-On Friendly Neutral Garment**: Minimalist, form-fitting neutral cream/beige slip dress.
- **ZERO Preexisting Accessories**:
  - Naked collarbone & neckline (no necklaces, chokers, chains).
  - Naked earlobes (no earrings, studs, jhumkas).
  - Naked wrists and fingers (no bangles, bracelets, rings).
  - Naked waist (no belts, latkans, sashes).
- **Locked Hair & Identity**: Canonical Indian influencer features, right-side crisp parting, textured sleek low bun, natural warm olive skin with micro-pores.
- **Locked Scene**: Champagne pleated silk studio backdrop, neutral diffused commercial studio lighting.

---

## The Atomic "Lego-Brick" Layering Architecture

Rather than attempting monolithic diffusion generation (which hallucinates drapes, bleeds accessories into fabric, and alters unmasked features), garments and accessories are split into atomic layers and inpainted sequentially **like stacking Lego bricks**:

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        THE LEGO-BRICK STACK                           │
├────────────────────────────────────────────────────────────────────────┤
│  BRICK 6: Fine Jewelry (Bangles, Kadas, Rings on locked hands)         │
│     ▲                                                                  │
│  BRICK 5: Fine Jewelry (Matching Antique Gold Jhumkas on earlobes)     │
│     ▲                                                                  │
│  BRICK 4: Fine Jewelry (Kundan Choker / Collar on bare collarbones)    │
│     ▲                                                                  │
│  BRICK 3: Kamarbandh / Waist Belt (Locks drape to natural waistline)   │
│     ▲                                                                  │
│  BRICK 2: Pre-Draped Cowl Pallu / Dupatta (Left shoulder to right hip) │
│     ▲                                                                  │
│  BRICK 1: Base Anarkali Gown (Bodice, sleeves, kali skirt, back scoop) │
│     ▲                                                                  │
│  LAYER 0: Canonical SSOT Clean Base Plate (0 Accessories, Neutral Slip)│
└────────────────────────────────────────────────────────────────────────┘
```

### Sequential Stacking Procedure:
1. **Layer 0 (Base Plate)**: Start with the clean SSOT base plate (`base_front.png` / `base_back.png`).
2. **Brick 1 (Base Garment)**:
   - *Mask*: Bodice, arms, skirt bounds.
   - *Inpaint*: Piece 1 (Anarkali Gown) transferring deep imperial wine maroon faux georgette, vertical sequin pinstripes, and flared 16-kali skirt.
   - *Output*: Layer 1.
3. **Brick 2 (Drape / Pallu on Layer 1)**:
   - *Mask*: Left shoulder, diagonal torso, right hip.
   - *Inpaint*: Piece 2 (Pre-Draped Cowl Pallu) anchoring at left shoulder, cascading crescent cowl folds, and scalloped bead fringe.
   - *Output*: Layer 2.
4. **Brick 3 (Locking Belt on Layer 2)**:
   - *Mask*: 1.5-inch waistband region.
   - *Inpaint*: Piece 3 (Embroidered Kamarbandh Belt) locking the cowl drape cleanly at the natural waistline.
   - *Output*: Layer 3 (Complete 3-Piece Dressed Ensemble).
5. **Brick 4 (Necklace on Layer 3)**:
   - *Mask*: Bare collarbone/neck box.
   - *Inpaint*: Polki / Kundan choker cleanly onto bare skin without touching clothing.
6. **Brick 5 (Earrings on Layer 4)**:
   - *Mask*: Bare earlobes.
   - *Inpaint*: Matching antique gold jhumkas.
7. **Brick 6 (Wrists/Hands on Layer 5)**:
   - *Mask*: Forearms and wrists.
   - *Inpaint*: Traditional kadas and glass bangles onto anatomically locked fingers.

---

## Dual-Engine Selection: FLUX.1 Fill vs Gemini / Nano Banana

### Why Gemini / Nano Banana is NOT used for inpainting:
- Multimodal foundation models (Nano Banana / Gemini Flash Image) generate full images based on reference context, but **do not offer native pixel-locked binary inpainting out of the box**.
- Requesting an inpaint causes global latent perturbation, subtly morphing facial features, skin undertones, hair strands, and backdrop pleats.

### Why Open-Source FLUX.1 Fill (`FLUX.1 Fill [dev]`):
- **Pixel-Locked Precision**: Operates with explicit binary inpaint masks.
- **Mathematical 0.0000% Drift**: Every pixel outside the mask boundary is mathematically preserved bit-for-bit.
- **Extreme Textile Realism**: Seamless boundary fusion for sheer georgette, metallic zari threads, and sequin reflections.

### The Division of Responsibilities:
- **Gemini / Nano Banana**: Generates ghost mannequin 4-view sheets, 4-quadrant macro texture sheets, flatlays, and performs Vision QA validation.
- **FLUX.1 Fill (in ComfyUI)**: The surgical execution engine that stacks the atomic Lego bricks onto the base plate.

---

## Non-Negotiable Lock Matrix

```text
┌───────────────────────┬──────────────────────────────────────────┐
│ Feature               │ Enforcement                              │
├───────────────────────┼──────────────────────────────────────────┤
│ Face & Features       │ ZERO DRIFT: Exact jawline, nose, eyes    │
│ Hair & Styling        │ EXACT: Right-side part, textured low bun │
│ Skin Tone & Hands     │ UNCHANGED: Natural warm undertone, 5 fing│
│ Accessories & Jewelry │ MODULAR: Added as atomic Lego bricks     │
│ Studio Backdrop       │ LOCKED: Champagne pleated silk fabric    │
│ Garment Replacement   │ 100% FAITHFUL: Silhouette, zari, drapes  │
└───────────────────────┴──────────────────────────────────────────┘
```

---

## The "3 Ws" Persistent Failure Ledger

### INC-001: Face & Hairstyle Drift on Inpainting
- **WHAT**: The model subtly altered the influencer's hairline and softened facial features during full-body garment transfer.
- **WHEN**: Triggers when inpaint masks loosely overlap the neck or shoulder lines without explicit facial bounding anchors.
- **WHY**: Diffusion models attempt to harmonize unmasked context with new clothing colors. Remediation: Dilate mask downward from collarbones; reinforce "Preserve the exact same woman, face, skin tone, hair, expression" in the invariant prompt clause.

### INC-002: Multi-Piece Garment Entanglement on Monolithic Transfer
- **WHAT**: Cowl dupatta generated on both left and right hips simultaneously; waist belt dissolved into skirt pleats.
- **WHEN**: Attempting to transfer all 3 pieces of an ensemble in a single diffusion prompt.
- **WHY**: Diffusion models struggle with simultaneous multi-region asymmetric physics. Remediation: Mandate the Lego-Brick atomic layering sequence (Piece 1 Gown $\rightarrow$ Piece 2 Cowl Pallu $\rightarrow$ Piece 3 Kamarbandh $\rightarrow$ Accessories).
