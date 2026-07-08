# Using this template

This repo is a **reusable scaffold** for spec-driven Slidev decks. It's frozen at
tag `template-v1`. Each real deck is its own independent repo — don't author decks
on branches here.

## Spin up a new deck

```bash
cp -R slidev-deck-one my-new-deck        # decoupled copy, fresh start
cd my-new-deck
rm -rf .git && git init && git add -A && git commit -m "Init from template-v1"
git remote add template /path/to/slidev-deck-one   # for backporting later
pnpm install
```

`cp` (not fork/branch) is deliberate: each deck evolves independently and should
share nothing with the template except the occasional cherry-picked improvement.

## Bootstrap checklist (new deck)

- [ ] `package.json` → set `name` to the deck's slug.
- [ ] `deck/brief.md` → fill in audience, goal, core message, **Voice & tone**,
      constraints, non-goals. Replace every placeholder.
- [ ] `deck/outline.md` → replace the sample node with the real narrative arc;
      this is the authoritative source of copy.
- [ ] `context/` → drop in source material; index it in `context/README.md`.
- [ ] `deck/decisions.md` → start a fresh dated ADR for this deck (keep the
      inherited "Adopt strong SDD" decision, or supersede it).
- [ ] `deck/open-questions.md` → clear to empty.
- [ ] `slides.md` → set `title`; generate slides from `outline.md` (don't hand-author).
- [ ] Verify with `pnpm dev`.

## Heads-up: memory doesn't travel

The Claude memory store is keyed by project *path*, so a copied deck starts with an
**empty** memory. Template-level conventions that every deck must inherit live in
`CLAUDE.md` and `deck/` (which do travel), not in memory.

## Backporting improvements to the template

Make the improvement while working in a deck, then from the template repo:

```bash
git fetch <that-deck-repo> && git cherry-pick <sha>
```

`cherry-pick` applies by patch, so it works across the unrelated histories. Bump the
tag (`template-v2`, …) when the baseline meaningfully changes.
