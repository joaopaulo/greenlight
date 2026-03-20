# Design System Specification: The Analytical Editorial

## 1. Overview & Creative North Star
**The Creative North Star: "The Transparent Laboratory"**
To move beyond the "generic SaaS" look, this design system adopts an editorial-meets-institutional aesthetic. We are not just building a landing page; we are crafting an authoritative digital whitepaper. The system breaks the rigid "boxed-in" template by utilizing intentional asymmetry, high-contrast typography scales, and a departure from traditional borders. 

By prioritizing **Tonal Layering** over structural lines, we create an environment that feels airy yet academically rigorous. The goal is to convey precision through whitespace and trust through sophisticated depth.

---

## 2. Colors: The Depth Palette
Our palette relies on a sophisticated range of blues and neutrals to establish an institutional "Blue-Chip" feel.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders for sectioning. 
Structure is defined solely through background shifts. For example, a `surface-container-low` section sitting on a `surface` background creates a clear but soft boundary. This removes visual noise and directs focus to the data.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the following tiers to define importance:
- **Base Layer:** `surface` (#f8f9fa) – The canvas.
- **Structural Sections:** `surface-container-low` (#f3f4f5) – Use for secondary content areas.
- **Interactive Layers:** `surface-container-lowest` (#ffffff) – Reserved for primary cards or floating elements to provide maximum "lift."
- **Nesting:** An inner container must always be a different tier than its parent (e.g., a `surface-container-lowest` card nested inside a `surface-container-high` section).

### The "Glass & Gradient" Rule
To add a premium "tech-forward" soul, use **Glassmorphism** for floating navigation or hovering tooltips:
- **Background:** `surface` at 70% opacity.
- **Effect:** `backdrop-blur: 20px`.
- **CTAs:** Use a subtle linear gradient from `primary` (#0040a1) to `primary-container` (#0056d2) to give buttons a tactile, high-end finish.

---

## 3. Typography: Editorial Authority
We utilize a dual-font strategy to balance technical precision with approachable modernism.

*   **Display & Headlines (Manrope):** A geometric sans-serif that feels engineered yet warm. 
    - Use `display-lg` (3.5rem) with `-0.02em` letter spacing for hero statements to create a "High-End Magazine" feel.
    - Headlines should use `headline-md` (1.75rem) with generous `1.5` line-height to ensure breathability.
*   **Body & Labels (Inter):** The gold standard for readability.
    - **Body-lg (1rem):** Used for primary insights and descriptions.
    - **Label-md (0.75rem):** Used for technical metadata in data tables, always in `on-surface-variant` (#424654) to differentiate from narrative text.

---

## 4. Elevation & Depth: Tonal Architecture
We reject the "drop shadow" defaults of the early web. Depth is an atmospheric property, not a drop-shadow effect.

*   **The Layering Principle:** Reach for color shifts before shadows. A card using `surface-container-lowest` on a `surface-container` background provides enough contrast to be "read" as a separate element without adding visual weight.
*   **Ambient Shadows:** If a floating state is required (e.g., a modal or active dropdown), use:
    - `Box-shadow: 0 24px 48px -12px rgba(0, 24, 71, 0.08)`. 
    - Note the tint: the shadow uses a 8% opacity version of `on-primary-fixed` (#001847) rather than pure black, making it feel integrated with the blue-themed environment.
*   **The Ghost Border:** If accessibility requires a stroke (e.g., input fields), use `outline-variant` (#c3c6d6) at **20% opacity**. This creates a "suggestion" of a boundary rather than a hard wall.

---

## 5. Components

### Cards & Data Tables
*   **Cards:** Use `rounded-xl` (0.75rem) corners. Forbid divider lines between card sections. Use `spacing-6` (2rem) of vertical whitespace to separate header from body.
*   **Data Tables:** Remove all vertical and horizontal grid lines.
    - **Header:** Use `surface-container-high` background with `label-md` typography in all-caps.
    - **Rows:** Alternate between `surface` and `surface-container-low` for readability. 
    - **Hover State:** Apply `surface-tint` (#0056d2) at 5% opacity to the row.

### Accordion-Style FAQs
*   **The "Floating Leaf" Pattern:** Each FAQ item should be its own `surface-container-lowest` container. 
*   **Interaction:** On expansion, do not push content down abruptly; use a smooth transition. The active state should swap the background to `primary-fixed` (#dae2ff) to signal focus without using a border.

### Buttons & Inputs
*   **Primary Button:** Gradient of `primary` to `primary-container`. `rounded-full` for a modern, tech-focused silhouette.
*   **Input Fields:** Use `surface-container-low` backgrounds. Replace the traditional bottom-border with a 2px highlight in `primary` only during the `:focus` state.
*   **Chips:** Use `secondary-container` (#d6e3fb) with `on-secondary-container` (#586579) text. No borders; use `rounded-md` (0.375rem).

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Place a headline on the left with a large `spacing-24` (8.5rem) gap before the body text to create editorial interest.
*   **Do** use `tertiary` (#822800) sparingly as an accent color for "Alerts" or "Key Statistical Significance" markers—it provides a sophisticated "burnt orange" contrast to the blues.
*   **Do** embrace whitespace. If a section feels crowded, double the spacing token (e.g., move from `spacing-10` to `spacing-20`).

### Don't
*   **Don't** use 100% black text. Always use `on-surface` (#191c1d) to maintain a premium, softened look.
*   **Don't** use standard 1px dividers. If you must separate content, use a 4px thick line in `surface-variant` (#e1e3e4) that only spans 10% of the container width (the "Graphic Notch").
*   **Don't** use harsh, small-radius corners. Stick to `lg` (0.5rem) and `xl` (0.75rem) to maintain the "Modern Institutional" friendliness.