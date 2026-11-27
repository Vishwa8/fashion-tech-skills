# Fashion Tech Skills Catalog

An industrial-grade, persistent, self-learning skill repository and automation library for luxury fashion e-commerce, virtual try-ons, 3D turnaround modeling, and video generation.

---

## Skills Catalog

| Skill | Description | ComfyUI Workflow |
| :--- | :--- | :--- |
| **[`4-view-garment-sheet`](skills/4-view-garment-sheet/SKILL.md)** | Generates 4-view turnaround reference sheets on ghost mannequin with strict single-side drape geometry. | Integrated prompt template |
| **[`dual-view-and-quad-details`](skills/dual-view-and-quad-details/SKILL.md)** | Decouples full-body silhouette physics (Front/Back) from 4-quadrant micro-texture matrices. | High-res macro conditioning |
| **[`virtual-tryon-lock`](skills/virtual-tryon-lock/SKILL.md)** | Executes high-fidelity virtual try-on onto influencer base plates with 0.0000% character and scene drift. | [`Tryon.json`](skills/virtual-tryon-lock/workflow.json) |
| **[`editorial-pose-matrix`](skills/editorial-pose-matrix/SKILL.md)** | Generates 5 high-fashion editorial catalog poses from locked try-on masters without design or identity drift. | [`Pose Redesigned.json`](skills/editorial-pose-matrix/workflow.json) |
| **[`video-turnaround-veo`](skills/video-turnaround-veo/SKILL.md)** | Generates cinematic slow-motion commercial video loops using Google Veo 3.1 with motion safety controls. | [`Video.json`](skills/video-turnaround-veo/workflow.json) |
| **[`luxury-catalog-copy`](skills/luxury-catalog-copy/SKILL.md)** | Produces luxury brand storytelling, Amazon/Shopify bullet points, and 100-word invariant AI prompt descriptors. | [`Catalog Description.json`](skills/luxury-catalog-copy/workflow.json) |
| **[`social-grid-syndication`](skills/social-grid-syndication/SKILL.md)** | Produces editorial cover photos and mathematical 3x3 Instagram grid splits for campaign launches. | [`Grid Splitter.json`](skills/social-grid-syndication/workflow.json) |
| **[`fashion-upscale-refine`](skills/fashion-upscale-refine/SKILL.md)** | Performs 4K/8K tiled latent upscaling and detail refinement for fabric weaves, metallic zari, and sequins. | [`Upscale.json`](skills/fashion-upscale-refine/workflow.json) |

---

## Platform Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for full details on the 5-tier architecture connecting:
1. **Webapp UI**: Client-facing portal (`apps/studio`).
2. **n8n Orchestration Engine**: Headless event-driven workflow automation.
3. **9Router Gateway**: Centralized API keys, multi-model routing, and rate-limit guards.
4. **ComfyUI Custom Nodes (`vishwa`)**: Local latent diffusion, Google Gemini API, and Veo video execution.
5. **Self-Learning "3 Ws" Engine**: Persistent knowledge and failure ledger.
