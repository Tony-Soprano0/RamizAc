# Design System Specification: The Architectural Precision Framework

## 1. Overview & Creative North Star
**Creative North Star: "The Editorial Engineer"**

This design system rejects the "blue-collar" template aesthetic in favor of a high-end, editorial approach to HVAC services. We are moving away from loud, industrial cliches and toward a visual language that mirrors the precision of expert mechanical engineering. The interface should feel like a premium architectural magazine: structured, spacious, and authoritative.

We achieve this through **Intentional Asymmetry**. Instead of rigid, centered grids, we utilize "The Shift"—offsetting headlines or imagery to create dynamic paths for the eye. We favor breathing room over density, ensuring every element feels intentional rather than "pasted."

---

## 2. Color & Tonal Depth
Our palette is rooted in the "New Neutral" philosophy. We avoid pure blacks and harsh whites to reduce eye strain and establish a sophisticated, high-end atmosphere.

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are strictly prohibited for defining sections or containers. Structure must be created through:
*   **Background Shifts:** Using `surface-container-low` against a `surface` background.
*   **Tonal Transitions:** Defining edges via subtle contrast rather than physical strokes.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of premium materials.
*   **Base Layer:** `surface` (#faf9f6) or `background` (#faf9f6).
*   **Secondary Layer:** `surface-container-low` (#f4f3f0) for subtle grouping.
*   **Elevation Layer:** `surface-container-lowest` (#ffffff) for high-priority interactive cards.
*   **Accent Layer:** `tertiary-fixed` (#e8e2d9) for informational callouts.

### The "Glass & Gradient" Rule
To elevate beyond flat design, use **Glassmorphism** for floating navigation or overlay modals. Use `surface-bright` with a 70% opacity and a `backdrop-blur: 12px`.
*   **Signature Gradient:** For primary CTAs, apply a subtle linear gradient from `primary` (#041635) to `primary-container` (#1b2b4b) at a 135-degree angle. This adds a "weighted" metallic feel appropriate for a high-end contracting brand.

---

## 3. Typography
We utilize a dual-typeface system to balance technical precision with approachable readability.

*   **Display & Headlines (Inter):** High-impact, geometric, and bold. Use `tight` letter-spacing (-0.02em) for all headlines to create a "locked-in" architectural feel. 
    *   *Role:* Conveys authority and the "contractor as an expert" persona.
*   **Title & Body (Manrope):** Slightly more humanist and open. Manrope’s geometry complements Inter but offers better legibility for long-form service descriptions.
    *   *Role:* Conveys transparency, reliability, and technical detail.

### Typography Scale
| Level | Font | Weight | Size | Tracking |
| :--- | :--- | :--- | :--- | :--- |
| **Display-lg** | Inter | Bold (700) | 3.5rem | -0.02em |
| **Headline-md**| Inter | Bold (700) | 1.75rem | -0.01em |
| **Title-md**   | Manrope | Semi-Bold (600) | 1.125rem | 0 |
| **Body-lg**    | Manrope | Regular (400) | 1rem | 0.01em |
| **Label-sm**   | Manrope | Bold (700) | 0.6875rem | 0.05em (Caps) |

---

## 4. Elevation & Depth
We eschew the "material shadow" in favor of **Tonal Layering** and **Ambient Light.**

*   **The Layering Principle:** Depth is achieved by placing lighter surfaces on darker backgrounds. A `surface-container-lowest` (#ffffff) card should sit on a `surface-container-low` (#f4f3f0) section to create a soft, natural lift.
*   **Ambient Shadows:** For interactive floating elements, use a "Large-Diffusion" shadow:
    *   `box-shadow: 0 12px 32px -4px rgba(27, 43, 75, 0.06);`
    *   *Note:* The shadow color is a tint of our `primary` (#1B2B4B), not grey.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use `outline-variant` at 15% opacity. Never use a 100% opaque border.

---

## 5. Components

### Buttons (The "Precision Tactile" Style)
*   **Primary:** `primary` background, `on-primary` text. No border. Radius: `md` (0.75rem).
*   **Secondary:** `secondary-container` background, `on-secondary-container` text.
*   **Interaction:** On hover, use a `1px` upward translation and increase shadow diffusion.

### Cards & Sections
*   **Forbid Dividers:** Do not use `<hr>` tags or border-bottoms. Separate content via 48px/64px vertical spacing or a shift to `tertiary-fixed` (#e8e2d9) backgrounds.
*   **Corner Radius:** Standardize on `md` (0.75rem) for cards and `lg` (1rem) for hero imagery.

### Input Fields
*   **Style:** Minimalist. Use `surface-container-highest` background with a `ghost-border`.
*   **Focus:** Transition the border to `secondary` (#395f94) and add a soft 4px outer glow of the same color at 10% opacity.

### Featured Component: The "Service Spec" List
Instead of standard bullet points, use a horizontal "Service Spec" layout. Small `label-sm` headers in `secondary` (#395f94) above `body-lg` text, separated by generous whitespace rather than lines.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical layouts where the image and text are slightly offset.
*   **Do** use `primary` (#041635) for all high-level navigation to anchor the page.
*   **Do** use "Muted Teal" (#3D8B7A) exclusively for trust indicators (Reviews, Certifications, "In Stock").
*   **Do** embrace generous padding (min 80px) between major sections.

### Don’t:
*   **Don’t** use full-bleed dark sections for anything other than the Footer. The site must breathe.
*   **Don’t** use generic stock photos of people pointing at AC units. Use architectural shots of vents, blueprints, or clean, macro-shots of high-end hardware.
*   **Don’t** use "Alert Red" for errors if possible. Use `error_container` (#ffdad6) to keep the premium, soft aesthetic even in "negative" states.
*   **Don’t** use standard 4-column grids. Try a 3-column grid where one column is intentionally left as whitespace.