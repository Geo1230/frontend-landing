# Style Presets Reference

10 curated visual styles for Frontend Landing. Each preset defines a complete aesthetic system: layout pattern, typography, colors, and signature elements. **Every preset produces a genuinely different landing page — not just a color swap.**

Refer to SKILL.md for base CSS architecture, the full Liquid Glass implementation (SVG displacement + 5-layer system), animation patterns, and CSS gotchas. This file contains **only** preset-specific design specs.

---

## Preset Selection Guide

| Preset | Vibe | Best For |
|--------|------|----------|
| 1. Liquid Glass | Premium, modern, depth | Tech products, premium brands, Apple-inspired |
| 2. SaaS Clean | Professional, trustworthy | B2B tools, dev products, dashboards |
| 3. Bold Startup | High-energy, confident | Launches, pitch pages, Y Combinator energy |
| 4. Neon Tech | Futuristic, electric | AI products, dev tools, crypto, gaming |
| 5. Warm Organic | Friendly, natural | Education, wellness, community platforms |
| 6. Editorial Luxe | Refined, aspirational | Fashion, luxury, media, premium services |
| 7. Brutalist Raw | Unconventional, bold | Creative agencies, art, indie projects |
| 8. Pastel Dream | Soft, playful, inviting | Consumer apps, lifestyle, kids, social |
| 9. Dark Cinema | Dramatic, immersive | Entertainment, gaming, music, film |
| 10. Minimal Ink | Intellectual, precise | Portfolios, writers, studios, architecture |

### Mood -> Preset Mapping

| User Feeling | Recommended Presets |
|-------------|---------------------|
| "Impressed / Professional" | SaaS Clean, Liquid Glass, Editorial Luxe |
| "Excited / Energized" | Bold Startup, Neon Tech, Brutalist Raw |
| "Calm / Focused" | Minimal Ink, Warm Organic, Pastel Dream |
| "Inspired / Premium" | Liquid Glass, Dark Cinema, Editorial Luxe |

---

## 1. Liquid Glass

**Vibe:** Premium, modern, depth, light interaction — Apple-inspired materiality. This is the flagship preset.

**Layout Pattern:** Premium narrative landing page with a memorable hero composition on an animated gradient mesh background. Use a floating glass pill nav, a strong editorial hero layout, and glass only where it creates hierarchy. Feature cards are glass containers on the mesh. CTA section uses a large payoff panel.

**Typography:**
- Display: `SF Pro Display` fallback to `Outfit` (600/700) — geometric, modern, clean
- Body: `SF Pro Text` fallback to `Inter Tight` (400/500) — NOT Inter; Inter Tight is a distinct condensed variant
- Source: Google Fonts (Outfit + Inter Tight)

**Colors:**
```css
:root {
    /* Base */
    --bg-primary: #050510;
    --text-primary: #f5f7fb;
    --text-secondary: rgba(245, 247, 251, 0.58);

    /* Gradient mesh nodes */
    --mesh-1: rgba(118, 141, 255, 0.32);   /* cool spectral blue */
    --mesh-2: rgba(196, 212, 255, 0.18);   /* white-blue bloom */
    --mesh-3: rgba(112, 219, 255, 0.18);   /* icy cyan */
    --mesh-4: rgba(255, 255, 255, 0.10);   /* pure white haze */

    /* Accent — iridescent tones */
    --accent: #dbe7ff;                      /* iridescent white-blue */
    --accent-glow: rgba(190, 215, 255, 0.24);

    /* Glass tokens */
    --glass-bg: rgba(255, 255, 255, 0.05);
    --glass-border: rgba(255, 255, 255, 0.10);
    --glass-highlight: rgba(255, 255, 255, 0.20);
    --glass-blur: 20px;
    --glass-saturation: 180%;
    --glass-radius: clamp(16px, 2.5vw, 28px);

    /* Fonts */
    --font-display: 'Outfit', system-ui, sans-serif;
    --font-body: 'Inter Tight', system-ui, sans-serif;
}
```

