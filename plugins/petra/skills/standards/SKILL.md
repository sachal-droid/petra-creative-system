---
name: standards
description: House rules for every Petra Creative System job, covering generation defaults (Nano Banana 2.1 capped at 2K, GPT Image 2.5 for mockups and typography, Seedance 2.5 at 480p), Higgsfield mechanics, approval gates, copy and claims rules, the quality check, the job record, delivery specs and the revision protocol. Every petra pipeline loads this before it starts. Also use when someone asks what the defaults or rules are, or wants to change one.
---

# Standards

Every petra pipeline follows these rules. The user can change any default in the conversation. The change holds for the rest of the job and is noted in the delivery and the job record.

## Generation defaults

Image model routing, on Higgsfield:
- `nano_banana_2_1` (Nano Banana 2.1) for anything that shows a real product, label, mascot or person who must match a reference. Best label fidelity. Supports 4:5 and seeds.
- `gpt_image_2_5` (GPT Image 2.5) for packaging mockups and dielines, style transfer, typography-led layouts, and transparent cutouts (`background: transparent`). Supports 4:5. Set `quality` to `high` for finals.
- Resolution `1k` for exploration (mood frames, first passes), `2k` for finals. Never `4k`, and never upscale past 2K.
- Aspect ratio set by the deliverable (see Delivery). No `auto` on finals.
- Attach the canonical reference for the exact SKU and variant on every product render, with role `image_references`. Never use one variant's reference for another.
- Three references when possible: the product group shot, a tight single crop of the hero variant, and one scene or style reference. Three references beat one for fidelity.
- Record the seed of every approved image and reuse it for variants in the same direction.

Video, on Higgsfield:
- Model `seedance_2_5` (Seedance 2.5)
- 480p via `draft: true`. A draft can be finalized at 1080p within seven days by passing its job id as `draft_job_id`. Do that only when the user asks.
- Mode `omni_reference` with the approved statics as references: the opening frame as `start_image`, the closing frame as `end_image` when the shot has one, product and talent stills as `image_references`. Use `t2v` only when no product, person or character has to stay consistent.
- Duration 4 to 30 seconds per shot, set in the render plan. Use `video_extension` to extend an approved shot rather than regenerating it.
- `generate_audio: false` by default. Turn it on per shot only when natural sound is wanted and no music or voiceover comes in the edit.
- Pass `aspect_ratio` explicitly. Vertical placements get `9:16`.

Product lock, on every render that shows the product:
- Name every label element and its position in the prompt, then end with: match the references exactly, do not simplify, abbreviate or restyle.
- State the variant's exact colors, and the colors that belong to other variants so the model does not borrow them.
- For a mascot or character, list the poses that are not allowed.
- When a product must be swapped into an existing scene, describe the swap in place (this product in this spot) rather than asking the model to remove something.

Higgsfield mechanics:
- Local or attached files go up in three steps: `media_upload`, PUT the file to the returned URL, `media_confirm`. Web images go through `media_import_url`. Pass the returned media id, never a URL, in `medias[].value`.
- Independent prompts go through `generate_image_batch` or `generate_video_batch`. `count` is only for variants of one prompt. The plan allows 8 concurrent jobs, so batch in groups of 8.
- Wait with `jobs_wait` (15 seconds or less per call) and show results once with `show_generation_by_ids`.
- Preflight cost with `get_cost: true` before Gate 2 and quote it in the render plan.
- Never pass `use_unlim` or `use_free_gens` unless the user asks for it.

If Higgsfield is not connected, deliver the render plan with final prompts and settings ready to paste, and say that connecting Higgsfield lets the system run them.

## Approval gates

1. Direction: after the three Direction Cards, always. Never pick for the user. When unattended, stop here.
2. Render plan: before anything that spends credits. Show each asset with its prompt summary, model, resolution, ratio, references, duration, the number of generations, the preflighted cost and the current Higgsfield balance.
3. Statics (video only): key frames approved before any animation.
4. Final: delivery comes with the quality check results and the job record.

## Copy rules

