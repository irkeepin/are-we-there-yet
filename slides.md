---
theme: seriph
title: Are We There Yet?
info: Insights on AI software productivity from 2026 DX Annual — a ChatBTV talk.
colorSchema: dark
transition: fade
mdc: true
fonts:
  sans: Archivo
  weights: '400,600,900'
  provider: google
layout: center
class: text-center
---

<!--
GENERATED ARTIFACT. Content authored in deck/outline.md (Isaiah's voice) against
the spec in deck/brief.md, then rendered here. Do not originate copy in this file
— see the strong-SDD drift rule in CLAUDE.md. Syntax: docs/syntax-reference.md

Transition scheme (deck/brief.md → Animations): every slide opens on its own
full-bleed photo (<PhotoBg>) with NO text at all. The first click fades the photo
(via :dimmed="$clicks > 0") and reveals only the slide title (title wrapped in its
own v-click). Every click after that proceeds normally: content lines reveal one
per click from click 2 onward, sub-lines reveal together with their parent
(v-clicks at default depth). "Reveal all at once" nodes reveal their whole body on
the click after the title. Title/author slides carry title + subtitle in one
v-click, so click 1 brings the whole block. Between slides, the deck-wide `fade`
transition gives the slideshow feel.
-->

<PhotoBg src="/images/PXL_20260627_104251542.png" :dimmed="$clicks > 0" />

<div v-click class="relative z-10">

# Are We There Yet?

Insights on AI software productivity from [2026 DX Annual](https://getdx.com/dxannual/)

</div>

<style>
h1 { color: #fcd34d; font-size: 4rem; }
</style>

<!--
arc-01 · Title slide. Reveal: all at once.
-->

---
layout: center
class: text-center
---

<PhotoBg src="/images/PXL_20260702_174043807.png" :dimmed="$clicks > 0" />

<div v-click class="relative z-10">

# Isaiah Keepin

<div class="text-xl leading-relaxed mt-4">

AVP Engineering, Sun Life

Ex Bluehouse Group

isaiah@isaiahkeepin.com

</div>

</div>

<style>
h1 { color: #5eead4; }
</style>

<!--
arc-02 · Author slide. Reveal: all at once.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260704_230327817.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# The Elephant in the Room

</div>

<v-clicks>

- What's the reality beneath the hype?
- Anecdotes are amazing, we've all seen them. At the same time —
  - Are companies overall seeing speed go up? Productivity go up?
  - How would we measure that anyway?
- And assuming that overall acceleration is possible —
  - How do we get more of it?
  - And do it safely?
  - And help the humans adjust?

</v-clicks>

</div>

<style>
h1 { color: #fda4af; }
</style>

<!--
arc-03 · Introduction — the main idea.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260705_140855514.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# DX Annual 2026

</div>

<v-clicks>

- SF, April 2026
- DX is a research company
- Brought together leaders & thinkers across many companies
- e.g. Microsoft, Google, Netflix, Airbnb, Mercari, Dell
- Excellent cross-sectional view of the issues at play
- Dev productivity leaders: neither kool-aid nor pitchforks

</v-clicks>

</div>

<style>
h1 { color: #7dd3fc; }
</style>

<!--
arc-04 · The conference — the main source.

Verbal close (kept off-slide per "move wordy content to speaker notes"):
My intent is to help you decide if you want to go deeper with any of the
talks posted online.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260701_162750105.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# Measuring Speed & Value

</div>

<v-clicks>

- Fundamentally, everyone wants to measure this and prove the value, and nobody really knows how
- All models are false but some are useful
- DX — Org-level PR throughput
- Uber — Whatever metric you choose will change as you mature

</v-clicks>

</div>

<style>
h1 { color: #bef264; }
</style>

<!--
arc-05 · Measurement.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260701_160313578.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# AI Platform Engineering

</div>

<v-clicks>

- Airbnb — Control plane as product
- Mercari — Nested autonomous loops
- Netflix — Default agents with company context built in
  - Low friction
  - Good defaults with opt-out
  - Eval set for knowledge base
- **Note for smaller orgs** — lightweight versions of these things are possible and worthwhile, especially in context management

</v-clicks>

</div>

<style>
h1 { color: #c4b5fd; }
</style>

<!--
arc-06 · Platform.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260701_162730380.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# Which Tasks to Delegate?

</div>

<v-clicks>

- Atlassian — Remove toil & let more people help
- 1Password — More humans in front and in back of SDLC
- Microsoft — Humans plan and validate
  - Agents create, deploy, and operate
  - Except in security — not ready

</v-clicks>

</div>

<style>
h1 { color: #fdba74; }
</style>

<!--
arc-07 · Delegation.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260627_190159817.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# Oh the Humans

</div>

<v-clicks>

- Dell — Tell a story where people can see themselves
- Github — The identity crisis is real
- Netflix — Differentiate training & message according to audience
  - For example, power users want lots of custom options, but regular folks want a few vetted choices
- Twilio — No need for top down mandates — the industry is doing it anyway

</v-clicks>

</div>

<style>
h1 { color: #f9a8d4; }
</style>

<!--
arc-08 · Managing humans.
-->

---
layout: center
class: text-center
---

<PhotoBg src="/images/PXL_20260701_181756363.png" :dimmed="$clicks > 0" />

<div class="relative z-10">

<div v-click>

# Prediction is Difficult<br>Especially About the Future

</div>

<div class="text-left inline-block mt-4">

<v-clicks>

- Visible timescale is 6–12 months
- Anything 18–24 is fooling yourself
- But the skill to adjust now will be the skill to adjust later
- Practices around the tools will change more slowly than the tools themselves (especially context management)

</v-clicks>

</div>

</div>

<style>
h1 { color: #67e8f9; }
</style>

<!--
arc-09 · Looking forward.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260705_202329156.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# What's Happening in Burlington?

</div>

<div v-click>

- How are we measuring AI efficiency gains?
- What are we doing to centralize AI resources, especially context?
- How are we deciding which tasks to offload to AI?
- What stories are we telling of an AI future where people can see themselves thriving?

</div>

</div>

<style>
h1 { color: #6ee7b7; }
</style>

<!--
arc-10 · Discussion — seed questions for the room. Reveal: all at once.
-->

---
layout: center
---

<PhotoBg src="/images/PXL_20260701_184225732.png" :dimmed="$clicks > 0" />

<div class="relative z-10 text-left max-w-4xl">

<div v-click>

# Speaker Attribution

</div>

<div v-click class="text-lg columns-2 gap-12">

- 1Password — Nancy Wang
- Airbnb — Madison Capps & Christopher Sanson
- Atlassian — Tarun Mandhana
- DX — Abi Noda
- Mercari — Michael Galloway
- Microsoft — Tim Bozarth
- Netflix — Stewart Reichling
- Twilio — Jesse Adametz
- Uber — Abhishek Tibrewal

</div>

</div>

<style>
h1 { color: #e2e8f0; }
</style>

<!--
arc-11 · Appendix: Attribution. Reveal: all at once.
-->
