---
name: dual-view-and-quad-details
description: Generates a master Front & Back side-by-side full-body split view paired with 4-quadrant macro detail sheets (Front & Back) on an invisible ghost mannequin. Captures full-body silhouette physics while delivering ultra-high-resolution macro textures (necklines, embroidery pinstripes, cowl beads, dori tie tassels) for downstream virtual try-on, turnaround modeling, and video conditioning.
---

# Dual-View & 4-Quadrant Macro Detail Specification

## Purpose
Instead of compressing 4 figures into a cramped low-resolution strip, this skill decouples **global full-body silhouette & drape physics** from **micro-texture resolution**:
1. **Master Split Sheet**: Front View (0°) | Back View (180°) Side-by-Side (4:3 aspect ratio).
2. **Front 4-Quadrant Macro Sheet**: 2×2 grid (1:1 ratio) capturing the front neckline, shoulder anchor, sleeve tailoring, waistband, cowl beads, and hem sweep.
3. **Back 4-Quadrant Macro Sheet**: 2×2 grid (1:1 ratio) capturing the rear shoulder transition, rear sleeve tailoring, scoop back neckline with dori knot & tiered latkan tassels, and rear skirt kalis.

---

## 1. Master Split View Architecture (`garment_front_back_master.png`)

```text
+-------------------------------+-------------------------------+
|       LEFT PANEL: FRONT (0°)  |      RIGHT PANEL: BACK (180°) |
|   - Full-body standing        |   - Full-body standing        |
|   - Curved square neckline    |   - Deep scoop back neckline  |
|   - Asymmetric cowl drape     |   - Dori tie & latkan tassels |
|   - Circular 16-kali flare    |   - Clean, smooth kalis flare |
+-------------------------------+-------------------------------+
```

### Non-Negotiable Rules
- **Single-Side Drape**: The asymmetric pleated cowl originates on the wearer's left shoulder (viewer's right in front) and wraps to the wearer's right hip (viewer's left in front). In the rear view (180°), the drape rests on the viewer's left shoulder and flows naturally along that side—**zero phantom vertical curtains or duplicate drapes**.
- **Ghost Mannequin**: Completely hollow neck opening with interior lining cavity depth (`#3A3A3A-#5A5A5A`). Zero neck cylinders or pegs.

---

## 2. Front 4-Quadrant Macro Matrix (`garment_front_quad_details.png`)

```text
+-------------------------------+-------------------------------+
| [TOP-LEFT]                    | [TOP-RIGHT]                   |
| Front Neckline & Shoulder     | Bodice & Sleeve Embroidery    |
| - Curved square collar piping | - Vertical zari pinstripes    |
| - Pleated cowl shoulder anchor| - Micro-sequin stitch density |
| - Hollow ghost lining depth   | - Tailored sleeve cuff & seam |
+-------------------------------+-------------------------------+
| [BOTTOM-LEFT]                 | [BOTTOM-RIGHT]                |
| Waistband & Cowl Bead Droplets| Circular Kalis & Hem Sweep    |
| - 1.5-inch embellished band   | - Vertical kali panel seams   |
| - Layered crescent cowl swags | - Fluid georgette drape folds |
| - Scalloped gold bead fringe  | - Floor pooling contact shadow|
+-------------------------------+-------------------------------+
```

---

## 3. Back 4-Quadrant Macro Matrix (`garment_back_quad_details.png`)

```text
+-------------------------------+-------------------------------+
| [TOP-LEFT]                    | [TOP-RIGHT]                   |
| Rear Shoulder Seam Transition | Rear Sleeve & Armhole         |
| - Shoulder strap construction | - Vertical zari pinstripes    |
| - Natural shawl drape resting | - Tailored sleeve cuff        |
| - Clean seam piping           | - Clean armhole tailoring     |
+-------------------------------+-------------------------------+
| [BOTTOM-LEFT]                 | [BOTTOM-RIGHT]                |
| Scoop Neckline & Latkan Knot  | Rear Skirt Kalis & Hem        |
| - Deep scoop/square collar    | - Flared vertical kali seams  |
| - Dori tie knot in center     | - Pure wine maroon texture    |
| - Tiered antique gold tassels | - Wide circular hem sweep     |
+-------------------------------+-------------------------------+
```

---

## Downstream Model Conditioning Protocol
When prompting virtual try-on, catalog poses, or Veo video generation:
- **Global Anchor**: Feed `garment_front_back_master.png` as the primary structural reference for figure height, pose, drape direction, and full-length proportions.
- **Texture Ground Truth**: Feed `garment_front_quad_details.png` and `garment_back_quad_details.png` to eliminate hallucinated embroidery patterns, blurry tassels, or missing bead trims.
