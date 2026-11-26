# Fashion Tech Skills

Specialized, production-grade AI engineering skills, schemas, and prompt specifications for virtual try-on, 3D garment turnaround modeling, automated catalog generation, and fashion e-commerce.

## Skills Catalog

### 1. [`4-view-garment-sheet`](skills/4-view-garment-sheet/SKILL.md)
Generates physically consistent, zero-defect 4-view garment reference sheets (Front 0°, 3/4 Turn 45°, Lateral Profile 90°, and Back 180°) on an invisible ghost mannequin on pure `#FFFFFF` background.
- **Enforces strict single-side drape geometry**: Prevents AI hallucinations such as duplicate drapes on both hips or disconnected shoulder wraps.
- **Natural ghost mannequin collar & sleeve integrity**: Prevents protruding neck stumps and black sliced cuff voids.
- **Anti-bleed interior shading**: Shaded inner cavities (`#3A3A3A-#5A5A5A`) to prevent pure white backdrop bleed-through.

---

## Directory Structure
```text
fashion-tech-skills/
├── README.md
├── .gitignore
└── skills/
    └── 4-view-garment-sheet/
        └── SKILL.md
```
