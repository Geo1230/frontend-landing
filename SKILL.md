---
name: frontend-landing
description: Create stunning, zero-dependency landing pages with modern visual effects like Liquid Glass (frosted glass refraction), scroll animations, and 10 distinctive style presets. Use this skill whenever the user wants to build a landing page, product page, personal homepage, portfolio site, launch page, one-pager, coming-soon page, or any single-page website. Also use when the user says "make me a website," "build a page for my project," "I need a homepage," or describes wanting a page with sections like hero, features, pricing, etc. Generates a single self-contained HTML file with inline CSS/JS — no frameworks, no build tools, no dependencies. Helps non-designers discover their preferred aesthetic through visual previews rather than abstract choices.
---

# Frontend Landing Skill

Create zero-dependency, visually striking landing pages from a single HTML file. Features **real Liquid Glass effects** — SVG displacement-map refraction with chromatic aberration, multi-layer borders, and depth simulation — all in pure CSS/SVG/JS. 10 curated style presets that produce genuinely different layouts, not just color swaps.

## Core Philosophy

1. **Zero Dependencies** — Single HTML file with inline CSS/JS. No npm, no build, no frameworks. Open in any browser, share anywhere.
2. **Show, Don't Tell** — Generate visual previews and let the user pick. Most people can't describe their aesthetic in words, but they know it when they see it.
3. **Anti-AI-Slop** — Every landing page must feel custom-crafted. Generic purple gradients, Inter/Roboto, cookie-cutter hero sections are banned.
4. **Responsive First** — All sizing uses `clamp()`. Every page looks great from 375px phone to 4K desktop.
5. **Liquid Glass Signature** — Our distinctive visual identity: real refraction via SVG displacement maps, chromatic aberration, edge-aware light simulation, and multi-layer glass borders. This is NOT just `backdrop-filter: blur()`.
6. **Brand Narrative First** — A landing page is not a pile of sections. It must open with a point of view, establish emotional tension, then move toward clarity, trust, and action.
7. **Hero Must Be Memorable** — The hero needs a signature visual anchor, not just a headline plus generic card grid. Build one focal form, scene, or product tableau that becomes the page's identity.
8. **Editorial Taste Over Template Energy** — Typography, spacing, contrast, and composition should feel art-directed. The page should read like a premium brand piece, not a generic SaaS builder export.

---

## Bundled References

Read `STYLE_PRESETS.md` (in the same directory as this file) during style selection (Phase 2). It contains all 10 preset specs with colors, fonts, layout patterns, and signature elements.

---

## Landing Page Architecture

### Required Sections

Every landing page includes at minimum:

| Section | Purpose | Content Limit |
|---------|---------|---------------|
| **Hero** | First impression, core message | 1 headline + 1 subline + 1 CTA button |
| **Features/Value** | What you offer | 1 heading + 3-6 feature cards |
| **CTA (Final)** | Convert the visitor | 1 headline + 1 button + optional subtext |
| **Footer** | Legal & links | Logo + nav links + copyright |

### Narrative Opening Requirement

The opening of every landing page must do more than introduce the product. It must establish a narrative arc:

1. **Emotional Hook** — Name the tension, desire, or worldview in one sharp line
2. **Brand Promise** — Show how the product reframes that tension
3. **Signature Visual** — Reinforce the promise with one memorable hero composition
4. **Action** — Give the visitor one clear next step

This can be implemented inside the hero, or via a hero + short bridge section, but it must feel intentional and branded.

### Optional Sections (pick what fits)

| Section | Purpose | Content Limit |
|---------|---------|---------------|
| **Social Proof** | Trust signals | 3-6 logos OR 2-3 testimonial quotes |
| **How It Works** | Process explanation | 3-4 steps with icons/numbers |
| **Pricing** | Plans comparison | 2-3 pricing cards |
| **FAQ** | Overcome objections | 4-6 collapsible Q&A pairs |
| **Stats/Numbers** | Impressive metrics | 3-4 animated counters |
| **Gallery/Showcase** | Visual portfolio | 3-6 images in grid |
| **Team** | Human connection | 3-4 member cards |
| **Newsletter** | Lead capture | 1 heading + email input + button |
| **Problem / Tension** | Frame the emotional or practical pain | 1 heading + 3-4 points or 1 quote block + supporting list |
| **Brand Statement** | Establish worldview and differentiation | 1 short editorial block or pull-quote style section |

### Content Density

Each viewport-height section should fit without internal scrolling:
- Max 6 cards per grid section (2x3 or 3x2)
- Max 4-6 bullet points per text section
- Max 3 lines per testimonial quote
- Images constrained to `max-height: min(50vh, 400px)`
- If content overflows → split into multiple sections

