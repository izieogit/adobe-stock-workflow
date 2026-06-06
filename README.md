# adobe-stock-workflow
AI-powered Adobe Stock upload workflow — prompts, evaluation, metadata, and duplicate prevention for solo creators.

A personal Claude-based workflow for creating and publishing AI-generated images to **Adobe Stock**.  
Covers everything from prompt generation to upload — built for solo creators using ChatGPT (DALL·E) and Midjourney (via Nanobana).

---

## Features

- Dual prompt generation — ChatGPT and Midjourney prompts written side by side, with Korean translations
- Image evaluation checklist — quality, legal compliance, and cultural accuracy (Korean vs. Chinese vs. Japanese style)
- Similarity detection — prevents near-duplicate uploads that risk account suspension
- Metadata generation — English title + up to 49 keywords, formatted for Adobe Stock search ranking
- Upload checklist — AI labeling, resolution, format, watermark removal, and more
- Upload registry — tracks completed images to avoid redundant subjects

---

## How It Works

```
1. Topic Planning     →  Registry conflict check + seasonal timing
2. Prompt Generation  →  ChatGPT (DALL·E) + Midjourney (Nanobana) dual prompts
3. Image Evaluation   →  Quality, legal, and cultural accuracy check
4. Upscale Decision   →  Recommended only for images with simple, flat areas
5. Metadata Writing   →  Title + keywords + category (after upscale is confirmed)
6. Upload & Registry  →  Checklist sign-off → registry entry
```

> Metadata is written **after** upscale confirmation — not before — to ensure it matches the final uploaded image.

---

## Prompt Structure

All prompts are provided in **English + Korean translation**.

### ChatGPT (DALL·E) — Required phrases

```
No watermark, no logo, no text, no signage anywhere.
No people visible.
Landscape orientation, minimum 3000 pixels long edge, 4MP or above.
Professional [lifestyle / architectural / nature / food] photography, commercial stock photo.
```

### Midjourney via Nanobana — Required parameters

```
no watermark no sparkle no logo no text no signage
--ar 3:2 --style raw --q 2
--no watermark, sparkle, logo, text, signage, person, crowd, blur, low resolution, overexposed, distorted
```

> For Korean subjects, add: `No chinese architecture, no japanese style.`

---

## Image Evaluation

Each image is checked across four areas before metadata is written:

| Area | What's checked |
|---|---|
| Prompt compliance | Objects, angle, lighting, color — do they match the prompt? |
| Technical quality | Resolution (min 4MP), distortion, anatomical errors, upscale artifacts |
| Adobe Stock rules | No watermarks, logos, text, trademarks, or identifiable faces |
| Cultural accuracy | Korean subjects checked against Chinese and Japanese style indicators |

Similarity between generated images is evaluated on 6 dimensions (angle, time of day, weather, color tone, subject, background). Images differing on 2+ dimensions are treated as independent uploads.

---

## Metadata Format

```
Title: [Subject] – [Location / Context] [Visual Style]

Keywords (up to 49, comma-separated, core 10 first):
keyword1, keyword2, keyword3, ...

Category:
Primary: [Main category]
Secondary: [Category], [Category]
```

**Keyword formula:**
`[Core subject ×5–7] + [Location / Country] + [Season / Time of day] + [Mood / Style] + [Composition] + [Emotion / Lifestyle]`

---

## Upload Checklist

**AI Labeling**
- [ ] "Created with generative AI tools" checkbox selected
- [ ] "Persons and properties are fictional" checkbox selected (if applicable)
- [ ] Asset type correctly set — Photo or Illustration

**Legal & Compliance**
- [ ] No watermark, signature, or ✦ symbol
- [ ] No text, signs, or legible characters
- [ ] No trademarks or brand logos
- [ ] No identifiable faces (silhouettes only)
- [ ] No property rights issues (landmarks, buildings)

**Technical Quality**
- [ ] Minimum 4MP (long edge 3,000px+), JPEG, sRGB
- [ ] File size 45MB or under
- [ ] No noise, blur, or distortion
- [ ] No anatomical errors (fingers, joints, limbs)
- [ ] No AI-generated broken text or strange patterns
- [ ] Color image — no black & white or duotone conversion
- [ ] No filter effects (sun rays, lens flare, vignette)

**Metadata**
- [ ] Title in English, under 200 characters
- [ ] Keywords: 49 or fewer, core 10 listed first
- [ ] No trademarks, camera specs, AI tool names, or public figures in title or keywords

**Duplicate Prevention**
- [ ] No similar image already in registry
- [ ] Not a flipped, cropped, or color-swapped version of an existing upload

---

## Tech Stack

| Tool | Role |
|---|---|
| Claude (claude.ai) | Skill runner — prompts, evaluation, metadata |
| ChatGPT (DALL·E) | Photorealistic image generation |
| Midjourney via Nanobana | Illustration and atmospheric image generation |

---

## Repository Structure

```
adobe-stock-workflow/
└── SKILL.md        # Full Claude skill — workflow, prompts, checklists, registry
```

---

## License

MIT License  
Prompt templates and workflow documentation are shared for personal and reference use.  
Images generated using this workflow are subject to the terms of the respective AI tools and Adobe Stock contributor guidelines.
