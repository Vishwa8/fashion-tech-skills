# Fashion Tech Platform Architecture & Self-Learning Engine

This repository serves as the persistent, self-learning knowledge and skill layer for automated fashion e-commerce advertising, virtual try-ons, 3D turnaround modeling, and video generation.

---

## 1. The 5-Tier Platform Ecosystem

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        1. APPLICATION LAYER                            │
│   • Webapp UI (Frontend for product uploads, catalog gallery & review) │
│   • Telegram Bot Interface (Instant notifications, tap-to-approve)     │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
┌───────────────────────────────────▼────────────────────────────────────┐
│                       2. ORCHESTRATION LAYER                           │
│   • n8n Engine (Modular event-driven pipelines, webhooks, sub-flows)   │
│   • Agent as the Brain (Vision QA gates, error correction, prompts)    │
└──────────────────┬─────────────────────────────────┬───────────────────┘
                   │                                 │
┌──────────────────▼──────────────────┐   ┌──────────▼───────────────────┐
│        3. INTELLIGENCE & ROUTING    │   │      4. COMPUTE & EXECUTION  │
│   • 9Router UI & Gateway            │   │   • Headless ComfyUI Engine  │
│     - Unified API key management    │   │     - Custom Nodes & Graphs  │
│     - Intelligent provider fallback │   │     - ControlNet / IP-Adapter│
│     - Cost & quota tracking         │   │   • Vertex AI / Veo Video API│
│     - Latency & rate-limit guards   │   │   • FFmpeg Post-Processing   │
└──────────────────┬──────────────────┘   └──────────┬───────────────────┘
                   │                                 │
┌──────────────────▼─────────────────────────────────▼───────────────────┐
│                     5. REPOSITORY & KNOWLEDGE TRUTH                    │
│   • fashion-tech-skills (Single source of truth: schemas, rules)       │
│   • Persistent "3 Ws" Learning Ledger (Self-evolving memory)          │
│   • S3 / MinIO / Local Object Store (Immutable asset URIs)             │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 2. The Persistent Self-Learning "3 Ws" Engine

AI models suffer from context evaporation. By using this Git repository as a persistent brain layer, every mistake, QA failure, and human correction compounds into hard, invariant software rules:

```text
                  ┌─────────────────────────────────────────┐
                  │         EXECUTION / GENERATION          │
                  │   (ComfyUI / Vertex AI / n8n Workflow)  │
                  └────────────────────┬────────────────────┘
                                       │
                                       ▼
                  ┌─────────────────────────────────────────┐
                  │           VISUAL QA / FEEDBACK          │
                  │   (Agent Inspector / Human Correction)  │
                  │   e.g. "shawl duplicated on both hips"  │
                  └────────────────────┬────────────────────┘
                                       │
                                       ▼
                  ┌─────────────────────────────────────────┐
                  │           3 Ws LESSON ENCODING          │
                  │   WHAT failed?                          │
                  │   WHEN does it trigger?                 │
                  │   WHY did it happen & how to prevent?   │
                  └────────────────────┬────────────────────┘
                                       │
                                       ▼
                  ┌─────────────────────────────────────────┐
                  │      PERSISTENT KNOWLEDGE UPDATED       │
                  │   1. Update SKILL.md (Negative Prompt,  │
                  │      Geometry Rules, Conditioning Logic)│
                  │   2. Append to lessons-learned.jsonl    │
                  │   3. Git Commit & Push to GitHub Repo   │
                  └─────────────────────────────────────────┘
```

### The "3 Ws" Data Contract
Whenever a new failure mode is resolved, it is appended to `lessons-learned.jsonl`:
- **WHAT**: Detailed geometric, structural, or textile defect (e.g., sliced sleeve cuffs, phantom duplicate hip cowl drapes, protruding mannequin neck hardware).
- **WHEN**: The precise prompt, aspect ratio, or garment cut conditions that trigger the defect (e.g., generating multi-angle views of an asymmetric single-shoulder pallu).
- **WHY**: The root cause in diffusion geometry (e.g., bilateral symmetry bias in U-Net/DiT architectures), paired with the exact negative prompt clause and structural constraint that eliminates it.

---

## 3. Skills Catalog

- **[`4-view-garment-sheet`](skills/4-view-garment-sheet/SKILL.md)**: Physical 3D turnaround modeling on pure white ghost mannequin with strict single-side asymmetric drape geometry.
- **[`dual-view-and-quad-details`](skills/dual-view-and-quad-details/SKILL.md)**: Decoupled master Front/Back split silhouette paired with 4-quadrant macro detail matrices for micro-texture ground truth.

---

## 4. Webapp & n8n Interoperability

Each skill in this repository is designed as a standalone, composable Lego block:
- **`SKILL.md`**: Theoretical prompt rules, negative constraints, and visual QA checklist.
- **`workflow.json`**: Headless ComfyUI node API graph executable via REST or WebSocket.
- **`n8n-node.json`**: Modular n8n sub-workflow definition accepting standardized JSON payloads from the Webapp UI.