### Emotional Pacing

Do not give every section the same visual weight.

- **Hero** should feel like the strongest moment on the page
- **Second beat** should clarify tension, promise, or differentiation
- **Middle sections** can become more structured and informational
- **Final CTA** should feel like a visual return or payoff, not just another box at the bottom

Use contrast in one or more of these dimensions between sections:

- Scale
- Alignment
- Background intensity
- Typography mood
- Component density
- Motion intensity

---

## Workflow

### Phase 0: Detect Mode

**Mode A: New Landing Page** — User wants to create from scratch → Phase 1
**Mode B: Enhancement** — User has existing HTML to improve → Read, analyze, enhance
**Mode C: Conversion** — User has content in another format → Extract, then Phase 1

### Phase 1: Understand the Content

Ask the user via AskUserQuestion:

**Question 1: Purpose**
- "Product / SaaS" — selling a digital product or service
- "Personal / Portfolio" — showcasing yourself or your work
- "Event / Launch" — promoting an event, launch, or announcement
- "Business / Agency" — company or agency homepage

**Question 2: Content Readiness**
- "Yes, here it is" — proceed with their content
- "I have rough ideas" — help organize into sections
- "Just the topic" — generate content for them

### Phase 2: Choose a Style

Read `STYLE_PRESETS.md` and offer two paths:

**Step 2.0: Style Path Selection**

Ask: "How would you like to choose your landing page style?"
- "Show me options" — Generate 3 previews based on my needs (recommended)
- "I know what I want" — Let me pick from the preset list

**Available Presets:**

| Preset | Vibe | Best For |
|--------|------|----------|
| Liquid Glass | Premium, Apple-inspired, depth | Tech products, premium brands |
| SaaS Clean | Professional, trustworthy | B2B software, tools |
| Bold Startup | High-energy, confident | Startups, launches |
| Neon Tech | Futuristic, cyberpunk | Dev tools, AI, crypto |
| Warm Organic | Friendly, natural | Education, community, wellness |
| Editorial Luxe | Magazine-style, refined | Fashion, luxury, media |
| Brutalist Raw | Unconventional, bold | Creative agencies, art |
| Pastel Dream | Soft, playful | Consumer apps, lifestyle |
| Dark Cinema | Dramatic, immersive | Entertainment, gaming, music |
| Minimal Ink | Typography-driven, clean | Portfolios, writers, studios |

**If "Show me options"** → Step 2.1

**If "I know what I want"** → Show preset picker, skip to Phase 3

**Step 2.1: Mood Selection**

Ask: "What feeling should visitors have when viewing your page?"
- "Impressed / Professional" → SaaS Clean, Liquid Glass, Editorial Luxe
- "Excited / Energized" → Bold Startup, Neon Tech, Brutalist Raw
- "Calm / Focused" → Minimal Ink, Warm Organic, Pastel Dream
- "Inspired / Premium" → Liquid Glass, Dark Cinema, Editorial Luxe
- multiSelect: true (up to 2)

**Step 2.2: Generate 3 Style Previews**

Generate 3 mini preview HTML files (hero section only, ~100 lines each):
```
.preview/style-a.html
.preview/style-b.html
.preview/style-c.html
```

Each preview should be self-contained, animated, and show:
- Typography choice (heading/body hierarchy)
- Color palette (background, accent, text)
- Animation style (how elements enter)
- If Liquid Glass preset: include the full glass effect on at least one element

Present previews and ask user to pick or mix.

### Phase 3: Generate & Iterate

1. Read chosen preset from `STYLE_PRESETS.md` for design specs
2. Generate the complete landing page as a single HTML file
3. **If the chosen style uses Liquid Glass** → include the full SVG displacement filter system (see below)
4. Open in browser via `open [filename].html`
5. Present summary and offer iteration

### Phase 3.1: Art Direction Checkpoint

Before finalizing any landing page, mentally verify all 5 of these:

1. **Brand narrative exists** — The top of the page expresses a point of view, not just category labels
2. **Hero has a focal image idea** — orb, product tableau, editorial composition, layered scene, abstract object, or another memorable anchor
3. **Typography has contrast** — Display and body fonts create hierarchy and tone, not just readability
4. **Sections have rhythm** — At least one section changes alignment, composition, or pacing from the previous one
5. **Still a landing page** — Navigation, scanability, CTA clarity, and free browsing remain intact

If any answer is no, revise before delivery.

---

## CRITICAL: Liquid Glass Implementation

