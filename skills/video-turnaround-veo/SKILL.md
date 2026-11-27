---
name: video-turnaround-veo
description: Generates smooth, cinematic, slow-motion commercial fashion video loops using Google Veo 3.1. Enforces strict motion safety rules (no wild spins, no face morphing, no garment reinterpretation) with keyframe interpolation and camera motion controls.
---

# Video Turnaround & Motion Safety Specification (Google Veo 3.1)

## Purpose
This skill generates premium, photorealistic video clips and turnaround loops of the virtual influencer wearing the couture garment using Google's Veo 3.1 video generation API. It enforces strict physical motion boundaries to eliminate facial morphing, unrealistic textile warping, and camera jitter.

---

## Motion Safety Rules Engine

```json
{
  "motion_safety_rules": {
    "body_orientation": "Keep the model fully front-facing or extremely slight 3/4 front-facing only. Never rotate enough to reveal side profile or back details.",
    "turn_limit": "No spins, no full 360 rotations, no side reveal, no back-facing movement, no rear garment reveal in front clip.",
    "face_lock": "Keep the face identity stable and consistent in every frame using face_source_of_truth. No morphing, no expression drift, no facial structure change.",
    "garment_lock": "Do not redesign, reinterpret, or newly reveal unseen dress details. Keep the entire outfit visually identical to garment_source_of_truth.",
    "background_lock": "Keep the same champagne satin draped background style and arrangement from scene_source_of_truth.",
    "pose_lock": "Keep the same standing presentation and front-view posture from pose_source_of_truth, with only tiny natural motion.",
    "motion_style": "Use only very slow and subtle slow-motion: minimal breathing, slight posture settling, tiny hand relaxation, and faint hair movement."
  }
}
```

---

## Canonical Veo 3.1 Prompt Template

```text
Cinematic slow-motion luxury fashion commercial video of the South Asian woman wearing the deep wine maroon Anarkali gown. 

CAMERA & LIGHTING:
Smooth slow camera dolly-in with subtle upward tilt, high-end 3200K warm studio key light casting soft specular highlights on antique gold zari pinstripes and micro-sequins.

MODEL & GARMENT MOTION:
The model holds an elegant, poised standing posture facing the camera with minimal slow-motion settling. Subtle natural breathing motion, delicate finger relaxation, and faint sway of the circular skirt hem. The asymmetric cowl drape and hanging micro-bead fringe catch the light with subtle micro-movements.

ABSOLUTE RESTRICTIONS:
Strictly front-facing. Zero full spins or fast turns. Zero facial morphing, zero identity drift. Background remains stationary champagne pleated silk. 4K photorealistic broadcast fashion reel.
```

---

## The "3 Ws" Persistent Failure Ledger

### INC-003: Video Spin Causing Hallucinated Rear Garment
- **WHAT**: When prompted with "360-degree rotating model", Veo hallucinated a backless bodice and changed the neckline during the turn.
- **WHEN**: Triggers whenever a video model is asked to rotate through angles not explicitly defined in conditioning keyframes.
- **WHY**: Video diffusion models cannot maintain 3D hidden surface consistency without multi-view conditioning. Remediation: Never request a full 360° spin in a single prompt. Split into a Front Clip (subtle breathing/dolly), a Back Clip (subtle tassel movement), and cross-fade in post-processing.
