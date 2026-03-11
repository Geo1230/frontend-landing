# Frontend Landing

Create stunning, zero-dependency landing pages as a single self-contained HTML file.

`frontend-landing` is a skill for generating premium one-page websites with strong art direction, responsive layouts, scroll animations, and a signature Liquid Glass visual system inspired by high-end product marketing pages.

It is designed for people who want beautiful output fast, without setting up a framework, build step, or component library.

## Installation

### For Claude Code / Windsurf Users

Copy the skill files into your local skills directory:

```bash
mkdir -p ~/.claude/skills/frontend-landing
cp SKILL.md ~/.claude/skills/frontend-landing/
cp STYLE_PRESETS.md ~/.claude/skills/frontend-landing/
```

If you also want to keep the repository docs and demo file locally, copy:

```bash
cp README.md ~/.claude/skills/frontend-landing/
cp test-liquid-glass.html ~/.claude/skills/frontend-landing/
```

Then invoke the skill from Claude Code / Cascade when you want to generate a landing page.

### Manual Download

1. Download `SKILL.md` and `STYLE_PRESETS.md` from this repository
2. Place them in `~/.claude/skills/frontend-landing/`
3. Restart your tool if needed

## What it does

- Generates a complete landing page in **one HTML file**
- Uses **inline CSS and JavaScript** only
- Requires **zero dependencies**
- Produces pages that are **responsive by default**
- Supports **10 distinct style presets**
- Includes a **real Liquid Glass implementation** with SVG displacement, blur, border layers, and interactive lighting
- Helps users choose style visually instead of relying on vague aesthetic descriptions

## Who it is for

Use this skill when you want to create:

- Product landing pages
- SaaS homepages
- Personal homepages
- Portfolio sites
- Launch pages
- Coming-soon pages
- Event pages
- Agency or studio one-pagers

It is especially useful when you want **high visual quality** but still want the final result to be easy to open, share, edit, and deploy.

## Key ideas

- **Zero dependency output**
  Every page is a single standalone HTML file. No npm install, no bundler, no framework.

- **Show, don’t tell**
  The skill is designed to help users pick a direction through concrete visual options instead of abstract design language.

- **Anti-template aesthetics**
  The goal is not generic AI landing pages. The skill pushes for memorable heroes, stronger typography, cleaner pacing, and more intentional composition.

- **Narrative-first landing pages**
  A page should not feel like a random stack of sections. It should open with a point of view, establish tension, create trust, and end in a clear call to action.

- **Premium Liquid Glass**
  The flagship style uses a layered glass material system with real SVG displacement refraction, chromatic edge aberration, backdrop blur, gradient borders, and mouse-responsive highlights.

## Requirements

- [Claude Code](https://claude.ai/claude-code) or a compatible skill-enabled environment
- No frontend framework, build tool, or package installation is required for the generated output

## Included files

| File | Purpose |
|------|---------|
| `SKILL.md` | Main skill definition, workflow, landing page architecture, Liquid Glass implementation, animation patterns, and base CSS system |
| `STYLE_PRESETS.md` | Reference file for all 10 presets, including typography, palettes, layout patterns, and usage guidance |
| `test-liquid-glass.html` | Local reference/demo page for testing the Liquid Glass material treatment |
| `README.md` | Repository overview, installation instructions, and open-source documentation |

## Style presets

The skill ships with 10 curated presets:

1. `Liquid Glass`
2. `SaaS Clean`
3. `Bold Startup`
4. `Neon Tech`
5. `Warm Organic`
6. `Editorial Luxe`
7. `Brutalist Raw`
8. `Pastel Dream`
9. `Dark Cinema`
10. `Minimal Ink`

These are not just color themes. Each preset defines a different:

- Layout pattern
- Typography system
- Color language
- Section rhythm
- Hero composition style
- Component treatment
- Visual tone

## Output characteristics

A typical generated page includes:

- A strong hero section with a clear focal point
- Feature or value sections
- Optional sections like pricing, FAQ, testimonials, stats, gallery, or newsletter
- A final CTA section
- Footer navigation
- Scroll reveal animations
- Responsive spacing with `clamp()`
- Visual hierarchy tuned for both desktop and mobile

## Liquid Glass highlight

The flagship `Liquid Glass` preset goes beyond ordinary frosted panels.

It combines:

- SVG `feDisplacementMap`-based refraction
- Chromatic aberration at edges
- Backdrop blur and saturation
- Multi-layer glass borders
- Directional highlight overlays
- Mouse-responsive lighting behavior

This creates a much richer glass material than a simple `backdrop-filter: blur()` treatment.

## Design standards

This skill intentionally avoids common low-quality landing page patterns such as:

- Generic purple gradients
- Default-looking SaaS hero layouts
- Weak typography pairings
- Repetitive centered sections
- Emoji-based icon systems
- Glass used on flat, textureless backgrounds

Instead, it pushes for:

- Memorable hero compositions
- Better section pacing
- Stronger editorial hierarchy
- Distinct visual direction per preset
- Premium brand presentation

## How to use

If you are using this as a Windsurf/Cascade skill, place it in your skills directory and invoke it when you want a landing page or one-page website.

Example prompts:

```text
Build a premium landing page for an AI note-taking product. Make it feel calm, sharp, and high-end.
```

```text
Create 3 visual directions for a personal portfolio homepage, then let me choose one.
```

```text
Make a single-file HTML launch page for a design studio using the Liquid Glass preset.
```

```text
I need a zero-dependency product page with hero, features, testimonials, pricing, and a strong final CTA.
```

## Recommended workflow

1. Define the page type and goal
2. Decide whether content already exists or needs to be generated
3. Choose a style path:
   - preview-based selection
   - direct preset selection
4. Generate the final single-file HTML page
5. Open locally and iterate on visuals, copy, and pacing

## Why single-file HTML

Single-file output makes the result:

- Easy to preview locally
- Easy to send to clients or teammates
- Easy to deploy to static hosting
- Easy to archive
- Easy to edit manually afterward

This is especially valuable for rapid prototyping, marketing experiments, and design exploration.

## Best fit

`frontend-landing` is best when you want **beautiful output quickly** and you value:

- visual quality
- portability
- fast iteration
- no setup friction
- strong landing page taste

If you want a polished marketing page without spinning up a full frontend stack, this skill is built for that.

## Credits

Created by [@Geo1230](https://github.com/Geo1230) with Cascade.

Inspired by the idea that premium marketing pages should be easier to make, easier to share, and not locked behind heavy frontend stacks.

## License

MIT — Use it, modify it, and share it.

## Author notes

If you publish this on GitHub, it helps to include:

 
- a few screenshots or GIFs
- 2 to 4 example prompts
- one or two generated sample pages
- a short before/after or preset comparison section

 
That will make the repo much easier to understand at a glance.
