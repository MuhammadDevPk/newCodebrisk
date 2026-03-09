# codebrisk Light Mode Migration Guide

This guide ensures visual consistency when converting dark-mode pages to the "Concierge White" light mode aesthetic used on the home page.

## 1. Core Design Tokens (Tailwind Config)

Replace the existing dark-mode tokens with these values:

```javascript
colors: {
    background: {
        start: '#F7F7F7',
        end: '#F0F0F0'
    },
    accent: {
        primary: '#CC9966',    // Heritage Gold
        secondary: '#9F7E59'   // Muted Bronze
    },
    text: {
        main: '#1C1C1C',       // Carbon Black
        muted: '#666666'       // Mid-Grey
    },
    surface: {
        light: '#FFFFFF',
        hover: '#FAFAFA'
    }
}
```

## 2. Global Styles (CSS)

- **Canvas**: Background must be `#F7F7F7`.
- **Noise Overlay**: Set opacity to `0.03` to keep it subtle.
- **Shadows (Depth)**: In light mode, depth is created by shadows, not glows.
  - Standard Card: `box-shadow: 0 10px 40px rgba(0, 0, 0, 0.03);`
  - Hover State: `box-shadow: 0 20px 50px rgba(0, 0, 0, 0.06);`
- **Backdrop Blur**: Use `blur(12px)` for the navigation with `bg-white/80`.

## 3. Component Transformations

| Element              | Dark Mode State     | Light Mode Transformation                                  |
| :------------------- | :------------------ | :--------------------------------------------------------- |
| **Main Headlines**   | White               | Carbon Black (`#1C1C1C`)                                   |
| **Paragraphs**       | Muted Grey          | Mid-Grey (`#666666`)                                       |
| **Cards**            | Glass/Translucent   | Solid White (`#FFFFFF`) with 1px border `rgba(0,0,0,0.05)` |
| **Primary Button**   | Gold text / Outline | Solid Gold (`#CC9966`) with White text                     |
| **Secondary Button** | Outline             | Carbon Black (`#1C1C1C`) border and text                   |
| **Links**            | White               | Carbon Black or Gold on hover                              |

## 4. Imagery & Visual Assets

- **NO "Dark Holes"**: Avoid images with black backgrounds.
- **High-Key Visuals**: Use images featuring natural daylight, high-key lighting, and minimal shadows.
- **Screenshots**: Use Light Mode IDE themes (GitHub Light, Atom One Light).
- **Icons**: Use lower stroke weights (e.g., `1.2`) and lower opacity (`30-40%`) for a premium feel.

## 5. Technical Content Rules

- **Agentic AI**: Always highlight the stack: **n8n, LangChain, and LangGraph**.
- **Location**: Ensure "Lahore, Pakistan" and contact details are clearly visible in the footer using Mid-Grey.
- **Voice**: Maintain the "Architectural Concierge" tone—confident, technical, and precise.

---

_Reference `index.html` for the live implementation of these rules._
