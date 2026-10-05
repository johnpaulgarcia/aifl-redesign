# AIFL Redesign — Shared Content Brief (read fully before building)

You are building ONE of 10 concept redesigns of https://aifl.edu.au/ for a client pitch.
Each concept is a complete, self-contained landing page in a single `index.html` file
(inline CSS + minimal inline JS, Google Fonts via <link>). No build step, no frameworks.

## The client

**AIFL — Australian Institute of Flexible Learning.** Melbourne, Victoria. Established 2005.
Delivering flexible, supported training across Australia in health and community care.
Tagline on the current site: "Education. Empowered. Endeavoured."
Phone: 1300 854 987 · Email: admin@aifl.edu.au
Operated by J J Endeavours Pty Ltd.

Positioning (paraphrase freely, keep the meaning):
- Passionate educators; empowering people through education since 2005.
- Flexible study options that fit around work and life — learn at any age, at any stage.
- Specialises in Health, Community Services, Mental Health, Ageing Support,
  Alcohol and Other Drugs, and Business.
- Trainers are experienced industry practitioners.
- Available throughout Australia, with full student support.
- Funded places via the Skills First program (Victoria) on some courses; VET in Schools
  (VETis) programs; subsidised traineeships.

## Courses (real — use only these, with these codes)

- Certificate IV in Mental Health — CHC43315
- Certificate IV in Ageing Support — CHC43015 · 12 months · Skills First funded
- Certificate III in Individual Support — CHC33015 · 60 weeks
- Certificate IV in Allied Health Assistance — HLT43015 · 69 weeks
- Certificate III in Allied Health Assistance — HLT33015
- Certificate IV in Alcohol and Other Drugs — CHC43215
- Diploma of Community Services — CHC52015
- Certificate III in Community Services — CHC32015
- Certificate II in Community Services — CHC22015
- Provide First Aid — HLTAID003
- Provide CPR — HLTAID001
- Certificate III in Business — BSB30115
- Certificate III in Business Administration (Medical) — BSB31115
- Certificate II in Health Support Services — HLT23215
- Certificate I in Active Volunteering — CHC14015

Real proof points you MAY use (nothing else quantitative):
- Established 2005 (→ "two decades", "since 2005")
- 15+ courses across health, community and business
- Study anywhere in Australia
- Phone 1300 854 987
- Free e-book download offer (motivation & positive thinking) — the site's real lead magnet

Primary conversion action: **course enquiry** ("Enquire now" → mailto:admin@aifl.edu.au or tel:1300854987).
Secondary: browse courses, download the free e-book.

## HARD RULES — the client's explicit asks

1. **No RTO anything.** Do not show "RTO", "RTO 45364", "Registered Training Organisation",
   NRT logos, government crests, or compliance badges anywhere. The rebrand drops the
   regulatory furniture entirely. (Course codes like CHC43315 are fine — they're part of
   course names.)
2. **Very 2026.** This must read as a 2026 redesign, not a 2019 template. Follow the
   Hallmark discipline below.

## HARD RULES — Hallmark design discipline (non-negotiable)

3. **Honest copy — zero invented content.** No made-up statistics ("98% employment",
   "5,000 graduates"), no fake testimonials with invented names, no fake partner/employer
   logos, no fabricated awards. If a proof element isn't in the "Real proof points" list,
   don't show a number. Testimonials: omit them entirely, or use a clearly-labelled
   placeholder quote area ("Student story — to be supplied").
4. **Tokens, not improvisation.** All colours as OKLCH custom properties in a `:root`
   block; every colour/font referenced via `var(--…)`. No raw hex/rgb scattered inline.
5. **Typography:** exactly 2 families (display + body), optionally +1 mono for details,
   loaded from Google Fonts. Never Inter, Roboto, Arial, Open Sans, Lato, Montserrat.
   **No italic headings, ever** — display type is always roman. Italic only inside
   running body copy. Display sizes with `clamp()`.
6. **No AI-slop tells:** no purple-blue gradients, no radial "blobs", no glassmorphism
   hero cards, no generic 3-icon feature row with stock icons, no fake browser/phone
   chrome mockups, no "01 · FEATURES" eyebrow/section tags (headings carry sections
   on their own), no tag-left/heading-right hanging headers, no emoji as UI icons,
   no bounce easing, no animating layout properties (transform + opacity only).
7. **Motion:** ≤3 microinteractions, transform/opacity only, named easings
   (`--ease-out`, `--ease-in`, `--ease-in-out`), durations 150–400ms,
   `prefers-reduced-motion: reduce` collapses everything to ≤150ms opacity fades.
8. **Interaction states:** every button/link/input styled for hover, `:focus-visible`
   (visible ring, ≥3:1, appears instantly — never animated in), `:active`, disabled.
9. **Mobile:** must render flawlessly at 320/375/414/768px. `overflow-x: clip` on
   `html` and `body` (never `hidden`). No two-line button labels. Grids collapse to
   one column; image grid tracks use `minmax(0,1fr)`; hit targets ≥44px on phones.
10. **Stamp:** the FIRST line inside your `<style>` must be:
    `/* Hallmark · variation: <NN> · macrostructure: <name> · theme: <name> · nav: <code> · footer: <code> · tone: <tone> */`
11. **Images:** no stock photography hotlinks. If your concept wants imagery, build it
    with CSS art / hand-written inline SVG (abstract shapes, texture, grain via SVG
    feTurbulence, patterns) — this is encouraged for the "tactile 2026" concepts.
12. Single file. Everything inline. No external CSS/JS except Google Fonts.
    `lang="en-AU"`, sensible `<title>` and meta description, semantic landmarks,
    skip-link, alt/aria where relevant.

## Your deliverable

Write exactly one file: `/Users/john/aifl-redesign/<your-assigned-folder>/index.html`
(create the folder). It must open in a browser with zero console errors and look like
a finished, art-directed page — not a wireframe. Complete page: nav, hero, course
discovery (use the real course list — all 15 or a curated 6-8 with "view all"), why-AIFL,
the e-book lead magnet or enquiry CTA, footer with phone/email/Melbourne/© 2026
J J Endeavours Pty Ltd.

Before finishing: re-read your file top to bottom and fix anything that breaks rules
3–11. Verify no horizontal scrollbar logic errors (long words, wide grids) by reasoning
through 320px width.
