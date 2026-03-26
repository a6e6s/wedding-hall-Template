```markdown
# Design System Specification: The Ethereal Curator

## 1. Overview & Creative North Star
The North Star for this design system is **"The Ethereal Curator."** 

In the high-end wedding industry, digital experiences must feel as curated and intentional as a physical venue. We are moving away from the rigid, "boxed-in" nature of standard web grids toward an editorial layout that breathes. By utilizing the 'Cairo' typeface for both English and Arabic, we achieve a bridge between modern geometric precision and traditional calligraphic elegance. 

The aesthetic is defined by **intentional asymmetry and tonal depth**. Rather than using lines to separate ideas, we use space, light, and subtle shifts in surface color to guide the eye. Overlapping elements and floating "glass" cards create a sense of three-dimensional luxury, making the user feel they are navigating a high-end invitation rather than a database of halls.

---

## 2. Colors: Depth over Boundaries
The palette is a sophisticated interplay between deep regal purples (`primary`) and sun-drenched golds (`secondary`), grounded by a series of off-white and soft grey surfaces.

### The "No-Line" Rule
**Explicit Instruction:** Use of 1px solid borders for sectioning is strictly prohibited. 
In this design system, boundaries are invisible. Use background color shifts to define areas. For example, a `surface-container-low` section should sit directly on a `surface` background. The transition is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of luxury materials:
*   **Base Layer:** `surface` (#faf9fc) - The canvas.
*   **Sectional Layer:** `surface-container-low` (#f5f3f7) - Use for large background blocks.
*   **Component Layer:** `surface-container-highest` (#e3e2e6) - Use for interactive cards or hall selection modules.
*   **Nesting:** An inner detail card (like a "Price Breakdown") should use `surface-container-lowest` (#ffffff) to appear as if it is rising out of the parent container.

### The "Glass & Gradient" Rule
To elevate the experience, apply **Glassmorphism** to floating navigation bars or selection modals. Use `surface_variant` at 60% opacity with a `20px` backdrop-blur. 
For primary CTAs, do not use flat colors. Apply a subtle linear gradient from `primary` (#51207a) to `primary_container` (#6a3a93) at a 135-degree angle to provide a "silk-like" visual soul.

---

## 3. Typography: The Cairo Monolith
We have standardized on **Cairo** to ensure a seamless, premium bilingual experience. Cairo’s wide counters and modern terminal strokes provide the "Modern Wedding" feel requested.

*   **Display (lg/md):** Reserved for hero headlines (e.g., "Find Your Forever Venue"). Use `primary` or `on_surface`.
*   **Headline (lg/md/sm):** Used for Hall Names and section titles. Headlines should feel authoritative yet airy.
*   **Title (lg/md):** Used for card headings and high-level navigation.
*   **Body (lg/md):** The workhorse for hall descriptions. Ensure line-height is generous (at least 1.6x) to maintain the editorial feel.
*   **Label (md/sm):** Used for metadata (e.g., "Capacity", "Availability").

*Note: While the provided JSON mentions 'beVietnamPro', this has been overridden by the 'Cairo' requirement for this specific implementation.*

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows and borders create "visual noise." We achieve hierarchy through **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking `surface-container` tiers. A `surface-container-lowest` card placed on a `surface-container-high` background creates a natural, soft lift.
*   **Ambient Shadows:** For floating hall-selection cards, use shadows that mimic natural light.
    *   **Blur:** 32px to 64px.
    *   **Opacity:** 4%–6% of `on_surface` (#1b1b1e).
    *   **Color:** Tint the shadow with a hint of `primary` to ensure it feels integrated into the theme.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use `outline_variant` at **15% opacity**. Never use a 100% opaque border.
*   **Transitions:** All elevation changes must use an `ease-in-out` transition of `300ms`. Movement should feel "weighted" and graceful, like the opening of a heavy velvet curtain.

---

## 5. Components

### Buttons
*   **Primary:** A gradient from `primary` to `primary_container`. Corner radius: `full`. Text: `on_primary`. Use for "Book Now."
*   **Secondary:** `secondary_container` background with `on_secondary_container` text. This provides the "Gold" accent from the logo without being overwhelming.

### Hall Selection Cards
*   **Layout:** Asymmetric. The image should slightly overflow the card container or use a `xl` (1.5rem) rounded corner on only three sides.
*   **Content:** Forbid divider lines. Use `spacing.6` (2rem) of vertical white space to separate the hall name from its features.
*   **Background:** Use `surface_container_lowest`.

### Input Fields
*   **Style:** Minimalist. No bottom line. Use a soft `surface_container_high` background with `md` (0.75rem) rounded corners.
*   **States:** On focus, the background shifts to `primary_fixed` with a 20% opacity `primary` ghost border.

### Selection Chips
*   **Unselected:** `surface_variant` background, `on_surface_variant` text.
*   **Selected:** `primary` background, `on_primary` text. No border.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Whitespace:** Use `spacing.12` or `spacing.16` between major sections to let the design breathe.
*   **Use Subtle Gold:** Use the `secondary` gold palette for highlights (ratings, icons, premium badges) only. It is an accent, not a base.
*   **Align to the Type:** Cairo has a distinct x-height; ensure icons are optically centered to the font, not just mathematically.

### Don’t:
*   **Don't use Dividers:** Never use a horizontal rule (`<hr>`) to separate content. Use a `surface-container` shift or `spacing.8`.
*   **Don't use Pure Black:** Always use `on_surface` (#1b1b1e) for text. Pure black is too harsh for the Royal Amethyst palette.
*   **Don't use Tight Corners:** Avoid `none` or `sm` roundedness. Stay within `md` to `xl` to maintain the "soft" wedding aesthetic.
*   **Don't Center-Align Everything:** While elegant, over-centering feels like a template. Use left-aligned (or right-aligned for Arabic) headlines with asymmetric image placements for a custom, high-end feel.```