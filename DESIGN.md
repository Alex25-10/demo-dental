```markdown
# Design System Document: The Clinical Atelier

This document outlines the visual language and implementation strategy for a premium, editorial-driven dental experience. We are moving away from the "sterile hospital" aesthetic and toward a "luxury boutique" feel. Our goal is to communicate precision, invisibility (aligners), and high-end medical expertise through sophisticated layering and authoritative typography.

---

## 1. Creative North Star: "The Invisible Precision"
The design system is built on the concept of **The Invisible Precision**. Much like the clear aligners the clinic specializes in, the UI should feel transparent, lightweight, and perfectly fitted. 

We break the "standard template" look by utilizing:
*   **Intentional Asymmetry:** Hero sections and image placements should feel curated, like a high-end fashion magazine, rather than a rigid bootstrap grid.
*   **Breathable Luxury:** Whitespace is not "empty space"; it is a premium commodity that signals confidence and calm.
*   **The Depth of Detail:** We replace harsh lines with tonal shifts, suggesting quality through subtlety rather than loudness.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a deep, authoritative Navy (`primary`), accented by the warmth of Gold (`tertiary`), and supported by a clinical yet soft Grey/White scale (`surface`).

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Traditional dividers are forbidden. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should transition directly into a `surface` background to denote a change in content.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper.
*   **Base:** `surface` (#f8f9fa) for the main canvas.
*   **Elevated Content:** Use `surface-container-low` (#f3f4f5) for large content blocks.
*   **Interactive Focus:** Use `surface-container-lowest` (#ffffff) for cards or inputs to make them "pop" against the slightly darker background.

### Glass & Gradient Rule
To evoke the "clear" nature of the product:
*   **Glassmorphism:** For floating navigation or modal overlays, use `surface` at 80% opacity with a `20px` backdrop-blur. 
*   **Signature Textures:** For primary CTAs, use a subtle linear gradient from `primary` (#00113a) to `primary_container` (#002366) at a 135-degree angle. This adds "soul" and prevents the navy from feeling flat or heavy.

---

## 3. Typography: The Editorial Voice
We use a high-contrast pairing of **Noto Serif** (Sophistication) and **Manrope** (Modern Precision).

*   **Display & Headlines (Noto Serif):** These are our "editorial" moments. Use `display-lg` for value propositions. The serif typeface conveys history, trust, and the "Atelier" feel.
*   **Body & Labels (Manrope):** A clean, geometric sans-serif that ensures medical information is legible and modern. 
*   **Hierarchy Note:** Always lead with Noto Serif for titles to establish authority, then transition to Manrope for supporting details to maintain a technical, clean edge.

---

## 4. Elevation & Depth: Tonal Layering
We avoid the "shadow-heavy" look of 2010s web design. Hierarchy is achieved through **Tonal Layering**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on top of a `surface-container-low` section. This creates a natural "lift" based on color value rather than artificial shadows.
*   **Ambient Shadows:** If a shadow is required for a floating "Book Appointment" button, use the `on-surface` color at 4% opacity with a `32px` blur and `8px` Y-offset. It should feel like a soft glow, not a dark smudge.
*   **The Ghost Border Fallback:** For form inputs where boundaries are critical for accessibility, use the `outline-variant` token at **15% opacity**. It should be barely perceptible.

---

## 5. Components

### Buttons
*   **Primary:** `primary` background, `on-primary` text. Large horizontal padding (2rem), `md` (0.75rem) rounded corners.
*   **Secondary:** `surface-container-high` background with `primary` text. No border.
*   **Tertiary (The "Gold" Accent):** For high-conversion links, use `on-tertiary-container` (#ad8a46) text with a `tertiary_fixed_dim` underline that grows on hover.

### Inputs & Fields
*   **Style:** `surface-container-lowest` background.
*   **Focus State:** Shift background to `surface` and add a subtle `tertiary` (Gold) bottom-border of 2px. This mimics a luxury stationery feel.

### Cards & Lists
*   **Forbid Dividers:** Use `1.5rem` of vertical whitespace to separate list items. 
*   **The Aligner Card:** Use `xl` (1.5rem) rounded corners for testimonial or product cards to mirror the organic, comfortable shape of dental aligners.

### Specialized Component: The "Consultation Float"
A persistent, glassmorphic floating action element using `surface` (80% alpha) and `primary` typography, anchored to the bottom right with a "soft-glow" ambient shadow.

---

## 6. Do’s and Don’ts

### Do:
*   **DO** use `tertiary` (Gold) sparingly. It is a "surgical" accent for highlights, icons, or small callouts.
*   **DO** lean into extreme asymmetry in the Hero section—overlap a `display-lg` serif headline over a high-quality photography mask.
*   **DO** use "Primary Fixed Dim" for subtle hover states on navy elements.

### Don't:
*   **DON'T** use pure black (#000000). Use `primary` or `on-surface` for all dark tones to maintain the navy-tinted sophistication.
*   **DON'T** use `none` or `sm` roundedness. The clinic is about comfort; use `md` as your minimum and `xl` for large containers.
*   **DON'T** use standard grid-gutters. Vary the spacing between elements to create a bespoke, non-templated rhythm.

---

## 7. Tokens Reference Summary

| Token | Value | Usage |
| :--- | :--- | :--- |
| **Primary** | `#00113a` | Brand authority, headers, primary buttons. |
| **Tertiary** | `#ad8a46` | Luxury accents, "Gold" standard highlights. |
| **Surface** | `#f8f9fa` | The main "canvas" of the experience. |
| **Roundness (xl)** | `1.5rem` | Major containers and product cards. |
| **Typography (H1)** | `Noto Serif` | Editorial authority. |
| **Typography (Body)**| `Manrope` | Technical precision. |

*This design system is a living document. Every pixel should feel like a deliberate choice in a high-end medical boutique.*```