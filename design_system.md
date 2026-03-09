# codebrisk Studio Design System (Light Mode)

## Aesthetic Direction

- **Vibe**: Sleek, Architectural, Concierge White.
- **Core Philosophy**: Pristine surfaces, high-contrast typography, and depth created through soft shadows rather than glows. Maintain the same rigorous spacing and weight from the dark mode version.

## Color System (Light Theme)

The palette shifts from "Matrix Noir" to a high-end, gallery-like aesthetic.

| Role                  | Name           | Value     | Usage                                                  |
| :-------------------- | :------------- | :-------- | :----------------------------------------------------- |
| **Background Canvas** | Off-White      | `#F7F7F7` | Primary page background.                               |
| **Surface secondary** | Pristine White | `#FFFFFF` | Card backgrounds, panel surfaces.                      |
| **Primary Accent**    | Heritage Gold  | `#CC9966` | CTAs, borders, high-contrast highlights.               |
| **Secondary Accent**  | Muted Bronze   | `#9F7E59` | Subtle technical labels (e.g., "Crafting Excellence"). |
| **Text Main**         | Carbon Black   | `#1C1C1C` | Headings and primary copy.                             |
| **Text Muted**        | Mid-Grey       | `#666666` | Supporting text, paragraphs, and footer meta.          |

## Typography

- **Font Family**: `Inter` (sans-serif)
- **Scale**:
  - `Hero Headline`: 5xl to 8xl, Carbon Black (`#1C1C1C`), `-0.04em` tracking.
  - `Body Copy`: `text-lg` to `xl`, Mid-Grey (`#666666`), `font-weight: 300`.

## Layout & Components (Modified)

- **Cards / Panels**:
  - Background: `#FFFFFF`
  - Border: `1px solid rgba(0, 0, 0, 0.05)`
  - Shadow: `0 15px 30px rgba(0, 0, 0, 0.05)` (Replaces glows)
- **Buttons**:
  - **Primary**: Solid Gold (`#CC9966`) background, White text.
  - **Secondary**: Carbon Black border and text.

## Motion & Depth

- **Shadows**: Soft, multi-layered shadows to provide a sense of "floating" elevation on the off-white canvas.
- **Parallax**: Retained for background radial blends, but using very soft, low-opacity warm wash colors (light gold/blue).
