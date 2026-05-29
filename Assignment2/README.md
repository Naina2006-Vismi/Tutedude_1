# Assignment 2 - Laundry Mart Hero Section

This project is a clean, responsive landing page for **Laundry Mart**, designed to demonstrate practical CSS layout skills. It focuses on the use of **Flexbox**, **Viewport Units**, and **Media Queries** to build a fluid, responsive user experience.

---

## 1. Flexbox Layout & Alignment

Flexbox (Flexible Box Layout) was chosen as the primary layout tool because it allows simple alignment of items along a single axis, automatically adjusting space distribution.

### Navbar Alignments:
* `display: flex` turns the `.navbar` container into a flex context.
* `justify-content: space-between` pushes the Logo to the left, Nav Links to the center, and the User Badge to the right.
* `align-items: center` centers all three elements vertically.
* `list-style: none` and `display: flex` on `.nav-links` aligns list items horizontally, with a `gap: 20px` to maintain clean spacing.

### Hero Section Alignments:
* `display: flex` places the text column (`.hero-left`) and the image column (`.hero-right`) side-by-side.
* `justify-content: space-around` distributes empty space around the two columns.
* `align-items: center` ensures the text block and image align vertically on the same centerline.

---

## 2. Why Viewport Units?

The problem description requires that the hero section fits completely on one screen without vertical scrolling on desktop. 

* We used `height: 90vh` for the `.hero` section.
* **vh (Viewport Height)** is a unit representing 1% of the viewable browser window height. Setting it to `90vh` leaves exactly 10% for the navbar and margins, ensuring the entire block fits neatly on the desktop screen without requiring scroll bars.

---

## 3. Responsive Design & Media Queries

While a fixed viewport height (`90vh`) works perfectly on desktop, it introduces layout bugs on smaller viewports (e.g., mobile phones) where screens are narrow.

### The Mobile Overflow Challenge:
1. On narrow screens, the headings and text paragraphs wrap onto multiple lines.
2. In a vertical stack (`flex-direction: column`), the content's total height exceeds `90vh`.
3. If we leave `height: 90vh` active on mobile, the text overflows, overlapping other elements or getting cut off.

### The Solution:
* We set up a media query breakpoint at `@media(max-width: 768px)`.
* We changed `flex-direction` to `column` for both the `.navbar` and `.hero` sections to stack components vertically.
* **Crucially**, we overrode the hero height to `height: auto` on mobile. This tells the browser to size the container based on its children, accommodating the wrapped text and image naturally, preventing overlap or cutoffs.
* We also reduced the heading font size from `50px` to `32px` for a proportional mobile scale.

---

## 4. Iterative Testing & Development

We built the layout incrementally to prevent errors:
1. **Reset & Basics**: Configured `box-sizing: border-box` first to prevent padding from expanding layout dimensions.
2. **Navbar**: Styled the Logo first, added navigation links, and then the User Badge, checking that flex row alignment centered them at each step.
3. **Hero Content**: Positioned text columns and scaled the image.
4. **Responsive Testing**: Resized the viewport in Chrome DevTools to locate visual breakpoints and adjusted mobile properties accordingly.
