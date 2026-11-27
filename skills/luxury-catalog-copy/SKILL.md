---
name: luxury-catalog-copy
description: Generates high-converting luxury editorial catalog copy, e-commerce bullet points, Amazon/Shopify SEO descriptions, and precise AI generation prompt descriptors from raw garment imagery and specifications.
---

# Luxury Fashion Catalog & Copywriting Specification

## Purpose
This skill extracts visual and physical attributes from garment references and generates multi-tiered copywriting assets:
1. **Luxury Brand Editorial Copy**: Evocative storytelling for lookbooks, Instagram captions, and high-fashion PR.
2. **E-Commerce Conversion Copy**: Structured Amazon/Shopify bullet points, fabric care details, and styling recommendations.
3. **100-Word Invariant Prompt Descriptors**: Standardized technical descriptors injected into downstream diffusion pipelines.

---

## Output Architecture

```text
┌───────────────────────────────────┬───────────────────────────────────┐
│ Section                           │ Output Format                     │
├───────────────────────────────────┼───────────────────────────────────┤
│ 1. Editorial Product Title        │ High-luxury regal nomenclature    │
│ 2. Haute Couture Narrative        │ 150-word evocative storytelling   │
│ 3. Technical Specifications       │ Fabric, weave, lining, closures   │
│ 4. 5 High-Conversion Bullet Points│ Bulleted feature-benefit copy     │
│ 5. AI Invariant Descriptor        │ Exact 100-word prompt string      │
└───────────────────────────────────┴───────────────────────────────────┘
```

---

## Canonical Generation Directive
- Extract the exact primary hex and accent hex shades.
- Classify the silhouette, necklines, sleeve cuts, panel divisions, and closures.
- Identify metallic embroidery styles (zari, zardozi, sitara sequins, cut-dana, threadwork).
- Frame the heritage and modern craftsmanship with royal Indian couture elegance.