This section defines the **real** Liquid Glass effect. This is the signature visual of Frontend Landing — it must look like Apple's iOS liquid glass, not a basic frosted panel.

### Architecture Overview

The effect has 5 layers:

1. **SVG Displacement Filter** — Inline SVG with `feDisplacementMap` for real refraction distortion
2. **Backdrop Blur Layer** — `backdrop-filter: blur() saturate()` applied through the SVG filter
3. **Edge Highlight Gradient** — `::before` pseudo-element with directional light gradient
4. **Border Layers** — Two overlapping border spans with `mix-blend-mode: screen` and `overlay`
5. **Hover/Active Effects** — Radial gradient overlays for interaction feedback

### Layer 1: SVG Displacement Filter

Place this SVG once in `<body>`. It creates a displacement map that bends the backdrop around the edges of glass elements — this is what creates the "refraction" look.

```html
<!-- Liquid Glass SVG Filters — place once in <body> -->
<svg style="position:absolute;width:0;height:0" aria-hidden="true">
  <defs>
    <!-- Radial gradient for edge-only displacement -->
    <radialGradient id="glass-edge-mask" cx="50%" cy="50%" r="50%">
      <stop offset="0%" stop-color="black" stop-opacity="0"/>
      <stop offset="65%" stop-color="black" stop-opacity="0"/>
      <stop offset="100%" stop-color="white" stop-opacity="1"/>
    </radialGradient>

    <!-- Main liquid glass filter -->
    <filter id="liquid-glass" x="-35%" y="-35%" width="170%" height="170%" color-interpolation-filters="sRGB">
      <!-- Displacement map: encodes refraction vectors in R/G channels -->
      <!-- This base64 image is a pre-computed displacement field with edge falloff -->
      <feImage x="0" y="0" width="100%" height="100%" result="DISP_MAP"
        href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cdefs%3E%3CradialGradient id='g' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%23808080'/%3E%3Cstop offset='50%25' stop-color='%23808080'/%3E%3Cstop offset='85%25' stop-color='%23606060'/%3E%3Cstop offset='95%25' stop-color='%23404040'/%3E%3Cstop offset='100%25' stop-color='%23808080'/%3E%3C/radialGradient%3E%3C/defs%3E%3Crect width='200' height='200' fill='url(%23g)'/%3E%3C/svg%3E"
        preserveAspectRatio="none"/>

      <!-- Red channel displacement (slight offset for chromatic aberration) -->
      <feDisplacementMap in="SourceGraphic" in2="DISP_MAP" scale="28" xChannelSelector="R" yChannelSelector="G" result="RED_DISP"/>
      <feColorMatrix in="RED_DISP" type="matrix"
        values="1 0 0 0 0  0 0 0 0 0  0 0 0 0 0  0 0 0 1 0" result="RED_CH"/>

      <!-- Green channel displacement -->
      <feDisplacementMap in="SourceGraphic" in2="DISP_MAP" scale="24" xChannelSelector="R" yChannelSelector="G" result="GREEN_DISP"/>
      <feColorMatrix in="GREEN_DISP" type="matrix"
        values="0 0 0 0 0  0 1 0 0 0  0 0 0 0 0  0 0 0 1 0" result="GREEN_CH"/>

      <!-- Blue channel displacement (stronger offset for visible aberration) -->
      <feDisplacementMap in="SourceGraphic" in2="DISP_MAP" scale="20" xChannelSelector="R" yChannelSelector="G" result="BLUE_DISP"/>
      <feColorMatrix in="BLUE_DISP" type="matrix"
        values="0 0 0 0 0  0 0 0 0 0  0 0 1 0 0  0 0 0 1 0" result="BLUE_CH"/>

      <!-- Combine all channels: screen blend produces chromatic fringing at edges -->
      <feBlend in="GREEN_CH" in2="BLUE_CH" mode="screen" result="GB"/>
      <feBlend in="RED_CH" in2="GB" mode="screen" result="RGB"/>

      <!-- Soften the combined result -->
      <feGaussianBlur in="RGB" stdDeviation="0.4" result="RGB_SOFT"/>

      <!-- Edge mask: only apply aberration at edges, keep center clean -->
      <feImage x="0" y="0" width="100%" height="100%" result="EDGE_MASK"
        href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cdefs%3E%3CradialGradient id='m' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='black' stop-opacity='0'/%3E%3Cstop offset='60%25' stop-color='black' stop-opacity='0'/%3E%3Cstop offset='100%25' stop-color='white' stop-opacity='1'/%3E%3C/radialGradient%3E%3C/defs%3E%3Crect width='200' height='200' fill='url(%23m)'/%3E%3C/svg%3E"
        preserveAspectRatio="none"/>
      <feComposite in="RGB_SOFT" in2="EDGE_MASK" operator="in" result="EDGE_ABERRATION"/>

      <!-- Invert mask for clean center -->
      <feComponentTransfer in="EDGE_MASK" result="INV_MASK">
        <feFuncA type="table" tableValues="1 0"/>
      </feComponentTransfer>
      <feComposite in="SourceGraphic" in2="INV_MASK" operator="in" result="CENTER_CLEAN"/>

      <!-- Final composite: clean center + aberrated edges -->
      <feComposite in="EDGE_ABERRATION" in2="CENTER_CLEAN" operator="over"/>
    </filter>

    <!-- Lighter variant for buttons/small elements -->
    <filter id="liquid-glass-light" x="-20%" y="-20%" width="140%" height="140%" color-interpolation-filters="sRGB">
      <feImage x="0" y="0" width="100%" height="100%" result="DISP_MAP"
        href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cdefs%3E%3CradialGradient id='g' cx='50%25' cy='50%25' r='50%25'%3E%3Cstop offset='0%25' stop-color='%23808080'/%3E%3Cstop offset='60%25' stop-color='%23808080'/%3E%3Cstop offset='90%25' stop-color='%23606060'/%3E%3Cstop offset='100%25' stop-color='%23808080'/%3E%3C/radialGradient%3E%3C/defs%3E%3Crect width='200' height='200' fill='url(%23g)'/%3E%3C/svg%3E"
        preserveAspectRatio="none"/>
      <feDisplacementMap in="SourceGraphic" in2="DISP_MAP" scale="16" xChannelSelector="R" yChannelSelector="G" result="DISPLACED"/>
      <feGaussianBlur in="DISPLACED" stdDeviation="0.3"/>
    </filter>
  </defs>
</svg>
```

