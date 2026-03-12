# CLAUDE.md — SugarScope Project Instructions

This file tells Claude Code about this project so it can work effectively.

---

## Project Overview

**SugarScope** is an AI-powered sugar quality analyzer for Erber Studio LLC's Sugar Operations division.

It helps inspect bulk imported sugar (primarily ICUMSA 45 and ICUMSA 150) by:
1. Analyzing sample photos via Claude Vision API
2. Cross-referencing lab/COA data against ICUMSA specifications
3. Producing PASS/WARN/FAIL verdicts with detailed inspection flags

---

## Current State

- `v1.0` is a **single-file HTML app** at `public/sugar-analyzer.html`
- It uses the Anthropic API directly from the browser (works inside claude.ai artifacts)
- No build system yet — runs with `npx serve public`

---

## Tech Stack (Current)

- Vanilla HTML/CSS/JS
- Anthropic Claude API (`claude-sonnet-4-20250514`) for vision
- Google Fonts (Share Tech Mono, Barlow Condensed, Barlow)

---

## Tech Stack (Target / Roadmap)

- React + Vite
- Tailwind CSS
- Anthropic SDK (via backend proxy)
- Node.js/Express backend (to protect API key)
- SQLite or Supabase for shipment logging

---

## Design Language

- Dark industrial/scientific aesthetic
- Color palette: `#0a0c0e` bg, `#00e5a0` accent (green), `#ff4757` danger, `#f5a623` warning
- Fonts: Barlow Condensed (display), Share Tech Mono (data/labels), Barlow (body)
- Tone: Precision instrument — like a lab device UI

---

## Key Domain Knowledge

### ICUMSA Grades
| Grade | Color | Pol | Moisture | Ash |
|-------|-------|-----|----------|-----|
| ICUMSA 45 | ≤45 IU — brilliant white | ≥99.8°Z | ≤0.04% | ≤0.04% |
| ICUMSA 150 | ≤150 IU — cream/light golden | ≥99.5°Z | ≤0.06% | ≤0.10% |
| ICUMSA 600 | VHP raw — light brown | ≥99.2°Z | ≤0.10% | ≤0.25% |

### Visual Inspection Rules
- ICUMSA 45: brilliant white, high sparkle, no cream tone, water-clear dissolved solution
- ICUMSA 150: off-white to light cream, slight opacity acceptable, faint straw-yellow dissolved
- Any musty/sour odor = immediate REJECT
- Any visible insects/rodent evidence = immediate REJECT
- Dissolved solution test: 10% solution in distilled water checked against daylight

---

## Planned Features (build these when asked)

1. **React conversion** — componentize the existing HTML app
2. **Shipment log** — store past analyses (date, lot#, grade, verdict, notes)
3. **PDF export** — generate inspection report PDF
4. **COA parser** — upload a PDF COA and auto-extract lab values
5. **Multi-sample compare** — side-by-side analysis of multiple samples
6. **Mobile PWA** — installable on phone for field use
7. **Backend proxy** — Node.js server to handle API key securely

---

## Owner

Collin Erber — Erber Studio LLC, Colorado
Sugar operations based in Miami market.
