# Algebra 1 EOC Practice Bank

A self-contained, single-file HTML study tool for the Florida B.E.S.T. Algebra 1 End-of-Course exam. **420 practice questions** (14 variations each of 30 problem types) with hints, step-by-step walkthroughs, topic filtering, test/exam mode with weakness analysis, and full localStorage persistence — all in **one HTML file**, no build step, no server.

**Live:** [jgrose.github.io/fl-eoc-alg1practice](https://jgrose.github.io/fl-eoc-alg1practice/)

## Features

- **Study mode** — One question at a time with prev/next carousel. Show hints, view full walkthroughs, scratchpad your work, get instant feedback. Filter by topic. Collapsible jump-grid for all 420 questions. Position persists across reloads.
- **Test / Exam mode** — Build a custom test: pick topics, choose 5–60 questions, random or sequential, with optional timer. *Exam Simulation* hides hints/walkthroughs until you submit. Timer can count up or count down with auto-submit at zero.
- **History** — Every completed test is saved with date, score, duration, mode (practice/exam), and a per-topic breakdown. "Retake Same Questions" button on each entry.
- **Weakness analysis** — A tiered signal (wrong = 1.0, opened walkthrough = 1.0, hint-only = 0.4) is tracked per question and merged across sessions via EMA. The end-of-test summary ranks the topics needing review.
- **Printable answer key** — One-click print view (`@media print`) shows all 420 questions with correct answers highlighted plus walkthroughs.
- **KaTeX math rendering** — Equations like `P = 5D/T`, `x²`, `∛7` get rendered as proper math. Falls back to plain Unicode text if KaTeX can't load.

## Question bank

420 questions organized into 30 problem types, 14 variations each, modeled on the publicly released 2024 B.E.S.T. Algebra 1 EOC test:

| Topic group        | Types | Questions |
|--------------------|------:|----------:|
| Linear Functions   |     6 |        84 |
| Inequalities       |     5 |        70 |
| Polynomials        |     4 |        56 |
| Exponential        |     4 |        56 |
| Function Type      |     4 |        56 |
| Quadratic          |     3 |        42 |
| Scatter / Models   |     2 |        28 |
| Systems            |     1 |        14 |
| Data & Stats       |     1 |        14 |
| **Total**          | **30**| **420**   |

Every question has a hint and a step-by-step walkthrough ending with the correct answer letter.

## Usage

### Run online
Visit [jgrose.github.io/fl-eoc-alg1practice](https://jgrose.github.io/fl-eoc-alg1practice/) — works in any modern browser.

### Run locally
```bash
git clone https://github.com/jgrose/fl-eoc-alg1practice.git
open fl-eoc-alg1practice/Algebra1_EOC_Practice_Bank.html
```

No build, no install, no server. KaTeX is loaded from jsDelivr CDN; everything else is inline in the single HTML file.

## Keyboard shortcuts (Study mode)

| Key | Action            |
|-----|-------------------|
| ←   | Previous question |
| →   | Next question     |

Suppressed while typing in the scratchpad or other text inputs.

## Persistence

All state is stored in `localStorage` under the key `algebra1eoc.v1`:

- Study mode answers and correct/incorrect flags
- Scratchpad notes per question
- Per-question weakness flags (EMA across sessions)
- Test history (up to 100 most recent attempts)
- UI prefs (last topic filter, current question, nav-row open/closed, test-builder settings)

Click **⚠ Clear Saved Progress** in Study mode to wipe everything.

## Browser support

Tested in current Chrome, Safari, and Firefox. Requires `localStorage`, `<details>`, and ES2017+ JavaScript.

## Tech notes

- Single file: ~230 KB of HTML/CSS/JS with 420 questions inline as a JavaScript array
- Vanilla HTML/CSS/JS — no React, no framework, no jQuery, no bundler
- KaTeX 0.16 via jsDelivr CDN for math rendering
- One-question carousel keeps the DOM small even with 420 questions held in memory
- `<details>` element for collapsible question navigator

## Disclaimer

This is an unofficial study aid. Question content consists of original value-variations modeled on the publicly available 2024 Florida B.E.S.T. Algebra 1 EOC released test items — *not* the actual exam questions. Not affiliated with or endorsed by the Florida Department of Education.
