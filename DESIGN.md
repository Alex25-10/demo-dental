# Design System Document: The Clinical Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Architectural Smile"**

This design system moves away from the sterile, cluttered "medical clinic" template and toward a high-end editorial experience. We treat the interface like a luxury lifestyle magazine: expansive, authoritative, and meticulously curated. 

The system leverages **intentional asymmetry** and **breathable whitespace** to mirror the precision of invisible aligner technology. By utilizing high-contrast typography scales and layered tonal depth, we establish a "Medical Luxury" aesthetic that feels more like an invitation to a private gallery than a visit to a doctor’s office. We break the grid with overlapping elements and "floating" components to create a sense of weightlessness and modern sophistication.

---

## 2. Colors & Surface Philosophy

### Color Tokens
- **Primary (Navy):** `#00113a` (The anchor of trust and authority)
- **Secondary (Muted Blue):** `#4c5f81` (For supporting interactive elements)
- **Tertiary (Gold Accent):** `#1d1200` / `#e9c176` (Used sparingly for "high-touch" moments)
- **Surface (Foundation):** `#f8f9fa` (The crisp, clean environment)

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. Boundaries must be defined solely through background color shifts. To separate a testimonial section from a service description, transition from `surface` to `surface-container-low`. This creates a seamless, "molded" look rather than a boxed-in feel.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the following logic for nesting:
1.  **Base Layer:** `surface` (The canvas)
2.  **Sectional Blocks:** `surface-container-low` (Subtle grouping)
3.  **Floating Cards:** `surface-container-lowest` (Pure white, perceived as "lifted")

### The "Glass & Gradient" Rule
To add "soul" to the navy primary, utilize subtle linear gradients (e.g., `primary` to `primary-container`). For high-end floating overlays (like booking modals), use **Glassmorphism**: `surface-container-lowest` at 80% opacity with a `24px` backdrop-blur.

---

## 3. Typography
The system uses a "High-Contrast Pairing" to balance clinical precision with luxury heritage.

| Level | Token | Font Family | Size | Character |
| :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Noto Serif | 3.5rem | Editorial, majestic, used for Hero statements. |
| **Headline** | `headline-md` | Noto Serif | 1.75rem | Authoritative but welcoming. |
| **Title** | `title-lg` | Manrope | 1.375rem | Modern, semi-bold, for feature headers. |
| **Body** | `body-lg` | Manrope | 1rem | Highly legible, generous line-height (1.6). |
| **Label** | `label-sm` | Manrope | 0.6875rem | All-caps with 0.1rem letter spacing for "Eyebrow" tags. |

**Editorial Tip:** Use `display-lg` in `primary` (Navy) for the first word of a header and `tertiary_fixed_dim` (Gold) for the second to create a signature focal point.

---

## 4. Elevation & Depth

### The Layering Principle
Hierarchy is achieved through **Tonal Layering**. Place a `surface-container-lowest` card on top of a `surface-container-low` background to create a soft, natural lift. This eliminates the need for aggressive shadows.

### Ambient Shadows
When a "floating" effect is mandatory (e.g., a primary CTA card), use an **Ambient Shadow**:
- **Color:** `#00113a` (Primary Navy) at 4% opacity.
- **Blur:** 40px to 60px.
- **Spread:** -10px (to keep it tight and sophisticated).

### The "Ghost Border" Fallback
If a border is required for accessibility in input fields, use the `outline-variant` token at **20% opacity**. Never use 100% opaque borders; they interrupt the "fluid" dental aesthetic.

---

## 5. Components

### Buttons: The Precision Interaction
- **Primary:** `primary` background with `on-primary` (White) text. Use `xl` (0.75rem) corner radius. Height: 56px for a premium feel.
- **Secondary:** Transparent background with a `tertiary_fixed_dim` (Gold) ghost border (20% opacity).
- **Tertiary/Link:** `primary` text with a 1px underline that only spans 50% of the text width, centered.

### Input Fields: The "Quiet" Field
Forgo the "box" look. Use a `surface-container-low` background with no border, and a bottom-only `outline` (1px at 10% opacity) that animates to 100% opacity `primary` on focus.

### Cards: The Gallery Block
- **Rule:** No dividers. Use 48px or 64px padding (Spacers) to separate content.
- **Composition:** Use an image that "breaks" the card boundary, slightly overlapping the edge to create an asymmetric, high-fashion layout.

### Specialized Component: The "Confidence Slider"
A custom comparison tool for "Before/After" results. The handle should be a minimal gold line (`tertiary_fixed_dim`) with a small, circular `surface-container-lowest` grip featuring a subtle ambient shadow.

---

## 6. Do’s and Don’ts

### Do:
- **Do** use "Over-sized" margins. If you think there is enough whitespace, add 20% more.
- **Do** use Noto Serif for numbers (e.g., "01", "02" in a process list) to make them look like architectural annotations.
- **Do** utilize `surface-bright` for the main background to ensure the "Medical Clean" feel is maintained.

### Don't:
- **Don't** use pure black `#000000`. Use `primary` or `on-surface` for all text.
- **Don't** use standard "Success Green." For positive medical confirmations, use a muted version of the Navy or a sophisticated Gold checkmark.
- **Don't** use sharp corners. Always use the `DEFAULT` (0.25rem) or `lg` (0.5rem) roundedness to keep the UI feeling "organic" and human.
- **Don't** use divider lines. If the content needs separation, use a background shift to `surface-container-low`.