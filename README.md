# Fashion Tech Skills Catalog

An industrial-grade, persistent, self-learning skill repository and automation library for luxury fashion e-commerce, virtual try-ons, 3D turnaround modeling, and video generation.

---

## Skills Catalog

| Skill | Category | Description | Artifacts |
| :--- | :--- | :--- | :--- |
| **[`skill-organizer`](skills/skill-organizer/SKILL.md)** | `meta-governance` | Universal taxonomy SSOT, contract schemas, & 3 Ws self-learning protocol. | `SKILL.md`, `taxonomy.json`, `protocol/` |
| **[`self-learning-skill-creator`](skills/self-learning-skill-creator/SKILL.md)** | `meta-governance` | Scaffolds & registers new modular skills adhering strictly to `skill-organizer`. | `SKILL.md`, `prompt_contract.json`, `self_learning.json` |
| **[`4-view-garment-sheet`](skills/4-view-garment-sheet/SKILL.md)** | `generative-fashion` | Generates 4-view turnaround reference sheets on ghost mannequin with strict single-side drape geometry. | `SKILL.md`, `prompt_contract.json`, `self_learning.json` |
| **[`dual-view-and-quad-details`](skills/dual-view-and-quad-details/SKILL.md)** | `generative-fashion` | Decouples full-body silhouette physics (Front/Back) from 4-quadrant micro-texture matrices. | `SKILL.md`, `prompt_contract.json`, `self_learning.json` |
| **[`virtual-tryon-lock`](skills/virtual-tryon-lock/SKILL.md)** | `generative-fashion` | Executes high-fidelity virtual try-on onto influencer base plates with 0.0000% character and scene drift. | [`Tryon.json`](skills/virtual-tryon-lock/workflow.json), `prompt_contract.json`, `self_learning.json` |
| **[`editorial-pose-matrix`](skills/editorial-pose-matrix/SKILL.md)** | `generative-fashion` | Generates 5 high-fashion editorial catalog poses from locked try-on masters without design or identity drift. | [`Pose Redesigned.json`](skills/editorial-pose-matrix/workflow.json), `prompt_contract.json`, `self_learning.json` |
| **[`video-turnaround-veo`](skills/video-turnaround-veo/SKILL.md)** | `generative-fashion` | Generates cinematic slow-motion commercial video loops using Google Veo 3.1 with motion safety controls. | [`Video.json`](skills/video-turnaround-veo/workflow.json), `prompt_contract.json`, `self_learning.json` |
| **[`luxury-catalog-copy`](skills/luxury-catalog-copy/SKILL.md)** | `generative-fashion` | Produces luxury brand storytelling, Amazon/Shopify bullet points, and 100-word invariant AI prompt descriptors. | [`Catalog Description.json`](skills/luxury-catalog-copy/workflow.json), `prompt_contract.json`, `self_learning.json` |
| **[`social-grid-syndication`](skills/social-grid-syndication/SKILL.md)** | `generative-fashion` | Produces editorial cover photos and mathematical 3x3 Instagram grid splits for campaign launches. | [`Grid Splitter.json`](skills/social-grid-syndication/workflow.json), `prompt_contract.json`, `self_learning.json` |
| **[`fashion-upscale-refine`](skills/fashion-upscale-refine/SKILL.md)** | `generative-fashion` | Performs 4K/8K tiled latent upscaling and detail refinement for fabric weaves, metallic zari, and sequins. | [`Upscale.json`](skills/fashion-upscale-refine/workflow.json), `prompt_contract.json`, `self_learning.json` |

---

## Platform Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for full details on the 5-tier architecture connecting:
1. **Webapp UI**: Client-facing portal (`apps/studio`).
2. **n8n Orchestration Engine**: Headless event-driven workflow automation.
3. **9Router Gateway**: Centralized API keys, multi-model routing, and rate-limit guards.
4. **ComfyUI Custom Nodes (`vishwa`)**: Local latent diffusion, Google Gemini API, and Veo video execution.
5. **Self-Learning "3 Ws" Engine**: Persistent knowledge and failure ledger.
