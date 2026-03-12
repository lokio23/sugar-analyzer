# 🍬 SugarScope — Sugar Quality Analyzer

**By Erber Studio LLC — Sugar Operations Division**

AI-powered ICUMSA sugar quality identification tool. Upload a sample image, enter any known lab data, and get an instant professional-grade analysis.

---

## Features

- 📸 **Image Analysis** — Drop a photo of your sugar sample; Claude Vision reads crystal color, shape, clarity, surface film, and foreign matter
- 🧪 **Lab Data Cross-Reference** — Enter COA values (Pol, moisture, ash, reducing sugars) to validate against ICUMSA specs
- 📊 **Grade Estimation** — Estimates ICUMSA grade (45, 100, 150, 600, 800, 1200+) with confidence scoring
- 🚦 **PASS / WARN / FAIL Verdict** — Clear verdict with detailed inspection flags
- 📏 **ICUMSA Color Scale** — Visual marker showing where your sample lands on the full scale
- 🧾 **Inspector Narrative** — Professional summary combining visual + lab findings

---

## Current Version

`v1.0` — Single-file HTML app (`public/sugar-analyzer.html`)

---

## Quick Start

```bash
# Serve locally
npm start

# Or just open directly in browser
open public/sugar-analyzer.html
```

---

## Roadmap (Claude Code TODO)

- [ ] Convert to React app with component architecture
- [ ] Add shipment logging — save past analyses with timestamps
- [ ] PDF export of inspection results
- [ ] Multi-sample comparison mode
- [ ] COA document upload + auto-parse lab values
- [ ] Mobile PWA for field use
- [ ] Connect to SugarCount database

---

## Project Structure

```
sugar-analyzer/
├── public/
│   └── sugar-analyzer.html    # Current working app (v1.0)
├── src/                       # Future React components
├── package.json
├── .gitignore
├── CLAUDE.md                  # Claude Code instructions
└── README.md
```

---

## API

Uses the Anthropic Claude API (`claude-sonnet-4-20250514`) for vision analysis.
API key is handled by the claude.ai environment — no key needed when running inside Claude artifacts.

> ⚠️ For standalone deployment, you will need to proxy API calls through a backend to protect your Anthropic API key.

---

## Notes

- Sample images should be well-lit, close-up shots of the sugar crystals
- Field photos via WhatsApp are supported
- Best results with natural daylight or neutral white light
- Always cross-reference visual analysis with certified lab COA
