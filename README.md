# ihumenyuk.github.io

Landing page for Iryna Humenyuk — selected data journalism, reporting and editorial work.

A single static page, no framework and no build step. The layout is a horizontally
scrolling editorial spread: narrow justified columns, caption-style headers, images hung
at varying heights.

## Structure

```
index.html        the whole site — markup, CSS and ~30 lines of JS
images/           project images, resized to max 1000px
```

## Editing

Each project is one `<section class="col">`. To add one, copy an existing section and
drop it in place. The pieces of a column:

- `<h2>` — the header, set in uppercase automatically
- `<p class="lede">` — optional opening line, slightly heavier
- `<p>` — body copy, justified with automatic hyphenation
- `<figure>` — optional image with `<figcaption>`
- `<p class="meta">` — the footer line; hangs at the bottom of the column

Images are hung at different heights with `drop-1` through `drop-5` on the `<figure>`
(roughly 18px to 300px of top margin). `narrow` and `half` reduce image width. Vary
these deliberately — the staggering is what makes it read as a spread rather than a grid.

`<div class="gutter">` draws the faint vertical rule that divides the spread into
"pages". Move or add them freely.

## Images

Add to `images/` and resize before committing:

```bash
sips -Z 1000 images/your-file.jpg
```

Always set `width`, `height` and `alt` on the `<img>` — the dimensions prevent layout
shift while loading, and the alt text is what a screen reader and a search engine read.

## Local preview

```bash
cd ihumenyuk.github.io && python3 -m http.server 4173
```

Then open http://localhost:4173.

## Notes

- Horizontal scrolling works natively on trackpads and touch; the small script maps a
  mouse wheel's vertical axis onto horizontal scroll and adds arrow / Home / End keys.
- Below 760px the columns widen to 74vw and scroll-snap engages, so it reads as a
  swipeable card stack on a phone.
- Published pieces link out to their original publishers rather than being reproduced.