**Background Pattern (animated mesh):**
```css
body {
    background:
        radial-gradient(ellipse at 25% 40%, var(--mesh-1) 0%, transparent 50%),
        radial-gradient(ellipse at 75% 25%, var(--mesh-2) 0%, transparent 50%),
        radial-gradient(ellipse at 50% 80%, var(--mesh-3) 0%, transparent 40%),
        radial-gradient(ellipse at 90% 60%, var(--mesh-4) 0%, transparent 45%),
        var(--bg-primary);
    background-attachment: fixed;
}

/* Animated variant — slow gradient drift */
body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
        radial-gradient(ellipse at 30% 50%, rgba(140, 100, 255, 0.2) 0%, transparent 50%),
        radial-gradient(ellipse at 70% 30%, rgba(100, 180, 255, 0.15) 0%, transparent 50%);
    background-size: 200% 200%;
    animation: meshDrift 20s ease-in-out infinite alternate;
    pointer-events: none;
    z-index: 0;
}

@keyframes meshDrift {
    0% { background-position: 0% 0%; }
    100% { background-position: 100% 100%; }
}
```

**Narrative Direction:**
- Open with aspiration, calm authority, or category redefinition — not feature inventory
- The first screen should feel like a premium product reveal
- Use a short tension-to-clarity message arc before deeper sections become more informational

**Signature Elements:**
- Floating glass navigation bar — pill-shaped, `position: fixed`, glass material
- Hero focal object — sculptural orb, refracted product tableau, or layered UI composition with depth
- Hero glass card or CTA container — uses full 5-layer glass system from SKILL.md
- Feature cards as glass containers on the mesh background
- Chromatic aberration visible at glass edges (from SVG displacement filter)
- Mouse-responsive border light on interactive glass elements
- Subtle grain texture overlay for materiality
- No emoji icons — use SVG line icons or text-only

**Glass Usage:** This preset uses the FULL Liquid Glass system from SKILL.md:
- Include the SVG `<filter id="liquid-glass">` in body
- Use `.glass` class with all 5 layers on nav, hero card, feature cards
- Add `data-interactive` to hero card and CTA for mouse-responsive borders
- Use `#liquid-glass-light` filter variant for smaller elements (buttons, badges)

**Grain Texture Overlay:**
```css
body::after {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 9999;
    opacity: 0.5;
}
```

**Hero Pattern:** Use one of these premium patterns: split narrative hero with text + focal orb, layered editorial hero with overlapping type and refracted product surface, or immersive centered hero with one dominant sculptural glass object. Avoid generic fake-dashboard-only heroes. The headline should feel composed and brand-led; the supporting visual should be memorable enough to identify the page at a glance.

**Section Treatment:** Alternate between open breathing space and denser structure. Feature cards are glass containers arranged in a 3-column grid, but at least one section should break the rhythm with asymmetry, editorial alignment, or a stronger visual block. Stats can use glass pill badges with counters. Final CTA should feel like a return to the opening atmosphere, not a generic footer-adjacent box.

**Avoid:** low-end purple gradients, overusing glass on every component equally, centered-everything composition, and generic SaaS dashboard mockups with no symbolic focal point.

---

## 2. SaaS Clean

**Vibe:** Professional, trustworthy, sharp, modern — Linear/Vercel energy

**Layout Pattern:** Left-aligned hero with right-side product mockup or illustration. Clean grid sections with precise spacing. Subtle background gradients per section.

**Typography:**
- Display: `General Sans` (600/700) — confident, geometric
- Body: `General Sans` (400/500) — single-family for cohesion
- Source: Fontshare

**Colors:**
```css
:root {
    --bg-primary: #fafafa;
    --bg-section-alt: #f4f4f5;
    --text-primary: #09090b;
    --text-secondary: #71717a;
    --accent: #18181b;
    --accent-highlight: #2563eb;
    --border: #e4e4e7;
    --card-bg: #ffffff;

    --font-display: 'General Sans', sans-serif;
    --font-body: 'General Sans', sans-serif;
}
```

**Signature Elements:**
- Subtle dotted grid background pattern on hero
- Clean card components with 1px borders, not shadows
- Pill-shaped badges/tags for categories
- Section dividers using thin horizontal rules
- Monochrome palette with one blue accent for CTAs
- Code-snippet styled feature highlights

**Narrative Direction:**
- Open with confident category positioning or operational clarity, not generic startup hype
- Make the product feel inevitable and trustworthy before listing details
- Keep the story calm, sharp, and rational: promise first, proof second, features third

**Glass Usage:** This preset does NOT use Liquid Glass. Omit SVG filters. Clean solid design only.