### Layer 2: Glass CSS (backdrop + filter)

```css
/* =========================================
   LIQUID GLASS: Core Material
   The .glass class creates the frosted glass effect.
   The SVG filter adds refraction on top.
   ========================================= */
.glass {
    position: relative;
    overflow: hidden;
    border-radius: clamp(16px, 2.5vw, 28px);
    /* Filter chain: SVG displacement + backdrop blur + saturation */
    filter: url(#liquid-glass);
    isolation: isolate;
}

/* Backdrop blur layer — applied to a child span for proper compositing */
.glass__backdrop {
    position: absolute;
    inset: 0;
    backdrop-filter: blur(20px) saturate(180%);
    -webkit-backdrop-filter: blur(20px) saturate(180%);
    background: rgba(255, 255, 255, 0.06);
    z-index: 0;
}

/* Content stays sharp above the blur */
.glass__content {
    position: relative;
    z-index: 1;
}

/* =========================================
   LIQUID GLASS: Edge Highlight (Layer 3)
   Simulates directional light refraction on edges
   ========================================= */
.glass::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: inherit;
    background: linear-gradient(
        135deg,
        rgba(255, 255, 255, 0.0) 0%,
        rgba(255, 255, 255, 0.12) 33%,
        rgba(255, 255, 255, 0.35) 66%,
        rgba(255, 255, 255, 0.0) 100%
    );
    pointer-events: none;
    z-index: 2;
    mix-blend-mode: overlay;
    opacity: 0.6;
}

/* =========================================
   LIQUID GLASS: Border Layers (Layer 4)
   Two overlapping semi-transparent borders
   with different blend modes for depth
   ========================================= */
.glass::after {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: inherit;
    padding: 1.5px;
    background: linear-gradient(
        135deg,
        rgba(255, 255, 255, 0.0) 0%,
        rgba(255, 255, 255, 0.15) 33%,
        rgba(255, 255, 255, 0.45) 66%,
        rgba(255, 255, 255, 0.0) 100%
    );
    -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    pointer-events: none;
    z-index: 3;
    mix-blend-mode: screen;
    opacity: 0.25;
}

/* Second border layer — overlay blend for iridescence */
.glass-border-overlay {
    position: absolute;
    inset: 0;
    border-radius: inherit;
    padding: 1.5px;
    background: linear-gradient(
        135deg,
        rgba(255, 255, 255, 0.0) 0%,
        rgba(255, 255, 255, 0.3) 33%,
        rgba(255, 255, 255, 0.6) 66%,
        rgba(255, 255, 255, 0.0) 100%
    );
    -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
    -webkit-mask-composite: xor;
    mask-composite: exclude;
    pointer-events: none;
    z-index: 4;
    mix-blend-mode: overlay;
}

/* Box shadow for depth */
.glass {
    box-shadow:
        0 0 0 0.5px rgba(255, 255, 255, 0.12) inset,
        0 1px 3px rgba(255, 255, 255, 0.15) inset,
        0 8px 32px rgba(0, 0, 0, 0.25),
        0 2px 8px rgba(0, 0, 0, 0.12);
}

/* =========================================
   LIQUID GLASS: Hover & Active (Layer 5)
   Radial gradient overlays for interaction
   ========================================= */
.glass:hover {
    box-shadow:
        0 0 0 0.5px rgba(255, 255, 255, 0.18) inset,
        0 1px 3px rgba(255, 255, 255, 0.2) inset,
        0 12px 40px rgba(0, 0, 0, 0.3),
        0 2px 8px rgba(0, 0, 0, 0.15),
        /* Chromatic aberration shadow on hover */
        -2px 0 12px rgba(255, 100, 150, 0.06),
        2px 0 12px rgba(100, 150, 255, 0.06);
}
```

