# AI Video Creation Pipeline 🎬

> **Turn a single photo into a cinematic AI-generated Instagram reel — fully prompt-driven, no code required.**

[![AI Powered](https://img.shields.io/badge/AI-Powered-blueviolet?logo=openai&logoColor=white)](#)
[![Format](https://img.shields.io/badge/Format-9%3A16_Reel-E4405F?logo=instagram&logoColor=white)](#)
[![Stars](https://img.shields.io/github/stars/kodelyx/ai-video-creation?style=social)](https://github.com/kodelyx/ai-video-creation/stargazers)

---

## Pipeline Overview

![Pipeline Flow](pipeline.png)

| Step | You Provide | Prompt File Used | AI Generates |
|:----:|:------------|:-----------------|:-------------|
| 1 | Your photo (`dp1.png`) | [`image_to_character_prompt.txt`](image_to_character_prompt.txt) | Character identity sheet |
| 2 | Character sheet + reel idea | [`storyboard_Image_planner_prompt.txt`](storyboard_Image_planner_prompt.txt) | 6-panel cinematic storyboard |
| 3 | Storyboard image | [`storyboard_Image_to_video_prompt.txt`](storyboard_Image_to_video_prompt.txt) | Production-ready video prompt |
| 4 | Video prompt + character ref | Your AI video tool (Kling/Runway/Veo) | Final 9:16 reel |

---

## Live Demo — Actual Pipeline Output

Every image and video below was generated using this pipeline.

### Step 1 → Reference Photo

This is the **only real photo** in the entire pipeline. Everything else is AI-generated from this single image.

> **Input:** One selfie/portrait photo  
> **Prompt:** [`image_to_character_prompt.txt`](image_to_character_prompt.txt)

![Reference Photo — dp1.png](dp1.png)

---

### Step 2 → Character Identity Sheet

The AI analyzes the reference photo and generates a detailed **identity lock sheet** — cataloging face shape, eyes, skin tone, hair, expression, makeup, clothing, and accessories. This sheet ensures the same face appears consistently across all future generations.

> **Input:** `dp1.png`  
> **Prompt:** [`image_to_character_prompt.txt`](image_to_character_prompt.txt)  
> **Output:** `character_sheet.png`

![Character Sheet — Identity Lock Reference](character_sheet.png)

The bottom strip shows **Consistency Priority (High → Low):** Face Shape → Eyes → Eyebrows → Nose → Lips → Hairline → Hairstyle → Skin Tone → Accessories

---

### Step 3 → Cinematic Storyboard

Using the character sheet and a reel concept (product promo, song lip-sync, lifestyle, etc.), the AI creates a **6-panel storyboard** with scene titles, descriptions, camera angles, mood, and color palette.

> **Input:** `character_sheet.png` + reel concept  
> **Prompt:** [`storyboard_Image_planner_prompt.txt`](storyboard_Image_planner_prompt.txt)  
> **Output:** `storyboard_Image.png`

![Storyboard — 6-Panel Cinematic Layout](storyboard_Image.png)

Each panel includes: **Scene title** · **Action description** · **Camera style** (Macro Close-Up, Medium Shot, Tight Portrait, Handheld Lifestyle, Product Detail, Hero Shot)

---

### Step 4 → Final Video

The storyboard is converted into a **timestamped video generation prompt** with lip-sync, physics lock, camera direction, and negative rules — then fed to an AI video generator.

> **Input:** `storyboard_Image.png`  
> **Prompt:** [`storyboard_Image_to_video_prompt.txt`](storyboard_Image_to_video_prompt.txt)  
> **Output:** `Finally_Video.mp4`

![Final Output — AI Generated Reel](demo.gif)

---

## How Each Prompt Works

### `image_to_character_prompt.txt`
Analyzes a reference photo and creates a professional **Character Sheet (Identity Lock Version)** with:
- Face analysis (shape, jawline, chin, eyes, nose, lips)
- Skin, hair, expression, makeup, clothing breakdown
- Bottom detail boxes (Expression, Makeup, Clothing, Accessories, Pose, Lighting, Camera, Identity Keywords)
- Consistency priority strip for future generation consistency

### `storyboard_Image_planner_prompt.txt`
Takes the character sheet + your reel concept and:
1. Analyzes character identity, outfit, mood, and aesthetic
2. Suggests a reel base (type, mood, scene style, action, format)
3. Asks for your approval before generating
4. Creates a **3×2 storyboard sheet** with 6 labeled scenes, camera styles, direction notes, mood/tone, and color palette

### `storyboard_Image_to_video_prompt.txt`
Converts the storyboard into a **production-ready video prompt** with:
- Scene-by-scene timestamps (0.0–1.5s, 1.5–3.0s, etc.)
- Camera styles per scene (macro, portrait, handheld, hero shot)
- Auto-generated Hindi dialogue in Devanagari
- Physics Lock rules (no floating objects, correct hand anatomy, 5 fingers)
- Negative rules (no cartoon, no 3D, no distortion, no watermarks)

### `ai_influencer_prompt.txt`
**Shortcut prompt** — skip the full pipeline. Uses reference image + character sheet directly to generate a lip-synced Hindi dialogue video. Just swap the dialogue section for each new video. Identity lock stays the same.

---

## Compatible AI Tools

| Tool | Best For | Use With |
|:-----|:---------|:---------|
| **Kling AI** | Lip-sync + identity consistency | Video generation (Step 4) |
| **Runway Gen-3** | Cinematic motion quality | Video generation (Step 4) |
| **Google Veo** | Photorealism | Video generation (Step 4) |
| **Luma Dream Machine** | Fast iterations | Video generation (Step 4) |
| **ChatGPT / Gemini** | Image generation | Character sheet + Storyboard (Steps 1-3) |
| **Midjourney** | High-quality images | Character sheet (Step 1) |

---

## Files

| File | What It Does |
|:-----|:-------------|
| `dp1.png` | Source identity photo |
| `character_sheet.png` | AI-generated identity lock sheet |
| `storyboard_Image.png` | 6-panel cinematic storyboard |
| `demo.gif` | Final output preview (animated) |
| `Finally_Video.mp4` | Final output (full quality) |
| `image_to_character_prompt.txt` | Photo → Character Sheet prompt |
| `storyboard_Image_planner_prompt.txt` | Character Sheet → Storyboard prompt |
| `storyboard_Image_to_video_prompt.txt` | Storyboard → Video Prompt generator |
| `ai_influencer_prompt.txt` | Direct video generation shortcut |

---

## Contributing

Found better prompt techniques? PRs welcome.

```
git checkout -b improve-prompt
git commit -m "improve: better physics lock rules"
git push origin improve-prompt
```

---

⭐ **Star this repo** if it saved you hours of prompt engineering.