**Hero Pattern:** Split layout with a sharper editorial frame: concise badge, assertive left-aligned headline, and a right-side product tableau or focused UI crop with depth. Avoid the cliché of a tiny headline paired with a generic full dashboard screenshot. Use one visual crop that communicates product character immediately.

**Section Treatment:** Alternating white/gray sections with varied intro alignment. Mix one structured feature grid with one more evidence-driven section such as proof metrics, workflow steps, or a product principle block. Clean pricing table with highlighted recommended plan. Final CTA should feel precise and high-confidence, not loud.

**Avoid:** overusing blue accents, symmetrical section repetition, and default “B2B SaaS screenshot on the right” layouts with no compositional tension.

---

## 3. Bold Startup

**Vibe:** High-energy, confident, punchy, oversized — startup launch energy

**Layout Pattern:** Full-width hero with massive typography. Sections use bold color blocks. Feature sections break the grid with overlapping elements.

**Typography:**
- Display: `Clash Display` (600/700) — bold, impactful, geometric
- Body: `Satoshi` (400/500) — clean complement
- Source: Fontshare

**Colors:**
```css
:root {
    --bg-primary: #0a0a0a;
    --text-primary: #ffffff;
    --text-secondary: #a3a3a3;
    --accent: #ff6b35;          /* Electric orange */
    --accent-secondary: #fbbf24; /* Warm yellow */
    --card-bg: #171717;
    --border: #262626;

    --font-display: 'Clash Display', sans-serif;
    --font-body: 'Satoshi', sans-serif;
}
```

**Signature Elements:**
- Oversized hero headline (clamp to 7vw max) with gradient text
- Gradient text using `background-clip: text` with accent colors
- Animated counter stats section with large numbers
- Bold colored CTA buttons with hover scale effect
- Section numbers as large decorative elements (01, 02, 03...)
- Marquee/ticker banner for social proof logos

**Narrative Direction:**
- Open with momentum and ambition, but anchor it in one clear product claim
- Make the energy feel directed, not chaotic
- Use the first two sections to move from “big swing” to “why this matters now”

**Glass Usage:** Optional — can use glass for the nav bar only. Use the `#liquid-glass-light` variant. Feature cards should be solid dark with colored border accents instead.

**Hero Pattern:** Full-width dark canvas with one dominant headline lockup and a bold supporting visual rhythm: oversized type, large section marker, or cropped product fragment. A centered hero is acceptable only if it still feels art-directed; otherwise use an offset layout with one deliberate tension point. The hero should feel like a launch poster, not a template banner.

**Section Treatment:** Dark cards with colored left border accent, but break the cadence with at least one oversized statement section or proof strip between grids. Large section numbers as watermarks. Feature grid with colored icon backgrounds. CTA should resolve the page’s energy into a single bold ask.

**Avoid:** shouting everywhere at once, rainbow accents, and filling every section with equally loud typography.

---

## 4. Neon Tech

**Vibe:** Futuristic, electric, cyberpunk, developer-focused

**Layout Pattern:** Dark canvas with neon accent lines and glowing elements. Grid-based layout with visible grid lines in background. Asymmetric hero.

**Typography:**
- Display: `Space Grotesk` (700) — techy, geometric
- Mono: `JetBrains Mono` (400) — for code accents and labels
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #0a0f1c;
    --bg-grid: rgba(0, 255, 204, 0.03);
    --text-primary: #e2e8f0;
    --text-secondary: #64748b;
    --accent-cyan: #00ffcc;
    --accent-magenta: #ff00aa;
    --accent-glow: rgba(0, 255, 204, 0.3);
    --card-bg: rgba(15, 23, 42, 0.8);
    --border: rgba(0, 255, 204, 0.15);

    --font-display: 'Space Grotesk', sans-serif;
    --font-body: 'Space Grotesk', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
}
```

**Signature Elements:**
- Background grid pattern (50px grid lines at 3% opacity)
- Neon glow effects: `box-shadow: 0 0 20px var(--accent-glow)`
- Monospace labels and badges
- Animated scan line or pulse effects
- Terminal-style code blocks in feature descriptions
- Cyan/magenta dual accent palette

**Narrative Direction:**
- Open with a sense of technical edge, precision, or system power
- Treat the page like a controlled interface environment, not a gamer poster
- Reveal complexity in layers: signal first, system proof second, deeper capabilities later

**Glass Usage:** Can use glass for cards with a neon tint. Modify glass background to `rgba(0, 255, 204, 0.04)` and glass border to `rgba(0, 255, 204, 0.15)`. Use `#liquid-glass-light` variant only. The neon glow replaces the standard glass highlight.

