# CLAUDE.md

Guidance for Claude Code when working in this repo. This is a **Slidev presentation deck**.

## What this is

A web-based slide deck authored in Markdown with [Slidev](https://sli.dev). Slides live
in `slides.md`, separated by `---`. The dev server hot-reloads on save.

- Package manager: **pnpm** (`pnpm-lock.yaml` is the source of truth — don't use npm/yarn)
- Slidev CLI: `@slidev/cli` v52
- Theme: **seriph** (set in the headmatter at the top of `slides.md`)

## Commands

```bash
pnpm dev      # slidev --open — live dev server, hot-reloads slides.md
pnpm build    # slidev build → dist/, then strips dist/_redirects (see Deploy)
pnpm export   # slidev export — PDF/PNG export
```

## Deploy

Live at **https://talk.isaiahkeepin.com**. Hosted on **Cloudflare Workers Static
Assets** (not classic Pages), wired to the GitHub repo `irkeepin/are-we-there-yet`.

- **Workflow:** `git push origin main` → Cloudflare runs `pnpm run build` →
  `npx wrangler deploy` uploads `dist/`. No GitHub Actions; Cloudflare builds from
  the repo. There is nothing to deploy by hand.
- **Config:** `wrangler.jsonc` points `wrangler deploy` at `./dist` and sets
  `not_found_handling: "single-page-application"` — that's what makes deep links
  (e.g. `/5`, refresh mid-deck) resolve to the SPA instead of 404ing.
- **Custom domain:** `talk.isaiahkeepin.com` is a subdomain (not a subpath of the
  apex) attached in the Worker's *Settings → Domains & Routes*. The apex
  `isaiahkeepin.com` is a separate Cloudflare project — don't touch it.

> ⚠️ **`_redirects` landmine.** Slidev's `build` emits a `dist/_redirects` with a
> `/* /index.html 200` catch-all. Workers Static Assets rejects it as a redirect
> loop and the deploy fails. The `build` script therefore ends with
> `rm -f dist/_redirects`; SPA fallback is handled by `wrangler.jsonc` instead.
> **Don't re-add `_redirects`** (or a `public/_redirects`) — it will break deploys.

## Where things live

- `slides.md` — the deck. Headmatter (theme, title, transition) is the first `---` block;
  each subsequent `---` starts a new slide, and a slide's own frontmatter goes right after it.
- `dist/` — build output. Generated; don't hand-edit.
- `TEMPLATE.md` — this repo is a reusable scaffold; the bootstrap checklist for
  spinning up a new deck lives there. Frozen at git tag `template-v1`.
- `docs/syntax-reference.md` — copy-paste Slidev syntax cheatsheet, kept out of
  `slides.md` so the deck stays strong-SDD.
- `.claude/skills/slidev/` — the Slidev authoring skill, **vendored and committed**. It's
  pinned via `skills-lock.json` (installed with `npx skills add slidevjs/slidev`) and refreshed
  by `npx skills update`. Treat as a reference layer; don't hand-edit — direct edits can be
  overwritten on update, and preferences belong in the section below instead.

## The `slidev` skill

When building or editing slides, use the `slidev` skill — it has the Slidev syntax, layout,
animation, and code-highlighting reference. My preferences below take precedence over the
skill's defaults when they conflict.

## My deck preferences

<!-- This section is the point of the file: it grows as Isaiah refines his style over decks.
     Keep it concrete. When a preference becomes a repeatable procedure, promote it to a
     separate personal skill instead of bloating this file. -->

- **Theme:** seriph for now. Flag before swapping themes — it restyles the whole deck.
- **Aspect ratio / canvas:** Slidev default (16:9). Change in headmatter if needed.
- **Code slides:** prefer TypeScript examples; use line-highlighting (`{1|2-3|all}`) to
  reveal code in steps rather than dumping a full block.
- **Animations:** reach for `v-click` to pace reveals; don't over-animate.
- **Speaker notes:** put them in the `<!-- -->` block at the end of each slide.

<!-- Add as you go, e.g.:
- Brand palette: <hex values>
- Title-slide convention: <how you like openers>
- Fonts: <family + where set>
-->

## Context & spec (spec-driven authoring)

This deck is authored **spec-first (strong SDD)**. `slides.md` is a *generated
artifact* — never the source of truth for content or copy.

- `context/` — **world context**: background/source material on the topic. Read the
  relevant file **before** writing slide copy or making a factual claim, and cite
  it. Index in `context/README.md`. Don't edit unless asked.
- `deck/brief.md` — **the spec**: audience, goal, core message, constraints, and
  **Voice & tone**. Read it at the start of any authoring session.
- `deck/outline.md` — the **authoritative** narrative arc *and* Isaiah's authored
  copy (headlines + key lines) in his voice. This is the source of truth for what
  the deck says. Slides render it; they don't originate content.
- `deck/decisions.md` — append-only, dated ADR log. Append when a content /
  structure / voice decision is made or changed.
- `deck/open-questions.md` — unresolved threads.

**Strong-SDD drift rule — edit the spec, not the artifact.** Change content by
editing `outline.md` (and `brief.md`), then regenerate the affected slides. If
`slides.md` is ever hand-edited for content/copy, immediately reconcile: fold the
change back into `outline.md` and log it in `decisions.md`, or revert it as
off-spec. Purely visual/layout tuning may live only in `slides.md` — but anything
that changes *what is said* belongs in the spec first. **Preserve Isaiah's
authored lines verbatim; don't paraphrase them during regeneration.**

> Personal working style and durable cross-session facts live in the memory store
> (`MEMORY.md`), not here. Deck content lives in `deck/`. This file is committed,
> team-facing guidance.

## Conventions

- **Spec-first:** edit `deck/outline.md` / `deck/brief.md`, then regenerate slides —
  don't originate content in `slides.md` (see the drift rule above). Verify visually
  via `pnpm dev` rather than trusting the diff alone.
- Don't commit `dist/` changes unless deploying (check `.gitignore`).
