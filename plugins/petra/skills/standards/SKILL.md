---
name: standards
description: House rules for every Petra Creative System job, covering generation defaults (Nano Banana 2.1 capped at 2K, Seedance 2.5 at 480p), approval gates, copy rules, the quality check and delivery specs. Every petra pipeline loads this before it starts. Also use when someone asks what the defaults or rules are, or wants to change one.
---

# Standards

Every petra pipeline follows these rules. The user can change any default in the conversation. The change holds for the rest of the job and is noted in the delivery.

## Generation defaults

Images, on Higgsfield:
- Model `nano_banana_2_1` (Nano Banana 2.1)
- Resolution `1k` for exploration (mood frames, first passes), `2k` for finals. Never `4k`, and never upscale past 2K.
- Aspect ratio set by the deliverable (see Delivery). No `auto` on finals.
- Attach the canonical reference for the exact SKU and variant on every product render. Never use one variant's reference for another.
- Record the seed of every approved image and reuse it for variants in the same direction.

Video, on Higgsfield:
- Model `seedance_2_5` (Seedance 2.5)
- 480p via `draft: true`. A draft can be finalized at 1080p within seven days by passing its job id as `draft_job_id`. Do that only when the user asks.
- Mode `omni_reference` with the approved statics as references. Use `t2v` only when no product, person or character has to stay consistent.
- Duration 4 to 30 seconds per shot, set in the render plan.
- Native audio only for shots that need natural sound. Off when music or voiceover comes in the edit. Set per shot in the render plan.

Product lock, on every render that shows the product:
- Name every label element and its position in the prompt.
- State the variant's exact colors, and the colors that belong to other variants.
- For a mascot or character, list the poses that are not allowed.

If Higgsfield is not connected, deliver the render plan with final prompts and settings ready to paste, and say that connecting Higgsfield lets the system run them.

## Approval gates

1. Direction: after the three Direction Cards, always. Never pick for the user. When unattended, stop here.
2. Render plan: before anything that spends credits. Show each asset with its prompt summary, model, resolution, ratio and duration, plus the number of generations and the current Higgsfield balance.
3. Statics (video only): key frames approved before any animation.
4. Final: delivery comes with the quality check results.

## Copy rules

- No em dashes. No "it's not X, it's Y".
- Never use: game-changing, obsessed, transformational, revolutionary, elevate, unlock, seamless, next-level, "most brands".
- Customer language beats marketing language. Prefer verbatim phrases from Discovery.
- Every claim traces to a product fact the user gave or a cited source. Health, safety, "natural", "clinically", "#1" and comparative claims need evidence. Flag them if there is none.
- No text on an image unless the copy is approved. Verify every rendered character. If the model cannot render the text cleanly, set it in layout instead.

Retail copy (packaging, listing images, marketing designs) must also be frictionless:
- Say what it is and the main benefit first, in plain words.
- Show what shoppers check before buying: size or count, variant, key ingredients or materials, how to use, who it is for.
- One idea per panel or image, readable in three seconds at thumbnail size.
- No jargon, no vague promises, nothing a shopper has to hunt for.

## Quality check

Run before every delivery and report pass or fail on each line. Fix fails first. If one cannot be fixed, say so.

- Strategy: expresses the chosen direction's idea and speaks to the priority persona
- Brand: palette, type and voice match the brand kit and Locked Brief
- Product: identical to the reference in shape, proportion, color and every label element
- Copy: approved wording only, every character verified, copy rules met
- Craft: reviewed by the pipeline's quality layer (for images, `studio` and `art-director`)
- Specs: format, size, ratio, resolution cap, file name

## Delivery

| Deliverable | Format | Default size |
|---|---|---|
| Website | One self-contained .html (inline CSS and JS, web fonts allowed) | Responsive, mobile first |
| Images | PNG | 2K, ratio by channel |
| Deck | .pptx | 16:9 |
| Packaging | PNG mockups and flat panel artwork, plus a print spec for the designer | 2K |
| Listing images | PNG | 2K, 1:1 |
| Marketing designs | PNG | 2K; 1:1, 4:5, 9:16 |
| Video | MP4 | 480p draft |
| Animation | MP4 or self-contained .html | By channel |

File names: `brand_deliverable_direction_asset_v01.ext`, for example `roofus_listing_d2_main_v01.png`.
