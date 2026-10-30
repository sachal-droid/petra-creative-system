---
name: video
description: Petra pipeline for video: product videos, ad spots, brand films, UGC-style clips, review reels and fashion films made with Seedance 2.5 on Higgsfield. Runs strategy, three directions, a shot list, approved statics (key frames) before any animation, an approved render plan, production at 480p draft, and the quality check. Use when someone wants moving image with a product, talent or brand in it.
---

# Video

Load `petra:standards`, then run `petra:strategy` (or reuse its Locked Brief). Then follow this.

## Brief additions

- Format and length: 6s bumper, 12 to 15s ad, 25 to 30s reel, 60s film; ratios needed (9:16 first for social, 4:5, 16:9)
- Talent: none, hands, a model, or a reusable AI talent the brand already uses (keep the same reference stills across jobs for continuity)
- Sound: voiceover (script and pronunciation notes), music, natural sound, or silent with a held super
- Supers: lines that must appear on screen, when, and for how long
- Edit plan: who edits (the system delivers shots; an editor assembles), or whether a single continuous shot is the deliverable

## Specialist skills

Use when installed: `film-director` (treatment, shot list, keyframes, QC), `seedance-shotlist-director` or `higgsfield-seedance-prompt` (shot-level Seedance prompts), `higgsfield-product-videography` (product motion), `higgsfield-cinematic-filmmaking` (cinematic grammar), `ugc-script-writer` (UGC scripts), `studio` (prompt craft). Imagery for key frames comes from `petra:images` rules.

## Directions

Each Direction Card adds: the film idea in one line, the opening image, the structure (hook, demonstration, proof, close) with seconds per beat, the camera language, the sound idea, and one drawn key frame.

## Shot list

After the pick, write the shot list: shot number, duration (4 to 30s), what happens, camera, product and talent in frame, super on screen, sound. Keep the camera on the product. Prefer still or simple actions for hands; complex hand actions (pouring, tapping, typing) distort in generation and get cut. Each shot has a start frame and, when the move needs an end state, an end frame.

## Statics (Gate 3)

Generate the start and end frames for every shot as stills first (`nano_banana_2_1`, one seed per direction, product lock on every frame). The user approves the statics before any video credit is spent.

## Render plan (Gate 2 for video)

One row per shot: shot number, duration, `seedance_2_5`, mode `omni_reference`, `start_image` and `end_image` media or job ids, `image_references` for product and talent, ratio, `generate_audio` (off unless natural sound is wanted), `draft: true`, prompt summary. Total generations, preflighted cost, balance. Wait for approval.

## Production

1. Render each shot once at 480p draft. Review motion, product lock and talent continuity.
2. Fix a shot by changing the prompt or frames, not by rerolling blindly. Extend an approved shot with `video_extension` rather than regenerating it.
3. Supers and voiceover are added in the edit, not generated, unless the direction calls for a rendered super and the model has proven it can hold the text cleanly.
4. Finalize at 1080p (`draft_job_id`) only when the user asks, within seven days of the draft.
5. Reels and multi-ratio deliveries: generate the primary ratio, then reframe approved shots rather than regenerating.

## Quality check additions

- Product lock holds in every frame; no label drift, no color borrowed from another variant
- Talent continuity: same face, hair, wardrobe across shots; hands plausible
- Motion: no warping, no extra limbs, camera moves as written
- Timing: shot durations add up to the format; supers legible for at least 2 seconds
- Sound: audio off where music or voiceover will be added; pronunciation notes passed to the editor

## Delivery

MP4 per shot at 480p draft, hosted URL per shot, the shot list with job ids and draft expiry dates, the approved statics, VO script and super timings for the editor, job record.