### Layer 5: Mouse-Responsive Light (JavaScript)

For interactive glass elements, add mouse-responsive border gradients:

```javascript
/* =========================================
   LIQUID GLASS: Mouse-Responsive Light
   Makes the glass edge highlight follow mouse position,
   simulating how real glass catches light from different angles.
   Apply to any .glass element that should respond to mouse.
   ========================================= */
class LiquidGlassInteractive {
    constructor(element) {
        this.el = element;
        this.borderEl = element.querySelector('.glass-border-overlay');
        if (!this.borderEl) return;

        this.bindEvents();
    }

    bindEvents() {
        this.el.addEventListener('mousemove', (e) => {
            const rect = this.el.getBoundingClientRect();
            const x = ((e.clientX - rect.left) / rect.width - 0.5) * 100;
            const y = ((e.clientY - rect.top) / rect.height - 0.5) * 100;
            const angle = 135 + x * 1.2;

            // Shift the gradient angle and intensity based on mouse position
            this.borderEl.style.background = `linear-gradient(
                ${angle}deg,
                rgba(255,255,255,0.0) 0%,
                rgba(255,255,255,${0.12 + Math.abs(x) * 0.008}) ${Math.max(10, 33 + y * 0.3)}%,
                rgba(255,255,255,${0.4 + Math.abs(x) * 0.012}) ${Math.min(90, 66 + y * 0.4)}%,
                rgba(255,255,255,0.0) 100%
            )`;

            // Also shift the ::before highlight via CSS custom properties
            this.el.style.setProperty('--light-angle', `${angle}deg`);
        });

        this.el.addEventListener('mouseleave', () => {
            this.borderEl.style.background = '';
            this.el.style.removeProperty('--light-angle');
        });
    }
}

// Initialize on all interactive glass elements
document.querySelectorAll('.glass[data-interactive]').forEach(el => {
    new LiquidGlassInteractive(el);
});
```

### Glass HTML Structure

Every glass element must follow this structure:

```html
<div class="glass" data-interactive>
    <span class="glass__backdrop"></span>
    <div class="glass-border-overlay"></div>
    <div class="glass__content">
        <!-- Your content here -->
    </div>
</div>
```

### Glass Variants

| Variant | Use | Modification |
|---------|-----|-------------|
| **Frosted Card** | Feature cards, testimonials | Default `.glass` + standard blur (20px) |
| **Clear Button** | CTAs, nav buttons | Reduce blur to 8px, increase saturation to 200%, add `border-radius: 999px` for pill shape, use `#liquid-glass-light` filter |
| **Nav Bar** | Sticky navigation | `position: fixed; top: 0`, blur 16px, reduce background opacity |
| **Deep Hero** | Hero card overlay | Increase blur to 28px, stronger box-shadow, larger border-radius |
| **Over-Light** | Glass on bright backgrounds | Add `background: rgba(0,0,0,0.04)` overlay behind glass, reduce highlight opacity |

### Background Requirements

**Glass NEEDS a rich background to refract against.** Glass on flat solid color is invisible.

Always pair glass elements with:
- **Gradient mesh**: 2-3 overlapping `radial-gradient()` with different hue/position
- **Animated gradient**: CSS `@keyframes` slowly shifting gradient positions
- **Blurred imagery**: Large background images with CSS blur
- **Particle patterns**: Canvas-based dots or geometric shapes with color

