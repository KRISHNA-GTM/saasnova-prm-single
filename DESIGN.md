# Design System Strategy: The Editorial Operator

## 1. Overview & Creative North Star
This design system is anchored by a Creative North Star we call **"The Editorial Operator."** 

In an industry saturated with generic SaaS templates and "hype" visuals, we are moving in the opposite direction. We prioritize high-signal messaging and architectural integrity over visual clutter. The "Editorial" aspect draws from high-end business journals—using bold typography, intentional white space, and a strict grid to signal authority. The "Operator" aspect reflects an enterprise-grade focus on execution: clean, functional, and devoid of unnecessary decorative fluff.

We break the "template" look through **intentional asymmetry.** While the system is grid-based, we use staggered column alignments and overlapping elements (like a `primary_container` element slightly bleeding into a `surface_container_low` section) to create a bespoke, premium feel that looks custom-engineered rather than dragged-and-dropped.

## 2. Colors & Surface Architecture
The color palette uses a foundation of high-contrast neutrals balanced by a sophisticated primary blue and vibrant accents.

*   **Primary (#005da9):** Used for core branding and high-importance CTAs.
*   **Secondary (#914c08):** Derived from our signature orange, used for tactical highlights.
*   **Tertiary (#b20070):** Our "high-signal" pink, reserved for specific data points or "operator-led" focus areas.

### The "No-Line" Rule
Standard UI relies on 1px borders to separate content. **In this system, 1px solid borders for sectioning are strictly prohibited.** We define boundaries through background color shifts. Use `surface_container_low` for large section backgrounds to distinguish them from the main `surface` or `surface_container_lowest` (pure white) areas.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to create "nested" depth:
*   **Level 0 (Base):** `surface` (#f9f9f9)
*   **Level 1 (Sections):** `surface_container_low` (#f3f3f4)
*   **Level 2 (Cards/Modules):** `surface_container_lowest` (#ffffff)
*   **Level 3 (Interactive/Floating):** `surface_bright` with Glassmorphism.

### Glass & Signature Textures
For floating navigation or high-end overlays, use **Glassmorphism.** Apply semi-transparent surface colors with a `24px` backdrop blur. Main CTAs should not be flat; use a subtle linear gradient from `primary` to `primary_container` to add "soul" and professional polish.

## 3. Typography: The Authority Scale
Our typography is designed for a strong hierarchy that commands attention.

*   **Headlines (Manrope):** We use Manrope for all `display` and `headline` levels. It is modern, geometric, and carries an "operator" precision. Use `display-lg` (3.5rem) for hero statements to create immediate high-signal impact.
*   **Body & Labels (Inter):** Inter is used for all functional text (`body` and `label`). It provides maximum legibility for complex enterprise data.
*   **Contrast as Logic:** Always pair a `headline-lg` with a significantly smaller `body-md`. This gap in scale is what creates the "Editorial" feel—the large text acts as an anchor, while the smaller text provides the necessary detail without competing for attention.

## 4. Elevation & Depth
We convey hierarchy through **Tonal Layering** rather than structural lines.

*   **The Layering Principle:** Place a `surface_container_lowest` card on top of a `surface_container_low` background. This creates a soft, natural lift that mimics fine paper stocks.
*   **Ambient Shadows:** If a card requires a floating effect (e.g., on hover), use a shadow with a large blur (32px+) and low opacity (4%-8%). The shadow color must be a tinted version of `on_surface` (a deep blue-grey) rather than pure black.
*   **The Ghost Border:** If a container is placed on a background of the same color, you may use a "Ghost Border." This is an `outline_variant` stroke at **10% opacity**. It should be felt, not seen.
*   **Backdrop Blurs:** Use blurs on any element that sits "above" the content (modals, sticky headers). This ensures the layout feels integrated and premium.

## 5. Components

### Buttons
*   **Primary:** Gradient from `primary` to `primary_container`. White text. `0.25rem` (DEFAULT) roundedness.
*   **Secondary:** `surface_container_highest` background with `on_surface` text. No border.
*   **Tertiary:** Ghost style. No background, `primary` text, underlined only on hover.

### Cards & Lists
*   **Cards:** Forbid divider lines. Use `1.5rem` to `2rem` of internal padding. Separate header and body text using vertical white space (use the Spacing Scale) rather than rules.
*   **Lists:** To separate list items, use a subtle shift to `surface_container_high` on hover.

### Inputs & Chips
*   **Input Fields:** Use `surface_container_low` as the background. On focus, transition the background to `surface_container_lowest` and add a `primary` Ghost Border.
*   **Selection Chips:** Use `secondary_fixed` for active states to provide a warm, premium contrast against the primary blue.

### Campaign-Specific Components
*   **Signal Stat:** A large `display-md` number using the `tertiary` (Pink) color, paired with a small `label-md` description. Used to highlight key ROI or performance metrics.
*   **Operator Module:** A `surface_container_lowest` card with a `0.5rem` left-hand accent border in `primary`. Used for executive summaries.

## 6. Do’s and Don’ts

### Do
*   **Do** use extreme white space. If a section feels "full," increase the padding.
*   **Do** align text to a strict 8px grid.
*   **Do** use asymmetrical layouts (e.g., a 7-column content block next to a 5-column empty space) to create an editorial look.
*   **Do** use high-contrast color pairings (e.g., `on_primary_fixed` on `primary_fixed`).

### Don't
*   **Don't** use 100% opaque, high-contrast borders for anything other than specific accessibility requirements.
*   **Don't** use generic "SaaS Blue" (#2196F3). Stick strictly to our defined `primary` (#005da9).
*   **Don't** use "hype" language or exclamation marks. Let the typography and color scale communicate the importance.
*   **Don't** use heavy, dark backgrounds. The system must remain "light" and "airy" to feel enterprise-grade.