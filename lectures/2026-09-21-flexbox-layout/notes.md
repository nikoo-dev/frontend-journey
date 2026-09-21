# Lecture — Flexbox Layout (2026-09-21)

## Recap of week 1

Confirmed solid on: HTML boilerplate, headings/paragraphs, links/images,
lists, `div`, class/id, semantic tags, forms — and CSS basics: selectors,
colors, fonts, width, box model properties, `box-sizing: border-box`.

## Why Flexbox?

By default, block elements stack vertically. Flexbox is the CSS layout system
for arranging elements horizontally, centering them, distributing space
between them, and aligning them on both axes — needed constantly for real
layouts (navbars, card rows, centering things on a page).

## Parent/child + display: flex

```html
<div class="container">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="box">3</div>
</div>
```

`display: flex` goes on the **parent** (`.container`) to arrange its
**children** (`.box`) — a common mistake is putting `display: flex` on the
child itself, which only affects that element's own inner content, not its
siblings.

```css
.container {
    display: flex;
    gap: 20px; /* spacing between children — cleaner than per-child margins */
}
```

## justify-content (main axis)

Controls alignment along the main axis: `flex-start`, `center`, `flex-end`,
`space-between`, `space-around`, `space-evenly`.

## align-items (cross axis)

Controls alignment on the perpendicular axis, e.g.:

```css
.container {
    height: 300px;
    display: flex;
    align-items: center;
}
```

Combined, `justify-content: center` + `align-items: center` on a full-height
container is the standard way to center something on the page:

```css
.page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
```

## flex-direction

Default is `row` (horizontal). `flex-direction: column` stacks children
vertically instead, which also flips which axis is "main" vs "cross".

## Practice

- Centered card on a full-height page
- Three course cards laid out in a row with `justify-content: center` + `gap`
- A navbar using `justify-content: space-between` to push the logo and nav
  links to opposite ends
- A form row (First Name / Last Name side by side) using `display: flex` on
  a wrapper div

## Homework — Sign Up Page

Header + short text + Registration Form (First Name + Last Name side by side
via Flexbox, Email, Password, Country, Terms checkbox, Submit button).
Requirements: `box-sizing: border-box`, width, padding, margin, border,
border-radius, `display: flex`, `gap`, `justify-content`, `align-items`.