**Hero Pattern:** Asymmetric hero with left-aligned headline and one high-contrast technical focal surface on the right: terminal, system panel, graph field, or luminous code environment. The visual should feel like infrastructure made visible. Keep motion subtle and intentional.

**Section Treatment:** Cards with neon border-bottom glow, but use at least one section that shifts from cards into a cleaner systems diagram, command list, or manifesto block. Stats displayed in monospace font. CTA button with pulsing glow animation used sparingly.

**Avoid:** excessive cyberpunk clutter, overly saturated magenta backgrounds, and visual noise that hurts readability.

**Grid Background:**
```css
body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
        linear-gradient(rgba(0, 255, 204, 0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0, 255, 204, 0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events: none;
}
```

---

## 5. Warm Organic

**Vibe:** Friendly, natural, approachable, handcrafted — feels human

**Layout Pattern:** Generous whitespace, rounded containers, organic flowing sections with wavy dividers. Content centered with comfortable reading width.

**Typography:**
- Display: `Fraunces` (600/700) — warm serif with personality
- Body: `DM Sans` (400/500) — friendly, rounded sans
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #fef7ed;        /* Warm cream */
    --bg-section-alt: #fdf2e9;
    --text-primary: #292524;
    --text-secondary: #78716c;
    --accent: #c2410c;            /* Warm terracotta */
    --accent-secondary: #15803d;  /* Forest green */
    --card-bg: #ffffff;
    --border: #e7e0d8;

    --font-display: 'Fraunces', serif;
    --font-body: 'DM Sans', sans-serif;
}
```

**Signature Elements:**
- Wavy SVG section dividers between sections
- Rounded corners everywhere (16-24px)
- Warm gradient backgrounds (cream to peach)
- Soft shadows with warm tone: `box-shadow: 0 4px 24px rgba(194, 65, 12, 0.08)`
- Organic blob shapes as decorative backgrounds

**Narrative Direction:**
- Open with warmth, trust, and human benefit rather than startup abstraction
- Let the page feel handcrafted and emotionally legible from the first screen
- Move from welcome, to reassurance, to practical value, to invitation

**Glass Usage:** None. This preset uses solid warm colors only.

**Hero Pattern:** Warm hero with a composed serif headline and either an organic product vignette, a framed lifestyle crop, or an abstract shape composition. Centered is fine here, but it should still feel authored through line breaks, spacing, and a distinctive visual anchor.

**Section Treatment:** White cards on cream background with rounded corners, but vary with one quieter text-led section or story block to avoid card fatigue. Feature icons in colored circles. Testimonials with rounded avatar photos. Wavy SVG separators between sections.

**Avoid:** childish illustrations, overly cute copy tone, and pastel candy colors that dilute the handcrafted warmth.

**Wavy Divider Pattern:**
```html
<svg viewBox="0 0 1440 100" preserveAspectRatio="none" style="width:100%;display:block">
  <path d="M0,40 C360,100 1080,0 1440,60 L1440,100 L0,100Z" fill="var(--bg-section-alt)"/>
</svg>
```

---

## 6. Editorial Luxe

**Vibe:** Magazine-style, refined, aspirational, curated — Vogue meets tech

**Layout Pattern:** Strong typographic hierarchy with deliberate pacing. Asymmetric layouts, large editorial whitespace, pull quotes, and one or two striking visual anchors. Content sections should feel curated rather than templated.

**Typography:**
- Display: `Cormorant Garamond` (500/700) — elegant editorial serif
- Body: `Work Sans` (400/500) — clean, modern contrast
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #faf9f7;        /* Warm white */
    --text-primary: #1a1a1a;
    --text-secondary: #6b6b6b;
    --accent: #b8860b;            /* Gold */
    --accent-secondary: #1a1a1a;
    --card-bg: #ffffff;
    --border: #e8e4df;
    --pull-quote-bg: #f0ece6;

    --font-display: 'Cormorant Garamond', serif;
    --font-body: 'Work Sans', sans-serif;
}
```

**Signature Elements:**
- Large serif headlines with dramatic size contrast (h1 vs body = 5:1 ratio)
- Pull quotes with oversized quotation marks
- Thin horizontal rules as section separators
- Image with text overlay layouts
- Gold accents for highlights and links
- All-caps small tracking for labels: `letter-spacing: 0.15em; text-transform: uppercase`

