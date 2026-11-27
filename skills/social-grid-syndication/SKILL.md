---
name: social-grid-syndication
description: Produces high-engagement social media assets, editorial cover photos, and precise 3x3 Instagram grid splits from catalog photography for unified campaign rollouts.
---

# Social Media Grid & Cover Photo Syndication Specification

## Purpose
This skill adapts high-resolution master catalog photography into high-converting social media distribution formats:
- **Cover Photos**: High-impact editorial portrait framing optimized for catalog thumbnails, reels covers, and hero banners.
- **3x3 Seamless Instagram Grid**: Mathematical 9-tile grid slicing with seamless edge alignment across 1080x1080 square tiles.
- **Story & Carousel Formats**: 9:16 vertical stories with dynamic zoom crops on intricate bodice embroidery and hem sweeps.

---

## 3x3 Grid Matrix Configuration

```text
┌─────────────┬─────────────┬─────────────┐
│ [Tile 1]    │ [Tile 2]    │ [Tile 3]    │
│ Top Left    │ Top Center  │ Top Right   │
├─────────────┼─────────────┼─────────────┤
│ [Tile 4]    │ [Tile 5]    │ [Tile 6]    │
│ Mid Left    │ Mid Center  │ Mid Right   │
├─────────────┼─────────────┼─────────────┤
│ [Tile 7]    │ [Tile 8]    │ [Tile 9]    │
│ Bottom Left │ Bottom Mid  │ Bottom Right│
└─────────────┴─────────────┴─────────────┘
```

---

## ComfyUI Node Execution
- Driven by `Grid Splitter.json` and `Cover Photo.json`.
- Automatically calculates coordinate slicing, preserving razor-sharp tile boundaries without compression artifacts.
