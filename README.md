# Frontend Landing

Create stunning, zero-dependency landing pages as a single self-contained HTML file.

`frontend-landing` is a skill for generating premium one-page websites with strong art direction, responsive layouts, scroll animations, and a signature Liquid Glass visual system inspired by high-end product marketing pages.

It is designed for people who want beautiful output fast, without setting up a framework, build step, or component library.

## What This Does

**Frontend Landing** helps non-designers create polished marketing pages without needing to know CSS frameworks or modern frontend tooling. It follows a "show, don't tell" workflow: instead of forcing users to describe aesthetics precisely, it can guide them through visual directions and style presets, then generate a complete landing page as a standalone HTML file.

### Key Features

- **Zero Dependencies** — Single HTML files with inline CSS/JS. No npm, no build tools, no frameworks.
- **Visual Style Discovery** — Helps users choose design direction through concrete visual options instead of vague aesthetic language.
- **10 Distinct Presets** — Includes genuinely different visual systems, not just color swaps.
- **Liquid Glass Signature** — Premium SVG-based refraction, chromatic aberration, blur, border layers, and interactive lighting.
- **Responsive by Default** — Layout, spacing, and type scale cleanly from phone to desktop.
- **Anti-AI-Slop** — Pushes toward stronger hero composition, typography, pacing, and art direction.

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

## Usage

### Create a New Landing Page

```text
/frontend-landing

> "Build a premium landing page for an AI note-taking product. Make it feel calm, sharp, and high-end."
```

The skill can:
1. Ask about your page type and content readiness
2. Help choose a style path or preset
3. Generate preview directions when needed
4. Build a complete single-file HTML landing page
5. Let you iterate on visuals, structure, and pacing

### Example Prompts

```text
/frontend-landing

> "Create 3 visual directions for a personal portfolio homepage, then let me choose one."
```

```text
/frontend-landing

> "Make a single-file HTML launch page for a design studio using the Liquid Glass preset."
```

```text
/frontend-landing

> "I need a zero-dependency product page with hero, features, testimonials, pricing, and a strong final CTA."
```

## Included Styles

- **Liquid Glass** — Premium, Apple-inspired, refractive, depth-driven
- **SaaS Clean** — Professional, trustworthy, modern B2B clarity
- **Bold Startup** — High-energy, launch-ready, oversized presence
- **Neon Tech** — Futuristic, technical, cyber-modern
- **Warm Organic** — Friendly, natural, human-centered
- **Editorial Luxe** — Refined, magazine-inspired, aspirational
- **Brutalist Raw** — Unconventional, graphic, intentionally bold
- **Pastel Dream** — Soft, playful, polished consumer energy
- **Dark Cinema** — Dramatic, immersive, cinematic mood
- **Minimal Ink** — Typography-led, precise, restrained

## Output Example

Each landing page is generated as a single, self-contained HTML file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page</title>
    <style>
        /* Fonts, CSS variables, layout system, animations */
    </style>
</head>
<body>
    <nav>...</nav>
    <section class="hero">...</section>
    <section class="features">...</section>
    <section class="cta">...</section>
    <footer>...</footer>
    <script>
        // Scroll animations, interactions, and optional Liquid Glass behavior
    </script>
</body>
</html>
```

Typical output includes:

- Hero section with a clear focal point
- Feature or value sections
- Optional pricing, FAQ, testimonials, stats, gallery, or newsletter sections
- Final CTA and footer
- Scroll reveal animations
- Responsive spacing with `clamp()`
- Visual hierarchy tuned for both desktop and mobile

## Philosophy

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

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Main skill definition, workflow, landing page architecture, Liquid Glass implementation, animation patterns, and base CSS system |
| `STYLE_PRESETS.md` | Reference file for all 10 presets, including typography, palettes, layout patterns, and usage guidance |
| `test-liquid-glass.html` | Local reference/demo page for testing the Liquid Glass material treatment |
| `README.md` | Repository overview, installation instructions, and open-source documentation |

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

## Why single-file HTML

Single-file output makes the result:

- Easy to preview locally
- Easy to send to clients or teammates
- Easy to deploy to static hosting
- Easy to archive
- Easy to edit manually afterward

This is especially valuable for rapid prototyping, marketing experiments, and design exploration.

## Best fit

Use this skill when you want to create:

- Product landing pages
- SaaS homepages
- Personal homepages
- Portfolio sites
- Launch pages
- Coming-soon pages
- Event pages
- Agency or studio one-pagers

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
