# Slidev syntax reference

A copy-paste cheatsheet of common Slidev patterns, kept **out of `slides.md`** so
the deck stays strong-SDD (every slide traces to `deck/outline.md`). Reach for the
`slidev` skill for the full reference; this file is the quick showcase.

> This was the template's original demo deck. It lives here as reference, not as
> deck content. When authoring a real deck, generate `slides.md` from
> `deck/outline.md` instead of pasting these in wholesale.

## Headmatter (first `---` block of `slides.md`)

```yaml
---
theme: seriph
title: <Deck title>
info: <One-line description>
class: text-center
transition: slide-left
mdc: true
---
```

## Title slide

```md
# <Deck title>

<Subtitle>

<div class="pt-12">
  <span class="px-2 py-1 rounded bg-white bg-opacity-10">
    Press <kbd>space</kbd> to begin <carbon:arrow-right class="inline"/>
  </span>
</div>

<!--
Presenter notes go here. Only you see these in presenter mode.
-->
```

## Bulleted content + per-slide transition

```md
---
transition: fade-out
---

# What's in the box

- 📝 **Markdown** — write slides in plain Markdown, separated by `---`
- 🎨 **Themes** — swap in the headmatter above
- 💻 **Code** — syntax-highlighted blocks with line highlighting & animation
- 🎬 **Animations** — reveal content with `v-click`
- 🧩 **Vue components** — drop interactive components right into slides
```

## Code with stepped line-highlighting

Prefer TypeScript examples; reveal lines in steps rather than dumping a block.

````md
# Code, highlighted

```ts {all|2|4-6|all}
function greet(name: string): string {
  const greeting = `Hello, ${name}!`

  return greeting
    .toUpperCase()
    .padEnd(20, '.')
}
```

<v-click>

Use `{1|2-3|all}` after the language to reveal lines on each click.

</v-click>
````

## Two-column layout

```md
---
layout: two-cols
---

# Left

- Content before `::right::` goes here

::right::

# Right

- Content after `::right::` lands here
- Great for compare/contrast
```

## Centered closing slide

```md
---
layout: center
class: text-center
---

# The end

[Slidev docs](https://sli.dev) · [Themes](https://sli.dev/resources/theme-gallery)
```
