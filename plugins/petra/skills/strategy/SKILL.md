---
name: strategy
description: Shared front end of every Petra Creative System job. Runs brief intake, buyer and market discovery, creative strategy and copy, then three visual and copy directions for the user to choose from, and writes the Locked Brief that production builds from. Use at the start of any petra pipeline, or on its own when someone asks for buyer research, personas, positioning, messaging, a creative strategy or campaign directions.
---

# Strategy

Four stages and one gate. The output is a Locked Brief that every production pipeline builds from. Load `petra:standards` first.

Where a stage names a skill, use that skill if it is installed. If it is not, use the method written under the stage. Either way, the stage must produce its deliverable in the format given.

## Stage 0: Brief

Ask in one round, at most four questions, skipping anything already answered:
1. Brand, product, exact SKU or variant, and what is being made
2. Who it is for and where it will live (channel, marketplace, placement, market)
3. The goal (launch, conversion, awareness, retail sell-in) and must-haves (offers, mandatory lines, claims, legal copy)
4. References, likes and dislikes, deadline

Then collect:
- Brand kit: an installed brand skill, or the user's filled copy of `templates/brand-kit.md`. If there is none, build a short one from the brand's site and listings during Discovery and mark it unconfirmed.
- Canonical product photos: one per variant, tight crop, label legible, at least 1200px.
- Product facts: size or count, ingredients or materials, how it is used, certifications, price point.

## Stage 1: Discovery

Skill: `growthub-creative-strategist`, Part 1 (market and product intelligence) and Part 2 (personas and pain points) only. The petra production pipelines replace its Part 3 image workflow.

Method without the skill: search in this order and cite every source.
1. Category and competitors: who is winning and what they do differently
2. Buyers: the life situations that make someone open to this product
3. Purchase drivers and barriers
4. Voice of customer: verbatim phrases from reviews, Reddit, comments and Q&A, with the source of each. Never paraphrase emotional language. Flag phrases that recur across three or more sources.
5. Communication gap: what competitors say versus what buyers need to hear

Depth: 8 to 15 searches for websites, packaging, decks and video. 4 to 8 for a single image or listing set. Never skip this stage.

Deliverable: Discovery Brief
- Competitors (3 to 5): position, promise, price, what works
- Drivers and barriers
- 3 to 4 personas, each named Adjective + Adjective + Archetype and defined by life situation and relationship to the problem, never by awareness level or mindset
- Per persona: top pains with verbatim quotes and sources
- The communication gap in two sentences
- Category creative audit for this deliverable: conventions to keep, conventions to break

## Stage 2: Strategy and copy

Strategy skill: `strategy-finishing`.
Method without it: build the nested strategy (business problem, consumer problem, insight, solution), then check that every problem raised has a matching answer.

Copy skill: `creative-writing-studio`. Draft with its writing principles, use its reader simulation to read every line as the priority persona, then run its line edit and proofreading passes.
Method without it: draft, read each line as the priority persona and mark where attention drops or trust breaks, cut anything that explains what the reader has already understood, then proof every character.

Deliverable: Strategy one-pager
- Business problem, consumer problem, insight, solution
- Insight in one sentence: [persona] wants [X], but [Y] stands in the way, because [Z]
- Single-minded proposition in one line
- Priority persona and awareness stage
- Emotional and rational balance, and why (how differentiated the product is, how considered the purchase is, how much attention the channel gets)
- Reasons to believe, from product facts only
- Message hierarchy: one primary message, up to three supporting

Deliverable: Copy bank
- 5 headlines, 3 subheads, body copy at the length this deliverable needs, 3 calls to action, proof points
- Each tagged with persona and awareness stage, with the strongest in each group marked
- All of it following the copy rules in `petra:standards`

## Stage 3: Three directions

Skill: `creative-director`, Phases 2 to 4, at the idea level this deliverable needs (usually campaign or execution).
Method without it: find one tension (cultural, category or human). Generate at least ten ideas using three different methods: structural change, collision of two unrelated things, inversion. Treat the first three as warm-up. Score the rest on originality, strategic fit, emotional specificity, feasibility and simplicity. Drop any idea that would still work with a competitor's name in place of the brand.

Keep three directions that differ in idea and in look. Three variations of one idea is one direction.

Deliverable: three Direction Cards
- Name, and the idea in one sentence
- The insight it plays and the persona it targets
- Visual world: palette (HEX), type pairing, imagery style (photo, illustration or 3D; lighting; lens), composition signature, texture, motion feel
- Copy voice: tone in three words, hero headline, two supporting lines, call to action
- How it shows up in this deliverable (hero section, front panel, main image, opening shot)
- Why it wins, and the risk
- Score

Show each direction as well as describing it: an inline style tile with palette, type and a sample headline. Mood frames from Higgsfield count as generation, so they need the user's go first.

End with a recommendation and the reason for it.

## Gate 1: the pick

Stop and wait. The user picks one, combines parts (for example the visual from 2 and the copy from 1), or asks for another round. Never pick for them. If no one is watching, stop here with the cards ready.

## Locked Brief

After the pick, write this and treat it as the only source for production. Any change after this point makes a new version. Say what changed.

```
LOCKED BRIEF  [brand] / [deliverable] / v1
Product:      name, SKU, variant, facts
Audience:     priority persona, awareness stage
Insight:
Proposition:
Direction:    name, idea in one sentence
Visual world: palette HEX, type, imagery, composition, texture, motion
Copy:         approved headline, subheads, body, CTA, proof points
Must-haves:
Don'ts:
Specs:        formats, sizes, channels
```
