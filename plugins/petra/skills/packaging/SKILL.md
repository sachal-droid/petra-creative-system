---
name: packaging
description: Petra pipeline for packaging: boxes, labels, pouches, tubes, inserts, display trays and dieline artwork. Runs strategy, three directions, an approved render plan, mockup and panel production, a print spec, and the quality check with regulated-claims and retail compliance checks. Use when someone wants packaging designed, redesigned, mocked up or adapted to a new SKU, variant or retailer.
---

# Packaging

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

- Structure: format (folding carton, label, pouch, tube, blister, sleeve, display), dimensions, dieline if one exists, substrate and finish
- Channel: mass, drug, off-price, specialty, DTC or club. Off-price and club often need a different panel hierarchy (value and count up front).
- Mandatory copy: net contents, ingredients or materials, directions, warnings, country of origin, barcode, certification marks, legal lines, retailer requirements
- Variant system: how many variants, what changes between them (color, flavor, scent, count) and what must stay fixed
- Shelf context: where it sits, what it sits next to, facing count, planogram constraints

## Discovery additions

Audit the shelf: photograph or collect the competitive set at this retailer, note the dominant colors, the claims everyone leads with, and the visual conventions (window, hero image, badge styles). Decide which conventions to keep so it reads as the category, and which to break so it is found first.

## Specialist skills

Use when installed: `higgsfield-ads-and-brand-visuals` (packaging and mockup workflows), `studio` (prompt craft), `art-director` (hierarchy and legibility review). Compliance questions for Amazon go to `amazon-compliance-roadmap` when installed.

## Directions

Each Direction Card adds: front panel hierarchy in order (brand, product name, benefit, variant, count), the variant color system, the hero visual (photo, illustration, mascot or type-led), and how it reads at 10 feet and at 2 feet.

## Render plan (Gate 2)

Two kinds of asset:
- Mockups: `gpt_image_2_5` for structure, finish and style transfer; `nano_banana_2_1` when an existing label or mascot must be reproduced exactly. Ratios 1:1 and 4:5 for review, 2K.
- Flat panel artwork: composed in layout, not generated. Generated elements (hero image, mascot, texture) are produced as cutouts (`background: transparent`) and placed.
One row per asset with model, references, prompt summary and the copy on it. Total generations, preflighted cost, balance. Wait for approval.

## Production

1. Front panel first, as flat artwork with real copy. Approve it before the mockup.
2. Mockup the approved front on the structure. Then side, back and top panels with mandatory copy placed.
3. Variants: change only the variant color and variant copy; everything else stays locked.
4. Shelf render: the pack in the shelf context from Discovery, between its real competitors.

## Quality check additions

- Mandatory copy present and placed: net contents, ingredients or materials, warnings, barcode area, certification marks, legal lines
- Regulated claims: every flagged claim resolved (cosmetics, pet pesticide, children's products, medical devices, sustainability marks)
- Legibility: product name readable at 10 feet, benefit at 4 feet, mandatory copy at reading distance; minimum type sizes respected
- Variant system: no color borrowed from another variant; variants told apart at a glance
- Barcode: quiet zone kept; not placed on a fold or seam

## Delivery

PNG mockups and flat panels at 2K, hosted URL per asset, job record, and a print spec for the designer: dimensions, dieline reference, color values (HEX plus the Pantone or CMYK the brand uses), fonts and sizes, finish, bleed and safe area, and the mandatory copy list with placement. The artwork handed to print is produced by a designer from this spec; the system's panels are the approved design, not the print-ready file.
