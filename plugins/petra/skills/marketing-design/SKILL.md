---
name: marketing-design
description: Petra pipeline for marketing statics: social posts, ad statics, email graphics, banners, sell sheets, one-pagers, retail signage and infographics. Runs strategy, three directions, an approved render plan, production with approved copy set in layout, and the quality check. Use when someone wants designed graphics with copy on them for a channel, rather than photography alone.
---

# Marketing design

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

Meta paid-ad statics for a Petra brand go to `petra-ad-creative` when it is installed (see `petra:start`).

## Brief additions

- Channel and placement for each asset, with the ratio and safe zones it needs (feed 1:1 or 4:5, story and reel 9:16, LinkedIn 4:5, email 600px wide, retail signage at print size)
- The set: how many assets, how many concepts, whether a series must feel like one campaign
- Offer or message mandatory lines, legal copy, logo lockup rules
- For sell sheets and one-pagers: the buyer audience, the SKUs with codes, case pack, pricing columns the user wants shown, contact block

## Specialist skills

Use when installed: `ad-creative` (headline and body variations at scale), `growthub-creative-strategist` (angles and hooks), `art-director` (layout and hierarchy review), `studio` (image prompt craft). Product and scene imagery comes from `petra:images` rules.

## Directions

Each Direction Card adds: the layout system (grid, type scale, image-to-copy ratio), the hook style (claim, question, proof, demonstration, comparison), and one drawn example of the hero asset at its real ratio.

## Render plan (Gate 2)

Generated imagery and composed layouts are listed separately. Imagery rows: model, ratio, references, prompt summary. Layout rows: asset, ratio, the exact copy on it, the image it uses. Total generations, preflighted cost, balance. Wait for approval.

## Production

1. Generate the imagery first (product truth on `nano_banana_2_1`; typographic or stylized backgrounds on `gpt_image_2_5`). Approve it.
2. Set copy in layout over approved imagery. Never ask the model to render body copy; headlines only when the model has proven it can render them, and every character is verified.
3. Build the hero ratio first, approve, then adapt to the other ratios by reframing the layout, not by regenerating the image.
4. Series: one seed, one palette, one type system across the set.

## Sell sheets and one-pagers

Trade-facing, so the trade copy rules apply. Structure: brand line and hero image, the range with SKU codes and counts, three proof points (ratings, velocity, distribution with sources), case pack and lead time, the contact block. Pricing only when the user supplies it and says which channel it is for.

## Quality check additions

- Safe zones: nothing important under platform UI (story and reel top and bottom bands, feed crop)
- Hierarchy: the hook reads first at thumbnail size, the brand is visible, one call to action
- Copy: approved lines only, every character verified, mandatory and legal lines present, flagged claims resolved
- Series: assets read as one campaign side by side

## Delivery

PNG at 2K per ratio, hosted URL per asset, job record. Sell sheets also as PDF when the user asks. Name files by channel and ratio.
