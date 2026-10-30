---
name: images
description: Petra pipeline for product, lifestyle, model and fashion images and hero shots. Runs strategy, three directions, an approved render plan, Higgsfield production with product lock, and the quality check. Use when someone wants photos or renders of a product, a person wearing or using it, or campaign hero imagery, and the deliverable is a set of still images.
---

# Images

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

Ask only what the Locked Brief does not already hold:
- Shot list intent: how many images, which SKUs and variants, which channels (site, Amazon, social, retail deck) and the ratio each needs
- Talent: none, hands only, a model (age range, look, wardrobe rules), or a reusable AI talent the brand already uses
- Scene rules: environments, props, lighting, anything that must never appear

## Specialist skills

Use when installed, otherwise follow the method written here:
- `higgsfield-product-photography` for hero, lifestyle, CGI and precision edits from one product image
- `higgsfield-fashion-photography` for on-model and apparel, including consistent models across many SKUs
- `studio` to write and tighten the final prompts for the chosen model
- `art-director` to review composition, lighting and brand fit before and after rendering

Method without them: write each prompt in this order: subject and product lock, scene, lighting, camera (lens, distance, angle), composition, mood, then negative constraints. One sentence per block.

## Render plan (Gate 2)

A table with one row per image: file name, purpose and channel, ratio, model (`nano_banana_2_1` for product truth, `gpt_image_2_5` for style transfer or cutouts), resolution (`1k` test, `2k` final), references by media id, seed (if reusing), prompt summary. Below it: total generations, preflighted cost, balance. Wait for approval.

## Production

1. Upload references once (three-step upload) and reuse the media ids across the job.
2. Render one test image per distinct scene at `1k`. Check product lock before spending on finals.
3. Render finals at `2k` in batches of up to 8. Record the seed of every approved image.
4. Variants of an approved image (other SKU, other ratio) reuse its seed and references and change only what differs.
5. For ratio changes that would crop the product, use `outpaint_image` or `reframe` on the approved image rather than a fresh generation.

## Quality check additions

- Product lock: compare each final against the reference at 100%: shape, proportion, cap or closure color, every label element and its position, mascot pose if any
- Talent: same face, body and wardrobe across the set; no extra fingers, no warped hands holding product
- Scene: nothing from the forbidden list; no text in the scene that was not approved
- Set consistency: lighting direction and color temperature match across images that will sit together

## Delivery

PNG at 2K in the ratios requested, hosted URL per asset, job record. Group files by channel in the delivery note.