- No em dashes. No "it's not X, it's Y".
- Never use: game-changing, obsessed, transformational, revolutionary, elevate, unlock, seamless, next-level, "most brands".
- Customer language beats marketing language. Prefer verbatim phrases from Discovery.
- Every claim traces to a product fact the user gave or a cited source. Health, safety, "natural", "clinically", "#1" and comparative claims need evidence. Flag them if there is none.
- No text on an image unless the copy is approved. Verify every rendered character. If the model cannot render the text cleanly, set it in layout instead.

Regulated claims. Before any copy is approved, check the product category and flag anything that needs substantiation or a specific regulator's wording:
- Cosmetics and personal care (FDA): no drug claims (treats, cures, heals, prevents) without OTC monograph status; "clean", "natural", "non-toxic" need a definition the brand can defend.
- Pet care: anything that kills, repels or controls pests is a pesticide claim (EPA FIFRA) and needs registration; dental claims stay cosmetic (freshens, cleans) unless substantiated.
- Children's products (CPSC): age grading on pack, no safety claims without the test report, small parts and choking warnings where required.
- OTC medical devices such as hearing aids (FDA): required on-pack statements, no claims beyond the cleared intended use.
- Sustainability (FTC Green Guides): "recyclable", "biodegradable", "compostable" need qualification; certification marks only where the brand holds the certificate.
Flag, do not decide. The user confirms every flagged claim or drops it.

Retail copy (packaging, listing images, marketing designs) must also be frictionless:
- Say what it is and the main benefit first, in plain words.
- Show what shoppers check before buying: size or count, variant, key ingredients or materials, how to use, who it is for.
- One idea per panel or image, readable in three seconds at thumbnail size.
- No jargon, no vague promises, nothing a shopper has to hunt for.

Trade copy (sell-in decks, sell sheets, line review submissions) speaks to a buyer, not a shopper:
- Lead with what the buyer is measured on: velocity, margin, differentiation on shelf, replenishment reliability, compliance.
- Every number has a source and a date. Door counts, ratings and revenue figures are confirmed with the user before they go in.
- Never imply distribution the brand does not have.

## Quality check

Run before every delivery and report pass or fail on each line. Fix fails first. If one cannot be fixed, say so.

- Strategy: expresses the chosen direction's idea and speaks to the priority persona
- Brand: palette, type and voice match the brand kit and Locked Brief
- Product: identical to the reference in shape, proportion, color and every label element
- Copy: approved wording only, every character verified, copy rules met, flagged claims resolved
- Craft: reviewed by the pipeline's quality layer (for images, `studio` and `art-director`)
- Specs: format, size, ratio, resolution cap, file name

## Job record

Every job writes `brand_deliverable_RUN.md` next to the deliverables and keeps it current. It holds: the Locked Brief and its version; the Direction Cards and the pick; for every generated asset its file name, model, prompt, references (media ids), seed, job id, resolution and ratio; the Gate 2 plan and cost; QC results; defaults the user changed. A job can be rerun or revised from this file alone.

## Delivery

| Deliverable | Format | Default size |
|---|---|---|
| Website | One self-contained .html (inline CSS and JS, web fonts allowed) | Responsive, mobile first |
| Images | PNG | 2K, ratio by channel |
| Deck | .pptx | 16:9 |
| Packaging | PNG mockups and flat panel artwork, plus a print spec for the designer | 2K |
| Listing images | PNG | 2K, 1:1 |
| Marketing designs | PNG | 2K; 1:1, 4:5, 9:16 (4:5 for LinkedIn) |
| Video | MP4 | 480p draft |
| Animation | MP4 or self-contained .html | By channel |

Deliver files plus the hosted Higgsfield URL for each generated asset, so they can be shared without downloading.

File names: `brand_deliverable_direction_asset_v01.ext`, for example `roofus_listing_d2_main_v01.png`.

## Revisions

After delivery, a change request is handled one asset at a time:
- A copy, color or layout change inside the chosen direction: regenerate with the same seed, references and model, change only what was asked, bump the asset version (`v02`).
- A change to the idea, audience or proposition: it is a new Locked Brief version. Say what changed and rerun from Stage 3 if the direction no longer fits.
- Never silently change an approved asset. Every revision is logged in the job record.
