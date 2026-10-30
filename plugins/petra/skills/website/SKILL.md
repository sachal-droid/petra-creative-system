---
name: website
description: Petra pipeline for websites, landing pages, microsites and product pages delivered as one self-contained HTML file. Runs strategy, three directions, an approved render plan, imagery production, the build, and the quality check including a responsive and performance pass. Use when someone wants a page or site designed and built, redesigned, or a landing page for a campaign or product.
---

# Website

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

- Page type: landing page, product page, brand homepage, microsite, campaign page
- Conversion goal and the one action the page exists for (buy, sign up, retailer locator, request a sample)
- Content supplied: copy, product data, reviews, logos, existing photography, legal and footer requirements
- Existing site: URL, what stays, what goes, platform it will be rebuilt in later (Shopify, Webflow, custom) so the HTML hands off cleanly
- Interactivity wanted: motion level (still, light, motion-led), video hero, interactive product selector

## Discovery additions

Audit the current site and three competitor pages: above-the-fold message, proof placement, navigation, page speed feel, mobile behavior. Note what shoppers say is confusing in reviews and support questions.

## Specialist skills

Use when installed: `design-taste-frontend`, `impeccable` or `hallmark` for anti-template layout and the pre-flight check, `design-motion-principles` for motion, `3d-web-and-physics` for 3D product viewers, `clone-website` when a redesign must start from the existing site's structure. Imagery comes from `petra:images` rules.

## Directions

Each Direction Card adds: the page architecture (sections in order with the job of each), the hero concept, the type and color system as CSS tokens, the motion feel, and a drawn above-the-fold frame at desktop and mobile widths.

## Render plan (Gate 2)

Section-by-section plan: headline and copy from the copy bank, the imagery each section needs (generated, supplied, or none), components and interactions. Generated imagery rows carry model, ratio (16:9 hero, 1:1 or 4:5 product tiles, 9:16 mobile hero if separate), references, prompt summary. Total generations, preflighted cost, balance. Wait for approval.

## Production

1. Generate and approve imagery first. Export approved images; reference them by hosted URL in the HTML and list them in the job record so the final host can rehost them.
2. Build one self-contained HTML file: inline CSS and JS, CSS custom properties for the design tokens, web fonts via a font service link, semantic sections, mobile first with a 16px side gutter and no horizontal scroll.
3. Copy comes from the approved copy bank only. Every claim on the page appears in the claims list.
4. Motion: purposeful, short, respects `prefers-reduced-motion`.
5. Forms and checkout are visual placeholders wired for the platform the site will live on; never collect real data in the deliverable.

## Quality check additions

- Responsive: 360px, 768px, 1280px screenshots reviewed; nothing clipped or overlapping
- Performance: images sized to their slot, lazy loaded below the fold, no library heavier than the page needs
- Accessibility: contrast at AA, alt text on product imagery, keyboard reachable controls, headings in order
- Conversion: the one action is visible above the fold and repeated where attention drops
- Copy: approved lines only, legal and footer requirements present, flagged claims resolved

## Delivery

One .html file, screenshots at the three widths, hosted URL per generated image, job record with the image list for rehosting and the token sheet (colors, type scale, spacing) for the platform rebuild.
