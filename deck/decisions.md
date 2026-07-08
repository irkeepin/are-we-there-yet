# Decisions — append-only log (ADRs)

Dated record of content, structure, and voice decisions and *why*. Newest at the
bottom. When a decision changes, **don't delete** the old entry — add a new one
that supersedes it and note which it replaces.

Format:

```
### YYYY-MM-DD · <short title>
- **Decision:**
- **Why:**
- **Affects:** <outline IDs / brief section>
- **Supersedes:** <prior entry, or —>
```

---

### 2026-07-07 · Adopt strong spec-driven authoring

- **Decision:** Author this deck spec-first. `deck/outline.md` is authoritative;
  `slides.md` is a generated artifact. Isaiah's voice is captured *in the spec* —
  the brief's Voice & tone section plus authored copy in the outline — so
  regenerating slides preserves it.
- **Why:** Isaiah wants a reliable home for his copywriting voice and a single
  authoritative outline, and is using this project to test SDD concepts.
- **Affects:** whole repo; CLAUDE.md routing block.
- **Supersedes:** —
