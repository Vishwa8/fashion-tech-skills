---
name: fashion-upscale-refine
description: Performs tile-based 4K high-resolution upscaling and detail refinement for fashion assets, enhancing micro-textures, metallic zari threads, and sequin reflections without introducing hallucinations or geometric distortion.
---

# Fashion 4K Upscale & Refinement Specification

## Purpose
This skill scales generation outputs to ultra-high-resolution print and e-commerce standards (3072x5504 or 4K/8K). It employs tiled latent diffusion and detail enhancement to crisply define fabric weave, zari sheen, and jewelry filigree without altering facial identity or silhouette proportions.

---

## Configuration Guidelines
- **Scale Factor**: 2x / 4x depending on target media.
- **Denoising Strength**: Strict conservative range (`0.15 - 0.25`) to avoid inventing foreign patterns or altering seam lines.
- **Tiling**: Tiled diffusion to eliminate GPU out-of-memory errors on large resolution canvases.
- **Preservation**: Strict facial and hand protection masks during high-pass detail enhancement.
