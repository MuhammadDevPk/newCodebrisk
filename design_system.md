# codebrisk Studio Design System

## Aesthetic Direction

- **Vibe**: Dark, cinematic, minimal and deeply confident. "Silicon Valley Agency" appeal.
- **Core Philosophy**: Generous negative space, large bold typography strictly left-aligned, pill-shaped buttons, and micro-glassmorphism. No flat colors—everything uses soft gradients and subtle overlays.

## Color System

The palette abandons harsh primaries for rich, dark cinematic tones punctuated by high-energy technical accents.

| Role                 | Name          | Value     | Usage                                                                   |
| :------------------- | :------------ | :-------- | :---------------------------------------------------------------------- |
| **Background Start** | Deep Night    | `#05070a` | Top gradient color for body/surface.                                    |
| **Background End**   | Deep Charcoal | `#0b1117` | Bottom gradient color for depth.                                        |
| **Primary Accent**   | Neon Cyan     | `#00d8ff` | Links, primary glowing elements, CTAs, highlights.                      |
| **Secondary Accent** | Soft Amber    | `#f4c76a` | Minimal, rare usage for secondary technical badges.                     |
| **Text Main**        | Off-White     | `#f5f7ff` | Headings, primary copy. Ensures legibility without harsh #FFF contrast. |
| **Text Muted**       | Slate Gray    | `#9297a5` | Paragraphs, meta text, inactive icons.                                  |

## Typography

- **Font Family**: `Inter` (sans-serif)
- **Characteristics**: Clean grotesk styling, tightly tracked headings across the board.
- **Scale**:
  - `Hero Headline`: 5xl to 7xl+ (`text-[5rem]`), tight tracking (`-0.04em`), `font-weight: 500`.
  - `Section Titles`: 3xl to 4xl, tight tracking, `font-weight: 600`.
  - `Body Copy`: `text-lg` to `text-xl`, relaxed leading, `font-weight: 300` (light) for a sophisticated editorial feel.

## Layout & Components

- **Cards / Panels**:
  - `class="glass-panel"`
  - Background `rgba(255, 255, 255, 0.02)`
  - Border `1px solid rgba(255, 255, 255, 0.05)`
  - High blur factor (`backdrop-filter: blur(16px)`)
- **Radii**:
  - Panels: `20px` (modern soft rounding)
  - Buttons: `full` (pill shape)
- **Micro-Interactions**:
  - `.subtle-glow`: Triggers a faint #00d8ff outline transition on card hover.
  - Button Hover: Outlined pills inherit a subtle background tint (`rgba(0, 216, 255, 0.05)`) and border color change. Solid buttons gain a mild cyan drop shadow.

## Motion Guidelines

- **Noise Overlay**: Fixed position SVG fractal noise (`opacity: 0.15`), providing texture.
- **Parallax Gradient**: A fixed background div containing ambient radial glows (`radial-gradient`), bound to `window.scrollY * 0.15` via vanilla JS, producing a smooth ambient depth shift when scrolling.
