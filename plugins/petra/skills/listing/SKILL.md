---
name: listing
description: Petra pipeline for marketplace listing image sets (Amazon, Walmart.com, TikTok Shop, Shopify product pages) and A+ content panels. Runs strategy, three directions, an approved render plan, production with product lock and approved on-image copy, and the quality check. Use when someone wants a main image, infographic images, lifestyle images, comparison charts or A+ modules for a product listing.
---

# Listing

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

- Marketplace and category, and the listing's current images if it exists
- The set: main image, then how many secondary images (default 6) and whether A+ modules are in scope
- Product facts to show: size or count, variant, ingredients or materials, how to use, who it is for, certifications, what is in the box
- Competitor listings the user wants beaten (3 to 5 ASINs or URLs)

## Discovery additions

Read the top competitor listings and the brand's own reviews. Pull: the questions shoppers ask, the complaints that recur, the claims competitors lead with, and the images competitors are missing. This decides the image order.

## The set

Default order, one job per image:
1. Main: product on pure white, fills 85 percent of frame, no text, no props, marketplace rules met
2. Benefit hero: the single main benefit, one line of approved copy
3. What is in it or how it works: ingredients, materials or mechanism
4. How to use: steps, in order, three at most
5. Lifestyle: the priority persona using it, product visible and legible
6. Comparison or proof: us versus the category, or ratings and certifications
7. Size, count or variant guide
A+ modules follow the same ideas at the marketplace's module sizes.

## Specialist skills

Use when installed: `higgsfield-product-photography` (packshots and lifestyle), `studio` (prompt craft), `art-director` (layout review). Text-heavy images (infographics, comparison charts) are built as layouts, not generated: generate the product and scene, then set the copy in a clean composed layout so every character is right.

## Render plan (Gate 2)

One row per image: slot, file name, ratio (1:1 unless the marketplace says otherwise), model, resolution, references, prompt summary, copy that will appear on it. Total generations, preflighted cost, balance. Wait for approval.

## Production

1. Main image first. Approve it before anything else; its product render is the reference for the rest of the set.
2. Render scene images at `1k`, check product lock, then finals at `2k`.
3. Compose copy over renders in layout. Verify every character. Keep text inside safe margins and readable at 300px wide.
4. Reuse one seed per direction so the set looks like one shoot.

## Quality check additions

- Marketplace rules: main image background, fill ratio, no badges or text where the marketplace forbids them
- Thumbnail test: each image communicates its one idea at 300px
- Facts: every number and ingredient on an image matches the product facts the user gave
- Claims: flagged claims resolved; no "#1" or "best" without the proof on the image or in the listing

## Delivery

PNG at 2K, 1:1 (plus any marketplace-specific sizes), numbered in slot order, hosted URL per asset, job record, and a short note on which competitor gap each image answers.