**Narrative Direction:**
- Open with a brand thesis, not a software feature summary
- Treat the first two sections like an editorial spread: statement, tension, perspective
- Use restrained CTA language so the page feels premium, not salesy

**Glass Usage:** None. Editorial uses solid backgrounds and typography as primary design.

**Hero Pattern:** Full-width with a commanding serif headline, restrained support copy, and either a large image, abstract composition, or spatial negative-space layout. Overlap headline and visual when possible. Minimal CTA — underlined text link or understated button. Subtitle in small all-caps with wide letter-spacing.

**Section Treatment:** Two-column layouts mixing text and imagery. Feature descriptions can be editorial paragraphs rather than card grids when appropriate. Testimonials should read like pull quotes. Break at least one section out of the normal grid so the page feels authored.

---

## 7. Brutalist Raw

**Vibe:** Bold, unconventional, attention-grabbing, raw — breaks the rules on purpose

**Layout Pattern:** Intentionally "broken" grid with overlapping elements, rotated text, visible borders. Combines mono typography with extreme size contrasts. Dense information areas next to empty space.

**Typography:**
- Display: `Syne` (700/800) — bold, distinctive, angular
- Mono: `Space Mono` (400/700) — raw, technical accent
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #f5f5f0;        /* Off-white / newsprint */
    --text-primary: #0a0a0a;
    --accent: #ff0000;            /* Pure red */
    --accent-secondary: #0000ff;  /* Pure blue */
    --card-bg: #ffffff;
    --border: #0a0a0a;            /* Black borders — visible, intentional */

    --font-display: 'Syne', sans-serif;
    --font-mono: 'Space Mono', monospace;
}
```

**Signature Elements:**
- Thick black borders (2-3px) on everything
- Rotated text labels: `transform: rotate(-90deg)`
- Oversized section numbers as background elements
- Mix of enormous and tiny type on the same section
- No border-radius — sharp corners everywhere
- Visible grid structure (CSS grid with gap as design element)

**Narrative Direction:**
- Open with a provocative statement or contrarian value proposition
- The aggression should feel intentional and graphic, not messy
- Use the page to frame bold differentiation first, then deliver proof and offer

**Glass Usage:** None. Brutalist is anti-glass by philosophy.

**Hero Pattern:** Asymmetric split with one giant statement, one dense counterweight block, and strong negative space. Use accent blocks and rotated text sparingly enough that the composition still reads instantly. CTA is a bordered box, not a filled button.

**Section Treatment:** Cards with thick black borders. Feature grid with visible gap lines. Insert at least one manifesto-like section or typographic wall between more structured blocks. Pricing in raw table format.

**Avoid:** random disorder, meme energy, and too many rotated elements competing for attention.

---

## 8. Pastel Dream

**Vibe:** Soft, playful, inviting, friendly — consumer product energy

**Layout Pattern:** Rounded everything, soft shadows, alternating pastel background sections. Centered layouts with card-based content. Floating decorative shapes.

**Typography:**
- Display: `Plus Jakarta Sans` (700/800) — friendly, geometric, modern
- Body: `Plus Jakarta Sans` (400/500) — cohesive single family
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #fdf4ff;          /* Lightest lavender */
    --bg-section-2: #fef3c7;        /* Soft yellow */
    --bg-section-3: #dcfce7;        /* Soft mint */
    --text-primary: #1e1b4b;        /* Deep indigo */
    --text-secondary: #6b7280;
    --accent: #c084fc;              /* Soft purple */
    --accent-secondary: #34d399;    /* Mint green */
    --card-bg: #ffffff;
    --border: rgba(0, 0, 0, 0.06);

    --font-display: 'Plus Jakarta Sans', sans-serif;
    --font-body: 'Plus Jakarta Sans', sans-serif;
}
```

**Signature Elements:**
- Floating decorative circles/blobs in pastel colors
- Large border-radius on everything (16-32px, pills for badges)
- Soft multi-color shadows: `box-shadow: 0 4px 20px rgba(192, 132, 252, 0.15)`
- Section backgrounds alternate between different pastel hues
- Bounce/spring animations on hover (scale + slight rotate)

**Narrative Direction:**
- Open with delight and clarity, not generic whimsy
- Make the page feel polished, productized, and emotionally light
- Balance softness with structure so the landing page still converts cleanly

