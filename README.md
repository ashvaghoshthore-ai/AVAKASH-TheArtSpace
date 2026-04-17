# Design System: The Sculpted Stage

## 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Sculpture"**

This design system is not a mere repository of components; it is a digital stage where the ancient geometry of Bharatanatyam meets contemporary high-end minimalism. We view the interface as a living sculpture—shifting, breathing, and defined by the tension between sharp precision and fluid grace. 

To break the "template" look, we move away from rigid, symmetrical grids. Instead, we embrace **intentional asymmetry** and **tonal depth**. Elements should feel as though they are carved from stone or cast in frosted glass, layered in a way that mimics the depth of a physical stage. The UI must feel curated, high-end, and intentionally quiet, allowing the abstract silhouettes and sophisticated typography to command the viewer’s attention.

---

## 2. Colors & Surface Philosophy
The palette is rooted in an earthy, sophisticated "Dark Olive" and "Obsidian" foundation. It evokes the atmosphere of a dimly lit theater before a performance.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid borders for sectioning. Boundaries must never be structural "lines." Instead, define space through:
*   **Tonal Transitions:** Transitioning from `surface` to `surface_container_low`.
*   **Negative Space:** Using generous padding to allow content to breathe.
*   **Shadow Play:** Using subtle depth to imply a break in the plane.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to create "nested" depth:
*   **Base Layer:** `surface` (#131313) for the primary background.
*   **Recessed Areas:** Use `surface_container_lowest` (#0e0e0e) for "wells" or background sections that should feel further away.
*   **Elevated Elements:** Use `surface_container_high` (#2a2a2a) for primary cards or floating panels.

### The "Glass & Gradient" Rule
To achieve a premium 3D feel, employ **Glassmorphism**. For floating navigation or modal overlays, use `surface_variant` at 60% opacity with a `backdrop-filter: blur(20px)`. 
*   **Signature Textures:** Apply a subtle radial gradient on Hero sections, transitioning from `primary_container` (#5e6930) at the focal point to `background` (#131313) at the edges. This mimics stage lighting.

---

## 3. Typography: The Editorial Voice
We pair the structural precision of **Inter** with the lyrical, high-contrast elegance of **Newsreader**.

*   **Display & Headlines (Inter):** Used for "The Sculpted" part of our identity—strong, modern, and unapologetically bold. Use `display-lg` for hero statements with tight letter-spacing (-0.02em) to feel architectural.
*   **Body & Accents (Newsreader):** Used for "The Stage"—human, sophisticated, and fluid. The use of serif for `body-lg` creates a high-end editorial feel, making the academy’s philosophy feel like a literary work.
*   **Labeling (Inter):** All functional UI (buttons, labels, inputs) stays in Inter to ensure modern utility and clarity.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too heavy for this aesthetic. We achieve lift through "Tonal Layering."

*   **The Layering Principle:** Place a `surface_container_highest` card on top of a `surface_dim` background to create a soft, natural lift.
*   **Ambient Shadows:** If a shadow is required for a floating CTA, use the `on_surface` color at 6% opacity with a 40px blur and 10px Y-offset. It should feel like a soft glow of light blocked by an object, not a black smudge.
*   **The "Ghost Border" Fallback:** If a container lacks sufficient contrast, use a "Ghost Border": `outline_variant` (#45483c) at **15% opacity**.
*   **3D Silhouettes:** Abstract mudra illustrations should utilize `primary` and `secondary_fixed_dim` tones, layered behind text with varying opacities to create a sense of three-dimensional space within the scroll.

---

## 5. Components

### Buttons
*   **Primary:** Background `primary` (#c1cd89), Text `on_primary`. No border. Corner radius: `sm` (0.125rem) for a sharp, chiseled look.
*   **Secondary (Glass):** `surface_variant` at 40% opacity, backdrop blur 12px, Ghost Border.
*   **Tertiary:** Text-only in `primary_fixed`, featuring a subtle `on_primary_container` underline that expands on hover.

### Cards & Lists
*   **Forbid Divider Lines.** Separate list items using a height increase (e.g., `1.5rem` of vertical space) or a subtle background shift to `surface_container_low` on hover.
*   **Cards:** Use `surface_container_high`. Ensure the corner radius is consistent (`md`). Imagery within cards should be abstract line art or 3D mudra forms, never photography.

### Input Fields
*   **Style:** Minimalist underline style or "Soft Well" (`surface_container_lowest`). 
*   **States:** On focus, the underline or subtle background should transition to `primary` with a smooth 300ms ease-in-out.
*   **Error:** Use `error` (#ffb4ab) sparingly.

### Interactive "Mudras" (Custom Component)
*   Instead of standard icons, use abstract 3D geometric forms that subtly animate (rotate/scale) when the user interacts with the section. These serve as visual anchors for "The Sculpted Stage."

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Let a headline sit on the left while the abstract 3D form sits slightly off-center to the right.
*   **Do** use Newsreader for pull-quotes and philosophical statements to heighten the "Academy" feel.
*   **Do** ensure all transitions are "Weighted." Use `cubic-bezier(0.4, 0, 0.2, 1)` for all movements to mimic the controlled power of a dancer.

### Don't
*   **Don't** use 100% white (#FFFFFF). Use `on_surface` (#e5e2e1) for text to maintain the moody, high-end atmosphere.
*   **Don't** use stock photography. If an image is needed, it must be post-processed into a high-contrast silhouette or an abstract 3D rendering.
*   **Don't** use "Rounded" buttons. Keep corner radii to `sm` or `none` to maintain the "Sculpted" architectural edge.
*   **Don't** use standard "Drop Shadows." If it looks like a default Photoshop shadow, it's wrong. Think "Ambient Occlusion."