```css
/* Example: Gradient mesh background for glass */
.glass-bg {
    background:
        radial-gradient(ellipse at 25% 40%, rgba(120, 119, 198, 0.4) 0%, transparent 50%),
        radial-gradient(ellipse at 75% 25%, rgba(168, 85, 247, 0.3) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 80%, rgba(59, 130, 246, 0.25) 0%, transparent 40%),
        #0c0c1d;
    background-attachment: fixed;
}

/* Animated mesh variant */
@keyframes meshShift {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
}
.glass-bg-animated {
    background-size: 200% 200%;
    animation: meshShift 15s ease-in-out infinite;
}
```

### Safari/Firefox Compatibility

```
NOTE: Safari and Firefox have limited support for SVG feDisplacementMap
inside filter chains with backdrop-filter. The SVG displacement (refraction)
may not render, but the frosted glass + borders + highlights will still look good.

Detection strategy:
- Check for Firefox via `navigator.userAgent`
- If Firefox, skip the `filter: url(#liquid-glass)` and rely on
  backdrop-filter + border layers only
- Safari supports backdrop-filter natively but may ignore feDisplacementMap
```

```javascript
/* Browser compatibility: disable SVG displacement on unsupported browsers */
(function() {
    const isFirefox = navigator.userAgent.toLowerCase().includes('firefox');
    if (isFirefox) {
        document.querySelectorAll('.glass').forEach(el => {
            el.style.filter = 'none';
        });
    }
})();
```

---

## Base CSS Architecture

### Art Direction Rules for Landing Pages

These rules apply across presets and should shape composition decisions:

#### 1. Hero Composition

Avoid the default formula of centered headline + subtext + two buttons + three cards underneath.

Prefer one of these hero patterns:

- **Split narrative hero** — text on one side, signature visual on the other
- **Layered editorial hero** — large headline over an abstract scene, object, or framed product surface
- **Immersive centered hero** — one dominant focal element surrounded by controlled supporting copy
- **Asymmetric hero** — offset layout with intentional negative space and one bold anchor element

Every hero should contain at least one of:

- a sculptural object or orb
- a product tableau or UI fragment with depth
- an abstract brand symbol
- a strong editorial text-image overlap
- a spatial lighting moment created with gradients, blur, or glass

#### 2. Typography Hierarchy

Type should communicate taste, not just content.

- Use a distinctive display/body pairing from presets or a similarly curated pairing
- Prefer visible contrast in voice: geometric + condensed, serif + clean sans, mono accents + elegant body, etc.
- Headline line breaks should feel composed, not mechanically balanced
- Labels, eyebrow text, and secondary copy should support the brand tone through tracking, casing, and restraint

#### 3. Section Rhythm

Do not stack sections with identical centered headings and identical card grids unless the content truly demands it.

Across the page, vary at least 2 of the following:

- left-aligned vs centered section intros
- open whitespace vs denser grids
- editorial text block vs structured cards
- light section vs dark/intense section
- flat content band vs framed/glass container

#### 4. Brand Worldbuilding

Even simple landing pages should imply a world around the product.

Use a combination of:

- atmospheric gradient meshes
- abstract shapes or light blooms
- grain or paper/noise textures
- repeated motif colors or forms
- consistent icon language (line icons, typographic marks, or text-only)

The worldbuilding must support the brand promise, not distract from it.

### Foundation Styles (include in every page)

```css
/* =========================================
   BASE: Reset & Layout Foundation
   ========================================= */
*, *::before, *::after {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
    scroll-snap-type: y proximity;
    height: 100%;
}

body {
    font-family: var(--font-body);
    background: var(--bg-primary);
    color: var(--text-primary);
    overflow-x: hidden;
    height: 100%;
    -webkit-font-smoothing: antialiased;
}

/* =========================================
   SECTIONS: Full-viewport segments
   ========================================= */
section {
    width: 100%;
    min-height: 100vh;
    min-height: 100dvh;
    padding: var(--section-padding);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    overflow: hidden;
}

/* Hero = exact viewport height */
.hero {
    height: 100vh;
    height: 100dvh;
    min-height: unset;
    scroll-snap-align: start;
}

/* =========================================
   RESPONSIVE TYPOGRAPHY & SPACING
   All values use clamp() — never fixed px
   ========================================= */
:root {
    --h1-size: clamp(2rem, 6vw, 5rem);
    --h2-size: clamp(1.5rem, 4vw, 3rem);
    --h3-size: clamp(1.125rem, 2.5vw, 1.5rem);
    --body-size: clamp(0.875rem, 1.5vw, 1.125rem);
    --small-size: clamp(0.75rem, 1vw, 0.875rem);

    --section-padding: clamp(2rem, 6vw, 6rem) clamp(1rem, 4vw, 4rem);
    --content-gap: clamp(1rem, 3vw, 3rem);
    --card-gap: clamp(0.75rem, 2vw, 1.5rem);
    --element-gap: clamp(0.5rem, 1vw, 1rem);
    --max-width: min(90vw, 1200px);

    --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
    --duration: 0.6s;
}

/* =========================================
   RESPONSIVE BREAKPOINTS
   ========================================= */
@media (max-width: 768px) {
    :root {
        --h1-size: clamp(1.75rem, 8vw, 3rem);
        --section-padding: clamp(1.5rem, 4vw, 3rem) clamp(1rem, 3vw, 2rem);
    }
    .grid { grid-template-columns: 1fr !important; }
}

@media (max-height: 600px) {
    :root {
        --section-padding: clamp(1rem, 3vw, 2rem) clamp(1rem, 3vw, 2rem);
        --h1-size: clamp(1.5rem, 5vw, 2.5rem);
    }
}

@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.2s !important;
    }
    html { scroll-behavior: auto; }
}
```

### Responsive Grid

```css
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 280px), 1fr));
    gap: var(--card-gap);
    width: 100%;
    max-width: var(--max-width);
}
```

---

## Scroll Animations

### Reveal on Scroll

```css
.reveal {
    opacity: 0;
    transform: translateY(30px);
    transition: opacity var(--duration) var(--ease-out-expo),
                transform var(--duration) var(--ease-out-expo);
}