**Glass Usage:** Optional light use. Can use glass for the hero card only, with modified glass tokens:
```css
--glass-bg: rgba(255, 255, 255, 0.4);    /* More opaque for light backgrounds */
--glass-border: rgba(255, 255, 255, 0.6);
--glass-blur: 12px;
```

**Hero Pattern:** Use a soft but distinctive hero scene: centered or slightly offset headline, floating shapes with restraint, and one rounded framed product or brand object that gives the page identity. The hero should feel designed, not merely cute.

**Section Treatment:** White cards with pastel shadows on alternating colored section backgrounds. Features with colorful icon badges. Include at least one cleaner section with more whitespace or a larger statement block to avoid toy-like repetition. Pricing cards with pastel header bars.

**Avoid:** sugary purple overload, childlike doodle energy, and excessive bounce effects that cheapen the product.

---

## 9. Dark Cinema

**Vibe:** Dramatic, immersive, cinematic, full-bleed — movie trailer energy

**Layout Pattern:** Full-bleed imagery and video backgrounds. Content overlays on dark gradients. Slow, dramatic reveal animations. Minimal UI — content IS the design.

**Typography:**
- Display: `Bebas Neue` (400) — cinematic, tall, impactful
- Body: `Source Sans 3` (400/500) — clean, readable on dark
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #000000;
    --bg-overlay: rgba(0, 0, 0, 0.6);
    --text-primary: #ffffff;
    --text-secondary: rgba(255, 255, 255, 0.6);
    --accent: #e11d48;             /* Cinema red */
    --accent-secondary: #fbbf24;   /* Award gold */
    --card-bg: rgba(255, 255, 255, 0.05);
    --border: rgba(255, 255, 255, 0.1);

    --font-display: 'Bebas Neue', sans-serif;
    --font-body: 'Source Sans 3', sans-serif;
}
```

**Signature Elements:**
- Full-viewport hero with dark gradient overlay
- Slow fade-in animations (1-1.5s duration)
- Letterboxed feel: extra horizontal padding for "widescreen" ratio
- Large scale transitions on reveal (0.95 to 1)
- Cinematic color grading: deep blacks, selective highlights

**Narrative Direction:**
- Open with drama, tension, and atmosphere before explanation
- Treat the page like a film trailer for the brand, but keep the information architecture readable
- Move from mood, to thesis, to proof, to invitation

**Glass Usage:** Optional. Can use glass on the nav bar and CTA section with deep dark tint:
```css
--glass-bg: rgba(0, 0, 0, 0.3);
--glass-border: rgba(255, 255, 255, 0.08);
--glass-blur: 24px;
```

**Reveal Animation Override:**
```css
.reveal {
    opacity: 0;
    transform: translateY(40px) scale(0.97);
    transition: opacity 1s var(--ease-out-expo),
                transform 1.2s var(--ease-out-expo);
}
```

**Hero Pattern:** Full-bleed dark background with one commanding headline and a strong visual field: image crop, abstract scene, or light-sculpted composition. Keep subtext minimal. Use a single CTA or understated dual action. The first screen should feel immersive and memorable rather than simply “dark with big text.”

**Section Treatment:** Content on dark with generous spacing. Alternate full-bleed atmosphere with calmer framed content sections so the page does not become monotonous. Stats use gold accent. Testimonials as cinematic title cards — large quote centered on black.

**Avoid:** overusing red accents, long paragraphs over busy imagery, and turning every section into the same black overlay block.

---

## 10. Minimal Ink

**Vibe:** Typography-driven, intellectual, precise, restrained — less is more

**Layout Pattern:** Maximum whitespace. Content in a narrow centered column (max-width: 680px). Typography is the primary design element. Almost no decoration.

**Typography:**
- Display: `Newsreader` (400/600) — literary, editorial, distinctive
- Body: `Source Serif 4` (400/500) — elegant body serif
- Source: Google Fonts

**Colors:**
```css
:root {
    --bg-primary: #ffffff;
    --text-primary: #111111;
    --text-secondary: #666666;
    --accent: #111111;             /* Black IS the accent */
    --accent-hover: #c41e3a;       /* Crimson on interaction only */
    --card-bg: #fafafa;
    --border: #e5e5e5;
    --max-content-width: 680px;

    --font-display: 'Newsreader', serif;
    --font-body: 'Source Serif 4', serif;
}
```

**Signature Elements:**
- Narrow content column (680px max)
- Drop caps on hero or section openers
- Elegant horizontal rules between sections
- No icons — text and typography do all the work
- Links are underlined, turn crimson on hover
- Large line-height (1.7-1.8) for body text
- Extreme font size contrast: h1 at 5rem, body at 1.05rem

**Narrative Direction:**
- Open with an idea worth reading, not a slogan
- Let clarity, restraint, and argument carry the brand
- Move from thesis, to reasoning, to offer with minimal ornament

**Glass Usage:** None. Minimal Ink is anti-decoration by design.

**Hero Pattern:** Minimal hero with a carefully composed headline, restrained supporting sentence, and a single text-link CTA. Centered is acceptable only if the spacing and line breaks feel deliberate. Consider offsetting one small element such as a label, rule, or note to avoid generic blog aesthetics.

**Section Treatment:** Long-form text sections with drop caps. Features as numbered paragraphs or short editorial lists. Testimonials as indented block quotes with em dash attribution. Pricing as simple stacked text. Use one or two wider interruptions, such as a quote band or manifesto line, so the page has rhythm.

**Avoid:** blog-like monotony, overly tiny text, and collapsing all landing-page structure into an essay.

---

## Font Pairing Quick Reference

| Preset | Display | Body | Source |
|--------|---------|------|--------|
| Liquid Glass | Outfit | Inter Tight | Google |
| SaaS Clean | General Sans | General Sans | Fontshare |
| Bold Startup | Clash Display | Satoshi | Fontshare |
| Neon Tech | Space Grotesk | JetBrains Mono | Google |
| Warm Organic | Fraunces | DM Sans | Google |
| Editorial Luxe | Cormorant Garamond | Work Sans | Google |
| Brutalist Raw | Syne | Space Mono | Google |
| Pastel Dream | Plus Jakarta Sans | Plus Jakarta Sans | Google |
| Dark Cinema | Bebas Neue | Source Sans 3 | Google |
| Minimal Ink | Newsreader | Source Serif 4 | Google |

---

## Glass Usage Summary

| Preset | Uses Liquid Glass? | Filter Variant | Notes |
|--------|-------------------|----------------|-------|
| Liquid Glass | FULL system | `#liquid-glass` + `#liquid-glass-light` | Primary glass showcase |
| SaaS Clean | No | — | Clean solid design |
| Bold Startup | Optional nav only | `#liquid-glass-light` | Glass is secondary |
| Neon Tech | Optional cards | `#liquid-glass-light` | Neon-tinted glass |
| Warm Organic | No | — | Solid warm colors |
| Editorial Luxe | No | — | Typography-driven |
| Brutalist Raw | No | — | Anti-glass philosophy |
| Pastel Dream | Optional hero | `#liquid-glass-light` | Light background glass |
| Dark Cinema | Optional nav/CTA | `#liquid-glass` | Dark tinted glass |
| Minimal Ink | No | — | Anti-decoration |

