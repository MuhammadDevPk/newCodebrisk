# codebrisk Design System & UI Specifications

This document outlines the design foundations, aesthetics, and interaction models for the newly engineered codebrisk landing page. We aimed for an ultra-premium, "Silicon Valley Agency" vibe that immediately builds trust with enterprise and startup clients looking for $10k+ engagements.

## 1. Aesthetic Philosophy & "Human-Designed" Guidelines

To ensure the design does not look generic or "AI-generated":

- **Irregularity over strict symmetry**: The Tech Matrix hero component is rotated slightly in 3D space (`rotate-y-[-5deg] rotate-x-[5deg]`). The Services cards use an alternating staggered layout (`even:translateY(40px)`).
- **Matte Glassmorphism**: High blur filters (`backdrop-filter: blur(12px)`) with solid, low-opacity backgrounds (`rgba(30,30,32,0.4)`), avoiding cheap high-opacity gloss.
- **Micro-noise**: A fixed SVG fractal noise overlay at `0.03` opacity creates film-grain texture, adding palpable depth that pure CSS gradients lack.

---

## 2. Color Palette (Dark Mode Native)

The palette uses deep neutral bases accented by precise, vibrant technical colors.

| Token              | Hex       | Usage                                                                  |
| ------------------ | --------- | ---------------------------------------------------------------------- |
| **Base Surface**   | `#0f0f11` | Primary background. Deepest charcoal, near OLED black.                 |
| **Card Surface**   | `#1a1a1c` | Background for glass panels and tech grid items.                       |
| **Electric Teal**  | `#00d4ff` | Primary Accent. Used for CTAs, active states, and tech glow.           |
| **Warm Gold**      | `#f4c430` | Secondary Accent. Used for AI/Premium highlights and hover inversions. |
| **Soft Lavender**  | `#e8ecff` | Tertiary Accent. Used for Design/UI specific highlights.               |
| **Text Primary**   | `#ffffff` | Headings and high-contrast text.                                       |
| **Text Secondary** | `#9ca3af` | Paragraphs and supporting text.                                        |

_Gradients:_

- **Text Gradients**: Subtle white-to-gray (`#ffffff` to `#a0a0b0`) for the main heading to prevent blinding contrast.
- **Mesh Background**: Radial gradients using hsla to create faint glowing orbs behind the geometric layout.

---

## 3. Typography Scale

We utilize two highly legible, modern typefaces to strike a balance between mechanical precision and editorial elegance.

- **Primary Display (Headings)**: `Clash Display` (Variable)
  - `Hero`: 5xl to 8xl (tight tracking, `-0.02em`)
  - `Section Titles`: 4xl to 5xl
  - `H3 Cards`: 2xl
- **Secondary/Body**: `Inter` (Variable)
  - `Body L`: 1.125rem / 18px
  - `Body M`: 1rem / 16px (relaxed leading)
  - `Tags/Meta`: 0.75rem / 12px (All Caps, wide tracking)

---

## 4. Animation & Micro-Interactions (GSAP + Framer Motion concepts)

### Magnetic Cursor (Custom)

A custom DOM-based cursor tracking the mouse position.

- **Default State**: 8px solid teal dot with a 40px outlined trailing ring.
- **Hover State (`.magnetic`)**: The dot shrinks to 0px, and the ring expands to 60px with a blurred gold backdrop (`#f4c430`), snapping slightly to the targeted element.

### Button Hover (Liquid Fill)

- **Primary Buttons (`.btn-primary`)**: Outlined buttons that use a `::before` pseudo-element sweeping from left to right with a soft gradient, invoking a liquid fill feeling instead of a harsh color snap.

### Scroll Trigger Details

- **Hero Stagger**: Content slides upward `30px` while fading in, staggered by `0.15s` via GSAP.
- **Tech Grid**: Grid squares scale up from `0.8x` with an elastic bounce (`ease: "back.out(1.5)"`).
- **Process Timeline**: Uses GSAP ScrollTrigger to translate the horizontal flex container leftward (`xPercent: -30`) as the user scrolls downwards, mimicking a native horizontal scroll journey.

---

## 5. Mobile & Responsive Strategy

**Breakpoints Strategy (Tailwind Native):**

1. **Desktop/Ultrawide (`>= 1024px`)**:
   - Hero: 50/50 split layout.
   - Services: 2x2 staggered grid.
   - Timeline: Horizontal scroll takeover.
   - UX: Custom magnetic cursor enabled.
2. **Tablet (`768px - 1023px`)**:
   - Hero: Stacked layout, text centered above the tech grid matrix.
   - Services: Maintained 2 column grid, spacing tightened.
   - UX: Magnetic cursor disabled, fallback to system pointer.
3. **Mobile (`< 768px`)**:
   - Hero: Typography clamped down (`text-5xl`), padding reduced.
   - Services: Staggered effect removed. 1 column grid, full width cards.
   - Timeline: Horizontal GSAP scrub is disabled, reverting to a standard vertical stacked layout for readability.

---

## 6. Development Notes

- The provided index.html is a standalone Prototype / Single Page build utilizing Tailwind CDN and GSAP CDN.
- For production deployment, you can port the structure directly into a Next.js or Nuxt.js repository.
- The CSS noise filter (`#noiseFilter`) uses SVG `feTurbulence`. This is highly performant but should be tested on low tier mobile devices. If framerate drops, swap for a compressed static noise `.png`.
