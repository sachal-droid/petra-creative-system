---
name: animation
description: Petra pipeline for motion graphics and animation: animated logos, kinetic type, animated explainers and infographics, UI and web motion, animated social posts, and character animation of a brand mascot. Delivers MP4 rendered from code or a self-contained HTML page. Runs strategy, three directions, an approved production plan, and the quality check with a motion review. Use when the deliverable moves but is built from design elements rather than filmed or generated footage.
---

# Animation

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

- Type: logo reveal, kinetic type, explainer, animated infographic, animated social post, web or UI motion, mascot animation
- Output: MP4 (length, ratio, frame rate, with or without sound) or HTML (where it embeds, autoplay and loop rules)
- Assets supplied: logo files, mascot artwork, brand type, data for infographics, script or copy
- Tone of motion: calm, playful, precise, energetic

## Specialist skills

Use when installed: `code-to-video` (MP4 from HTML or React with HyperFrames or Remotion), `animation-principles` (timing, easing, feel), `design-motion-principles` (UI motion and audit), `generative-2d-graphics` (p5.js or Paper.js patterns and illustration), `3d-web-and-physics` (three.js and physics). Mascot or character motion that needs generated footage runs through `petra:video` with the mascot's forbidden poses enforced.

## Directions

Each Direction Card adds: the motion idea in one line, the storyboard in 4 to 6 frames, the easing and timing character, the type behavior, the sound idea, and one drawn frame.

## Production plan (Gate 2)

Storyboard with timings per beat, the build approach (HTML and CSS, Remotion, p5.js, three.js), the assets needed and whether any imagery is generated (rows with model, ratio, references, prompt summary, cost). Wait for approval. Code-rendered animation spends no credits; say so.

## Production

1. Build the storyboard frames as stills first and approve them.
2. Build the animation in code with the brand's tokens. Logo and mascot artwork are used as supplied vectors, never regenerated.
3. Timing follows the approved storyboard; easing is consistent across the piece; nothing moves without a reason.
4. Render MP4 at the agreed ratio and frame rate (default 30fps, 1080 on the long edge). HTML deliverables are one self-contained file, respect `prefers-reduced-motion`, and loop cleanly where asked.
5. Social versions: build the primary ratio, then adapt the layout for the others.

## Quality check additions

- Motion review: timing and easing match the direction; no default linear moves; reads at a glance on a phone
- Brand: logo clear space and minimum size respected in every frame; palette and type exact
- Legibility: type on screen long enough to read twice; safe zones for the platform
- Technical: frame rate steady, no dropped frames, file size fit for the channel, HTML plays without external dependencies beyond fonts
- Mascot: only allowed poses appear

## Delivery

MP4 per ratio or the .html file, a frame sheet (stills of each beat), the source project so it can be edited later, hosted URL for any generated imagery, job record.