.reveal.visible {
    opacity: 1;
    transform: translateY(0);
}

/* Stagger children */
.reveal:nth-child(1) { transition-delay: 0.05s; }
.reveal:nth-child(2) { transition-delay: 0.1s; }
.reveal:nth-child(3) { transition-delay: 0.15s; }
.reveal:nth-child(4) { transition-delay: 0.2s; }
.reveal:nth-child(5) { transition-delay: 0.25s; }
.reveal:nth-child(6) { transition-delay: 0.3s; }
```

### Animation Variants

```css
.reveal-scale { opacity: 0; transform: scale(0.92); }
.reveal-scale.visible { opacity: 1; transform: scale(1); }

.reveal-left { opacity: 0; transform: translateX(-40px); }
.reveal-left.visible { opacity: 1; transform: translateX(0); }

.reveal-blur { opacity: 0; filter: blur(8px); }
.reveal-blur.visible { opacity: 1; filter: blur(0); }
```

### Intersection Observer (include in every page)

```javascript
const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            entry.target.classList.add('visible');
        }
    });
}, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

### Counter Animation

```javascript
function animateCounter(el) {
    const target = parseInt(el.dataset.target);
    const duration = 1500;
    const start = performance.now();
    function update(now) {
        const progress = Math.min((now - start) / duration, 1);
        const eased = 1 - Math.pow(1 - progress, 3);
        el.textContent = Math.floor(target * eased).toLocaleString();
        if (progress < 1) requestAnimationFrame(update);
    }
    requestAnimationFrame(update);
}
```

---

## HTML Template

Complete page skeleton — adapt sections and glass usage based on user needs.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
    <!-- Fonts from preset -->
    <link rel="stylesheet" href="...">
    <style>
        /* :root variables (from chosen preset in STYLE_PRESETS.md) */
        /* Base styles (from this file § Base CSS Architecture) */
        /* Liquid Glass CSS (from this file § Liquid Glass Implementation) */
        /* Component styles (from preset) */
        /* Animations (from this file § Scroll Animations) */
        /* Responsive breakpoints (from this file § Base CSS Architecture) */
    </style>
</head>
<body>
    <!-- SVG displacement filters (from this file § Layer 1) -->
    <svg style="position:absolute;width:0;height:0" aria-hidden="true">...</svg>

    <!-- Sticky glass navigation -->
    <nav class="glass" style="position:fixed;top:0;...">
        <span class="glass__backdrop"></span>
        <div class="glass__content">...</div>
    </nav>

    <!-- Hero section with glass card -->
    <section class="hero glass-bg">
        <h1 class="reveal">Headline</h1>
        <p class="reveal">Subtext</p>
        <div class="glass reveal" data-interactive>
            <span class="glass__backdrop"></span>
            <div class="glass-border-overlay"></div>
            <div class="glass__content">
                <a href="#" class="cta-button">Get Started</a>
            </div>
        </div>
    </section>

    <!-- Feature section -->
    <section>
        <h2 class="reveal">Features</h2>
        <div class="grid">
            <div class="glass reveal">
                <span class="glass__backdrop"></span>
                <div class="glass__content">Feature 1</div>
            </div>
            <!-- more feature cards -->
        </div>
    </section>

    <!-- More sections... -->

    <!-- Footer -->
    <footer>...</footer>

    <script>
        /* Intersection Observer for .reveal */
        /* LiquidGlassInteractive for mouse-responsive borders */
        /* Counter animations (if stats section) */
        /* FAQ accordion (if FAQ section) */
        /* Mobile nav toggle */
        /* Browser compatibility check */
    </script>