---

## DO NOT USE (Anti-AI-Slop)

**Fonts:** Inter, Roboto, Arial, Open Sans, Lato, system-ui as display font
**Colors:** `#6366f1` (generic indigo), `#8b5cf6` (generic purple), purple-on-white gradients, generic blue `#3b82f6`
**Layouts:** Everything centered with identical spacing, 3 identical icon-title-text cards, generic hero with stock photo
**Icons:** No emoji icons unless user explicitly requests them
**Glass:** Never use glass on a flat solid color background — it becomes invisible

---

## CSS Gotchas

### Negating CSS Functions

```css
right: -clamp(28px, 3.5vw, 44px);              /* WRONG — silently ignored */
right: calc(-1 * clamp(28px, 3.5vw, 44px));     /* CORRECT */
```

CSS does not allow a leading `-` before function names like `clamp()`, `min()`, `max()`. The browser silently discards the entire declaration. Always use `calc(-1 * ...)`.

### backdrop-filter Requires -webkit- Prefix

```css
backdrop-filter: blur(20px);
-webkit-backdrop-filter: blur(20px);  /* Required for Safari */
```

### clamp() Minimum Readability

Body text minimum: `0.875rem` (14px). Never go below this.

---

**Full Liquid Glass implementation (SVG filters, 5-layer system, JS interactivity) -> See SKILL.md.**
This file contains only preset-specific design specs.
