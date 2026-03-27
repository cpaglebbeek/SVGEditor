# CLAUDE.md — SVG Editor

## Project
- **Naam:** SVG Editor
- **Type:** SaaS Webapp
- **Doel:** SaaS SVG Corporate Identity editor
- **Versie:** v1.4.4
- **Codenaam-thema:** Who Am I (Jackie Chan, 1998) facts
- **Huidige codenaam:** Who_Am_I
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
├── index.html                    # Huidige versie (v1.4.4)
├── META_LAYOUT_MANIFEST.JSON     # Voorbeeld manifest (11 assets, 19 elementen)
├── version.json
├── CLAUDE.md
├── README.md
├── .gitignore
└── versions/                     # Versiehistorie
    ├── v0.6.8_phase-h.html       # Phase H: basis canvas + export
    ├── v1.1.1.html               # Collapsible toolbox + packages
    ├── v1.4.2_prod.html          # Lijntekentool (productie)
    ├── v1.4.3.html               # Tussenversie
    └── v1.4.4.html               # Lijnrotatie (latest)
```

## Versiehistorie
| Versie | Fase | Key Features |
|--------|------|--------------|
| v0.6.8 | Phase H | SVG assets, tekst, kleurremapping, zoom/pan, undo, SVG/JSON export |
| v1.1.1 | — | Inklapbare toolbar, element packages, asset deduplicatie |
| v1.4.2 | PROD | Lijntekentool, stroke kleur/dikte, NL labels |
| v1.4.3 | — | Uitgebreide lijn/stroke features |
| v1.4.4 | Latest | Lijnrotatie, rotation handle, +/-15° knoppen |

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
