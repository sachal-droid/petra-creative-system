---
name: start
description: Front door of the Petra Creative System. Use when someone wants creative work made (website, landing page, product or lifestyle images, deck, packaging, listing images, social or ad designs, video, animation, motion graphics) without naming a petra pipeline, when one request covers several deliverables, when someone wants a finished petra job revised, or when someone asks what the system can make.
---

# Start

Find the right pipeline, check what already exists, then run it.

## 1. Match the job

| The user wants | Pipeline |
|---|---|
| Website, landing page, microsite, product page | `petra:website` |
| Product, lifestyle, model or fashion photos, hero images | `petra:images` |
| Pitch, strategy, sales, sell-in or brand deck, line review submission | `petra:deck` |
| Packaging, box, label, pouch, insert, dieline artwork | `petra:packaging` |
| Amazon, Walmart, TikTok Shop or marketplace listing images, A+ content | `petra:listing` |
| Social posts, ad statics, email graphics, banners, sell sheets, retail signage | `petra:marketing-design` |
| Product video, ad video, brand film, UGC-style video, review reel | `petra:video` |
| Motion graphics, animated logo, kinetic type, animated explainer, animated infographic | `petra:animation` |

If the job could be either of two pipelines, ask one question offering both.

Meta paid-ad statics for a Petra brand: if `petra-ad-creative` is installed, it owns that job (it carries the brand identity files and the dashboard publish step). Run `petra:strategy` first only if the user wants new strategy or directions; otherwise hand off directly.

## 2. Several deliverables

For a launch kit or campaign (for example site, listing and video), run `petra:strategy` once, then each pipeline in the order the user needs, all reusing the same Locked Brief. Propose the order and confirm it. Shared assets (hero image, product renders) are generated once and reused.

## 3. Check what already exists

- An approved strategy or brief: map it onto the Locked Brief fields in `petra:strategy`, list what is missing, and start at production once the user confirms. If no direction has been chosen yet, Gate 1 still applies.
- A brand kit, product photos, past work: collect them now.
- A job record (`*_RUN.md`) from an earlier petra job: this is a revision. Load it, follow the revision rules in `petra:standards`, and do not rerun stages that are already locked.

## 4. Run

Load `petra:standards`, then the pipeline skill, and follow it from the start.
