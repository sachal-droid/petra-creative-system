# Petra Creative System

An agency process for Claude. Every job runs the way a good agency runs it: research the buyer, write the strategy, show three directions, build the one you pick, check it, deliver it.

## What it makes

| You need | Run | You get |
|---|---|---|
| Website or landing page | `/petra:website` | One self-contained HTML file |
| Product, lifestyle or fashion images | `/petra:images` | PNG, up to 2K |
| Deck | `/petra:deck` | PowerPoint (.pptx) |
| Packaging | `/petra:packaging` | Mockups and panel artwork, up to 2K |
| Listing images | `/petra:listing` | Marketplace image set, up to 2K |
| Marketing designs | `/petra:marketing-design` | Social, ad and email statics, up to 2K |
| Video | `/petra:video` | Seedance 2.5 clips at 480p |
| Animation and motion graphics | `/petra:animation` | MP4 or HTML |

Not sure which? Run `/petra:start` and describe the job. To revise a finished job, run `/petra:start` and attach its job record (`*_RUN.md`).

Decks, sell sheets and line review submissions for retail buyers run a trade-facing variant: buyer persona, retailer scorecard, and a numbers audit before anything is typed.

## How every job runs

1. **Brief**: a few questions about brand, product, audience and goal
2. **Discovery**: market, competitors, buyers and their own words
3. **Strategy and copy**: the insight, the proposition, the words
4. **Three directions**, visual and copy. **You pick one.**
5. **Render plan**: what gets generated and how. **You approve it** before any credits are spent.
6. **Production**
7. **Quality check**: strategy, brand, product accuracy, copy, specs
8. **Delivery**

## Install

In Claude (web, desktop or Cowork): **Customize > Plugins > Add > Add marketplace**, enter `sachal-droid/petra-creative-system`, then add **petra**.

In Claude Code:

```
/plugin marketplace add sachal-droid/petra-creative-system
/plugin install petra@petra-creative
```

## Connect

- **Higgsfield**, for images and video. Without it you get finished prompts and settings to run yourself.

## Bring your brand

Copy `plugins/petra/skills/strategy/templates/brand-kit.md`, fill it in, and attach it when you start a job, along with one clear photo per product variant. Without a brand kit, the system drafts one from your website and listings and asks you to confirm it.

Keep filled brand kits out of this public repo. Attach them per job, or keep them in a private skill (Petra's own brand files live in a private `petra-ad-creative` skill that the pipelines read when it is installed).

## Defaults

| | Default | Limit |
|---|---|---|
| Images, product truth | Nano Banana 2.1 | 2K max |
| Images, mockups, typography, cutouts, style transfer | GPT Image 2.5 | 2K max |
| Video | Seedance 2.5 | 480p draft, can be finalized at 1080p within 7 days |

Every job keeps a job record (prompts, references, seeds, job ids, QC results) so it can be rerun or revised later. Every claim passes a regulated-claims check (cosmetics, pet, children's products, medical devices, sustainability) before copy is approved.

Change any default by saying so in the chat. The change holds for the rest of that job.

## Works better with

Each stage names a specialist skill and uses it if you have it installed. Otherwise it runs its own built-in method. THIRD_PARTY.md lists those skills with sources and credits.

## License

MIT for Petra's own files. Third-party skills keep their own licenses.
