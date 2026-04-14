# ThemeDemo---EduViet

```markdown
# Design System Specification: The Kinetic Academic

## 1. Overview & Creative North Star
**Creative North Star: "The Illuminating Path"**
To move beyond the generic "e-learning dashboard" aesthetic, this design system adopts a philosophy of **The Illuminating Path**. We reject the rigid, boxy constraints of traditional LMS platforms in favor of an editorial, fluid experience. The "Path" is characterized by intentional asymmetry, sweeping white space, and high-contrast typography that guides the student’s eye like a premium magazine. 

We break the "template" look by layering vibrant pops of `secondary_container` (Sunny Yellow) over deep, professional `primary` (Electric Blue) foundations. Our layouts should feel energetic yet organized, using "breathing room" as a functional tool to reduce cognitive load and spark motivation.

---

## 2. Colors & Surface Architecture

### Tonal Hierarchy
We move away from flat design by utilizing the Material 3 tonal palette to create a sense of environmental depth.

- **Primary (`#0037b0`) & Primary Container (`#1d4ed8`):** Our "Electric Blue" drives the professional core. Use the `primary_container` for hero sections to establish authority.
- **Secondary (`#795900`) & Secondary Container (`#ffc329`):** Our "Sunny Yellow" acts as the kinetic energy. It is reserved for high-impact moments: CTAs, progress indicators, and "aha!" moments.

### The "No-Line" Rule
**Borders are prohibited for sectioning.** To define boundaries, we use background shifts. 
- A lesson card (`surface_container_lowest`) sits on a workspace background (`surface_container_low`). 
- A sidebar (`surface_container`) is distinguished from the main feed (`surface`) purely through color elevation.

### Surface Hierarchy & Nesting
Treat the interface as a series of stacked, premium papers.
*   **Level 0 (Base):** `surface` (#faf8ff) - The canvas.
*   **Level 1 (Sections):** `surface_container_low` (#f3f2fe) - Large content areas.
*   **Level 2 (Cards/Modules):** `surface_container_lowest` (#ffffff) - High-focus interactive elements.
*   **Level 3 (Pop-overs):** `surface_bright` (#faf8ff) - Floating elements with ambient shadows.

### The "Glass & Gradient" Rule
To add "soul," use a **Linear Gradient** on primary CTAs: `primary_container` to `primary`. For floating navigation or video overlays, apply **Glassmorphism**: `surface` at 70% opacity with a `24px` backdrop blur.

---

## 3. Typography: Editorial Authority
We use **Plus Jakarta Sans** to balance friendliness with digital marketing precision.

| Token | Size | Weight | Use Case |
| :--- | :--- | :--- | :--- |
| `display-lg` | 3.5rem | 800 | Hero headlines, "Impact" numbers |
| `headline-md` | 1.75rem | 700 | Module titles, Section headers |
| `title-lg` | 1.375rem | 600 | Card titles, Navigation items |
| `body-lg` | 1rem | 400 | Primary course content, Lesson text |
| `label-md` | 0.75rem | 500 | Metadata, Tags, Micro-copy |

**Editorial Contrast:** Pair a `display-lg` headline in `on_surface` with a `title-md` sub-headline in `primary`. The scale jump should feel intentional and bold.

---

## 4. Elevation & Depth

### The Layering Principle
Avoid "Floating Box Syndrome." Instead of adding a shadow to every card, use **Tonal Layering**. Place a `surface_container_highest` element behind a `surface_container_lowest` element to create natural, soft-touch separation.

### Ambient Shadows
Where physical lift is required (e.g., a floating "Ask Mentor" button), use **Ambient Shadows**:
- **X: 0, Y: 8, Blur: 32, Spread: 0**
- **Color:** `on_surface` at **6% opacity**. 
*Note: Never use pure black shadows. The shadow should feel like a soft glow of the background color.*

### The "Ghost Border" Fallback
If accessibility requires a container edge (e.g., in high-glare environments), use a **Ghost Border**: `outline_variant` at **15% opacity**.

---

## 5. Components

### Buttons: The Kinetic Trigger
- **Primary:** `primary_container` background, `on_primary` text. Radius: `full`. No border.
- **Secondary:** `secondary_container` background, `on_secondary_container` text. Radius: `full`.
- **States:** On hover, apply a `surface_tint` overlay at 8% to create a subtle "glow" effect.

### Input Fields: The Clean Slate
- **Style:** `surface_container_low` background with no border. 
- **Active State:** A `2px` "Ghost Border" of `primary` becomes visible. 
- **Corners:** `sm` (0.5rem) to maintain a modern, crisp feel.

### Cards & Lists: The No-Divider Rule
**Dividers are forbidden.** 
- Separate list items using `1.5rem` (md) vertical spacing. 
- Group content using subtle background blocks of `surface_container` instead of lines. This keeps the interface "bright and clean."

### Specialized Learning Components
- **Progress Orbital:** A circular progress bar using `secondary` (Sunny Yellow) against a `secondary_fixed` track. 
- **Focus Mode Card:** A large-scale card using `xl` (3rem) roundedness to create a "cocoon" effect for concentrated reading.

---

## 6. Do’s and Don’ts

### Do:
- **Use Intentional Asymmetry:** Align text to the left but place supporting imagery or stats slightly offset to the right to create visual "energy."
- **Embrace White Space:** If a section feels crowded, double the padding. "Modern" is defined by the space you *don't* fill.
- **Color Coding:** Use `tertiary` (Burnt Orange/Red) exclusively for urgent notifications or error states to keep the palette professional.

### Don't:
- **No 1px Lines:** Never use a solid 100% opaque line to separate content. Use space or tonal shifts.
- **No Sharp Corners:** Avoid the `none` roundedness scale. Even buttons should have at least `sm` rounding to feel "accessible."
- **No Pure Grey:** Always use the tinted neutrals (`surface_variant`, `outline`) to keep the "Electric Blue" vibe consistent throughout the UI.