</body>
</html>
```

---

## Iteration Guide

When the user asks for changes:

- **Change one section** — locate the `<section>` by class/id, edit only that section
- **Swap the entire style** — replace `:root` CSS variables and font `<link>`, update glass parameters if switching to/from Liquid Glass
- **Adjust glass intensity** — modify `feDisplacementMap scale` values in SVG, `blur()` amount, and border opacity
- **Adjust animations** — modify `.reveal` transition values and stagger timing
- **Add a new section** — insert a `<section>`, follow content density limits, add `.reveal` classes

---

## Anti-AI-Slop Rules

### Avoid These Defaults

**Fonts:** Inter, Roboto, Arial, Open Sans, Lato, system-ui as display font
**Colors:** `#6366f1` (generic indigo), `#8b5cf6` (generic purple), purple-on-white gradients, generic blue `#3b82f6` as primary
**Layouts:** Everything centered with identical spacing, 3 identical icon-title-text cards, generic hero with stock photo
**Icons:** No emoji icons unless user explicitly requests them

### Additional Anti-Template Rules

Avoid these common landing-page failure modes:

- **Generic SaaS hero** — small badge, predictable headline, two buttons, fake dashboard card, nothing memorable
- **Uniform section cadence** — every section centered, same width, same gap, same card pattern
- **Decorative glass without purpose** — glass applied everywhere with no focal hierarchy
- **Typography without point of view** — clean but bland pairings that flatten brand personality
- **Feature-first storytelling** — listing capabilities before establishing why the brand matters

### Prefer Instead

**Fonts:** Distinctive pairings from Google Fonts or Fontshare. Display + body contrast. Each preset in `STYLE_PRESETS.md` has a curated pairing.
**Colors:** Cohesive palettes with personality. One dominant + one sharp accent. Consider iridescent/prismatic accent tones for glass presets.
**Layouts:** Asymmetry where appropriate. Grid-breaking hero elements. Generous negative space.
**Details:** Subtle grain/noise textures, gradient mesh backgrounds, micro-interactions, staggered reveal timing.
**Storytelling:** A point-of-view opening, a recognizably branded hero, and section-to-section momentum.

---

## CSS Gotchas

### Negating CSS Functions

```css
margin-left: -clamp(1rem, 3vw, 3rem);           /* WRONG — silently ignored */
margin-left: calc(-1 * clamp(1rem, 3vw, 3rem));  /* CORRECT */
```

### backdrop-filter Compatibility

```css
backdrop-filter: blur(20px);
-webkit-backdrop-filter: blur(20px);  /* Required for Safari */
```

### scroll-snap Behavior

Use `scroll-snap-type: y proximity` not `y mandatory`. Mandatory feels jarring on landing pages.

### clamp() Minimum Readability

Body text minimum: `0.875rem` (14px). Never go below this in any clamp.

---

## Troubleshooting

**Glass invisible:** Background is too flat. Add gradient mesh or blurred image behind glass elements.
**Chromatic aberration too strong:** Reduce `scale` values in SVG `feDisplacementMap` (default: 28/24/20 for R/G/B).
**Performance issues on mobile:** Disable SVG filter on mobile (`@media (max-width: 768px) { .glass { filter: none; } }`), keep backdrop-filter only.
**Fonts not loading:** Check Google Fonts / Fontshare URL. Ensure font names match in CSS.
**Safari glass looks different:** Safari handles `feDisplacementMap` differently. The backdrop-filter + borders still provide a good glass look.

---

## Testing

After generating, suggest the user test at these sizes in browser DevTools:
- **Desktop:** 1920x1080, 1440x900
- **Tablet:** 768x1024 (portrait)
- **Mobile:** 375x667 (iPhone SE), 414x896 (iPhone 11)

---

## Example Session Flow

1. User: "I want to create a landing page for my AI startup"
2. Skill asks about purpose, content readiness
3. User shares product details
4. Skill asks about desired feeling (Impressed + Premium)
5. Skill generates 3 style previews (Liquid Glass, SaaS Clean, Dark Cinema)
6. User picks Liquid Glass, asks for darker background
7. Skill generates full landing page with real SVG displacement glass effect
8. Skill opens the page in browser
9. User requests tweaks to feature section
10. Final page delivered
