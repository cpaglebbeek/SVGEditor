# CLAUDE.md — SVG Editor

## Project
- **Naam:** SVG Editor
- **Type:** SaaS Webapp
- **Doel:** SaaS SVG Corporate Identity editor
- **Versie:** v1.5.9 (OAK_snoop_redfix2)
- **Codenaam-thema:** Who Am I (Jackie Chan, 1998) facts
- **Huidige codenaam:** Who_Am_I
- **Baseline:** PROD_1.5.5 verworpen wegens DOM-bug (rectToolBtn binnen verborgen bmpSnoopBox); OAK_v1.5.9_snoop_redfix2 als werkende latest
- **Lokaal pad:** `/Users/christian/Documents/Gemini_Projects/SVGEditor`
- **GitHub:** [cpaglebbeek/SVGEditor](https://github.com/cpaglebbeek/SVGEditor)
- **Branch:** main
- **Ecosysteem:** iCt Horse

## Tech Stack
- **Frameworks:** Geen — 100% vanilla JavaScript (ES6+)
- **CSS:** Geen frameworks — custom CSS met CSS variables
- **Dependencies:** Zero — geen externe libraries
- **Architectuur:** Single-file monolithisch HTML (CSS + JS inline)
- **State:** Centraal `state` object, snapshot-based undo (JSON serialisatie)
- **SVG:** Native SVG DOM APIs, DOMParser, XMLSerializer
- **Interactie:** Pointer Events API met setPointerCapture
- **Coördinaten:** Millimeters (A4: 210x297mm), SVG viewBox zoom/pan
- **Thema:** Dark navy (#0b1220), accent blauw (#7aa2ff), warm gele toolbar
- **Taal:** Nederlands (html lang="nl")

## Structuur
```
SVGEditor/
├── index.html                    # Huidige versie (v1.5.9 OAK)
├── META_LAYOUT_MANIFEST.JSON     # Voorbeeld manifest (11 assets, 19 elementen)
├── version.json
├── CLAUDE.md
├── README.md
├── .gitignore
└── versions/                     # 68 historische builds (Feb 2026 archief)
    ├── meta_layout_editor_v0_1 → v0_11                         # Pre-rebrand
    ├── meta_layout_editor_v0_6_*_phaseA → phaseK               # Phase-iteraties
    ├── svg-editor1.0 / svg-editor1.0_v0.6.8 / svg-editor-1.4.7 # Rebrand
    ├── svg-layout-editor_PROD_1.4.2 / PROD_1.5.5               # Productie-builds
    ├── svg-layout-editor_v1.4.3 → v1.4.8_orange                # Hoofdtak
    ├── svg-layout-editor_OAK_v1.4.9_red → v1.4.22              # OAK-tak v1.4
    └── svg-layout-editor_OAK_v1.5.0 → v1.5.9_snoop_redfix2     # OAK-tak v1.5
```

## Versiehistorie (highlights, niet uitputtend)
| Versie | Fase | Key Features |
|--------|------|--------------|
| v0.1 – v0.11 | meta_layout_editor | Pre-rebrand prototype |
| v0.6.x | phaseA – phaseK | Phase-iteraties: canvas, assets, tekst, zoom, undo, export |
| v0.6.8 | Phase H | SVG assets, tekst, kleurremapping, zoom/pan, undo, SVG/JSON export |
| v1.4.2 | PROD | Lijntekentool, stroke kleur/dikte, NL labels |
| v1.4.4 | — | Lijnrotatie, rotation handle, +/-15° knoppen (eerste git-import 27 mrt) |
| v1.4.6 | — | **Rechthoek-tool** (▭ Rechthoek + rectToolControls) |
| v1.4.9 | OAK_red | Start OAK-experimentele tak |
| v1.5.0 | OAK | Hex-color input (rectStrokeHexTool) |
| v1.5.4 | OAK_snoop | "snoop" pipet-mechanisme |
| v1.5.5 | PROD | bmpSnoop-integratie — **DOM-bug: rectToolBtn binnen verborgen wrapper** |
| v1.5.9 | OAK_snoop_redfix2 | Latest werkende build (huidige live versie) |

## Versioning & Codenamen
| Kleur | Impact | Versie | Codenaam |
|-------|--------|--------|----------|
| Groen | Minor (code only) | +0.0.1 | Who Am I fact |
| Oranje | Design impact | +0.1.0 | Who Am I fact |
| Rood | Major (redesign) | +1.0.0 | Who Am I fact |

## Protocollen
- **WhatIf Protocol:** Verplicht voor elke build/wijziging (zie Meta_Master)
- **Auto commit + push:** Na elke wijziging
- **Root Cause Analysis:** Verplicht bij elke bugfix (Functioneel, Technisch, Architectonisch)
