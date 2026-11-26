---
name: 4-view-garment-sheet
description: Generates physically consistent, zero-defect 4-view garment reference sheets (Front, 3/4 Angle, Profile, Back) on an invisible ghost mannequin for virtual try-on, turnaround modeling, and video conditioning. Enforces strict single-side drape geometry, natural finished necklines/shoulders, and anti-bleed protocols.
---

# 4-View Garment Reference Sheet Specification

## Purpose
This skill creates production-grade, 4-view garment turnaround reference sheets in a single horizontal layout on a pure white `#FFFFFF` studio background. It ensures 100% physically consistent 3D geometry across all views without AI hallucinations or duplicate drapes.

## The 4 Canonical Views (Single Horizontal Row)
1. **View 1: Front View (0°)**:
   - Full-body standing perspective.
   - Symmetrical or asymmetrical bodice construction.
   - If asymmetrical cowl/shawl exists, it originates on **one shoulder only** (e.g., wearer's left / viewer's right) and crosses diagonally to the opposite hip into fluid crescent folds with bead droplets.
2. **View 2: 3/4 Angle View (45°)**:
   - Three-quarter angle showing the **smooth/undraped side** of the dress.
   - Shows fitted bodice, vertical sequin/embroidery stripes, and full flared skirt kalis.
   - **Crucial Rule**: NEVER duplicate the heavy cowl drape on this side. It must be clean.
3. **View 3: Lateral Profile View (90°)**:
   - Direct profile showing the side where the cowl drape falls.
   - Highlights the depth, cascade, and fluid crescent folds of the drape along that side only.
4. **View 4: Back View (180°)**:
   - Full rear view.
   - Shows clean scoop/square back neckline with functional dori tie cords and handcrafted gold latkan bell tassels.
   - The shawl/cowl wraps cleanly over the **single designated shoulder only** and drapes naturally behind/around without creating a phantom duplicate drape on the other side.
   - Clean circular hem sweep and back kalis flare.

## Non-Negotiable Hard Constraints

### 1. 3D Asymmetry & Single-Side Drape Lock
- When a garment features an attached cowl, shawl, pallu, or dupatta, it belongs to **ONE SINGLE SHOULDER and ONE HIP ONLY**.
- **Forbidden**: Placing crescent cowl drapes on both left and right hips simultaneously (View 2 and View 3 must never both show heavy draped swags). One side is draped; the opposite side is smooth and tailored.

### 2. Natural Ghost Mannequin & Collar Integrity
- **No Protruding Hardware**: Zero mannequin neck stumps, wooden pegs, chrome stands, or cylinder posts protruding above or inside the collar.
- **Solid Continuous Seams**: Shoulder seams, collar curves, and strap edges must be continuous, fully sewn, intact fabric. Never slice or hollow out shoulder fabric with jagged white cutouts.
- **Interior Cavity**: The hollow interior opening is shaded with soft, deep charcoal-grey tones (`#3A3A3A-#5A5A5A`) defining structural 3D volume, with pure `#FFFFFF` background around the exterior.

### 3. Background & Grounding
- Pure `#FFFFFF` studio backdrop (RGB: 255, 255, 255) with zero gradient or color bleed.
- Subtle soft contact drop shadows under the sweeping hem to ground the figures at an identical baseline.

### 4. Fabric & Textile Fidelity
- Color: Deep imperial wine maroon (`#4A0E17`).
- Fabric: Heavy premium faux georgette / raw silk with visible micro-weave and fluid vertical drape.
- Embroidery: Vertical pinstripes of antique gold metallic zari threadwork and micro-sequins spaced 0.5 inches apart across bodice and matching waistband.
- Hemline: Wide circular kalis flare pooling naturally at floor level.

## Prompt Architecture Template (One-Shot Perfect Generation)
```text
A professional garment reference sheet isolated on pure white #FFFFFF background in a single horizontal row showing four full-body standing views: Front View, 3/4 Angle View, Profile View, and Back View on an invisible ghost mannequin.

STRUCTURAL LOCK:
The garment construction, seam placement, closure placement, neckline geometry, sleeve volume, waist position, hem width, tier placement, panel divisions, and silhouette proportions must match the reference image exactly.

3D ASYMMETRIC DRAPE GEOMETRY (SINGLE-SIDE RULE):
The asymmetric pleated cowl dupatta/shawl is attached to ONE SINGLE SHOULDER ONLY (wearer's left shoulder) and drapes across to ONE HIP ONLY (wearer's right hip).
- View 1 (Front View): Pleated shawl originates at wearer's left shoulder, crosses diagonally under the waistband, and drapes into fluid crescent cowl folds with scalloped gold trim and hanging micro-bead droplets over the wearer's right hip.
- View 2 (3/4 Angle View): Displays the clean, smooth, undraped opposite side of the gown, showing the fitted bodice with vertical sequin stripes and flared circular kalis skirt WITHOUT any cowl drape.
- View 3 (Profile View): Profile perspective of the draped hip showcasing the dimensional crescent cowl swags.
- View 4 (Back View): Rear view showing the shawl resting cleanly over the wearer's left shoulder and cascading naturally down that side. The opposite rear side is smooth and flared. The center back features a clean deep scoop back neckline with dual dori tie strings and tiered antique gold latkan bell tassels.
The AI is strictly forbidden from duplicating the cowl drape on both hips.

COLLAR & GHOST MANNEQUIN INTEGRITY:
True invisible ghost mannequin. Shoulder seams and neckline edges must be solid, continuous, smoothly tailored fabric with NO jagged cutouts, holes, or missing cloth. There is absolutely NO visible mannequin neck cylinder, stand, post, or peg protruding above or inside the neckline opening. The interior neck cavity is rendered with deep charcoal-grey tones (#3A3A3A-#5A5A5A) to define 3D volume against the pure white #FFFFFF background.

GARMENT SPECIFICATIONS:
- Base: Deep imperial wine maroon (#4A0E17) premium heavy faux georgette.
- Bodice: Curved square front neckline, elbow-length half sleeves, vertical antique gold zari and micro-sequin pinstripes. Matching 1.5-inch embellished waistband.
- Skirt: Voluminous 16-kali flared circular skirt pooling naturally at floor level.

Single horizontal row, 1376x768 (Landscape 1K), photorealistic DSLR studio catalog quality, diffuse lighting, grounding floor contact shadows.
```
