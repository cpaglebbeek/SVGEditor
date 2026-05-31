# RELEASES — SVG Editor

Retroactief samengesteld uit het Downloads-archief (7–15 Feb 2026) plus de huidige live-build. File-data zijn de **originele mtime** uit `~/Downloads`, niet de repo-import-datum (27 maart 2026 — toen werd v1.4.4 als baseline in Git gezet, ~6 weken na de laatste werkelijke build).

Codenaam-thema: **Who Am I (Jackie Chan, 1998)** — per-release codenamen nog niet toegekend.

## Legenda feature-flags
- `line` — lijntekentool aanwezig
- `rect` — rechthoek-tool aanwezig (sinds v1.4.6)
- `BMPSNOOP` — bitmap-snoop integratie aanwezig (⚠ veroorzaakt DOM-bug, zie BUGLIST)
- `pipette` — pipetteCursor variant
- `(basic)` — geen lijn/rect/snoop features

## Status nu live
- **https://icthorse.nl/SVG/** → `svg-layout-editor_OAK_v1.5.9_snoop_redfix2.html` (14 Feb 14:00)
- Eerder live (kort, kapot): `svg-layout-editor_PROD_1.5.5.html` — teruggerold wegens BUG-001

---

## Tijdslijn

### Pre-rebrand prototype (META Layout Editor) — 7 Feb
| Datum | Bestand | Title | Features |
|---|---|---|---|
| 2026-02-07 14:53 | meta_layout_editor_v0_1.html | v0.1 | (basic) |
| 2026-02-07 15:01 | meta_layout_editor_v0_2.html | v0.2 | (basic) |
| 2026-02-07 15:09 | meta_layout_editor_v0_3.html | v0.3 | (basic) |
| (zie volledige lijst onderaan voor v0.4 — v0.11) | | | |

### Phase-iteraties v0.6.x (Phase A → K) — 7–9 Feb
13 phase-builds: A, AB, AC, C, Cplus, D, E, Eplus, F, G, H, J_pipet, K1K2, K_zoom, plus `phaseJ_pipet`, `prod_grid`, `prod_zoom`, `prod_grid_toggle`. Iteratief opbouwen van canvas, assets, tekst, zoom, undo, export.

### Rebrand naar SVG Editor — 9 Feb
| Datum | Bestand | Notitie |
|---|---|---|
| 2026-02-09 | svg-editor1.0.html | Eerste rebrand-build |
| 2026-02-09 | svg-editor1.0_v0.6.8.html | Rebrand van phase H |
| 2026-02-09 | svg-editor_v0.6.8_invoice-fields.html | Invoice-velden experiment |

### Hoofdtak v1.4.x — 9 Feb
| Datum | Bestand | Mijlpaal |
|---|---|---|
| 2026-02-09 | svg-layout-editor_PROD_1.4.2.html | Lijntekentool (eerste PROD) |
| 2026-02-09 | svg-layout-editor_v1.4.3.html | Uitgebreide lijn/stroke |
| 2026-02-09 | svg-layout-editor_v1.4.4.html | Lijnrotatie + handles |
| 2026-02-09 | svg-layout-editor_v1.4.5.html | Tussenversie |
| **2026-02-09 23:11** | **svg-layout-editor_v1.4.6.html** | **▭ Rechthoek-tool toegevoegd** |
| 2026-02-09 23:20 | svg-layout-editor_v1.4.7.html | Rect-tool refinement |
| 2026-02-09 23:31 | svg-layout-editor_v1.4.8_orange.html | Oranje-variant |
| 2026-02-10 | svg-editor-1.4.7.html | Alt-build v1.4.7 |

### OAK-tak v1.4.9–v1.4.22 — 10–14 Feb
Experimentele dev-tak. Highlights: `_red` variant (v1.4.9), kleur-iteraties, UI-tweaks. 14 builds totaal.

### OAK-tak v1.5.0–v1.5.9 — 13–15 Feb
| Datum | Bestand | Mijlpaal |
|---|---|---|
| 2026-02-13 | svg-layout-editor_OAK_v1.5.0.html | Hex-color tool-input (`rectStrokeHexTool`) |
| 2026-02-13 | svg-layout-editor_OAK_v1.5.1.html | — |
| 2026-02-13 | svg-layout-editor_OAK_v1.5.2.html | — |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.3.html | — |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.3_bitmapSnoop.html | **⚠ bmpSnoop-integratie introduceert DOM-bug** |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.4_snoop.html | Schone "snoop" parallel-tak |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.4_bitmapSnoop_line_text.html | ⚠ bmpSnoop |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.5_snoop.html | snoop |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.5_bitmapSnoop_uiFix.html | ⚠ bmpSnoop |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.6_pipetteCursor.html | pipette-variant |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.6_snoop_orange.html | snoop + oranje |
| 2026-02-15 | svg-layout-editor_OAK_v1.5.6_bitmapSnoop_uiOrderFix.html | ⚠ bmpSnoop |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.7_snoop_redfix.html | snoop bugfix |
| 2026-02-15 | svg-layout-editor_OAK_v1.5.7_pipetteCursorFix.html | pipette bugfix |
| 2026-02-14 | svg-layout-editor_OAK_v1.5.8_snoop_diag.html | snoop diagnostics |
| **2026-02-14 14:00** | **svg-layout-editor_OAK_v1.5.9_snoop_redfix2.html** | **Huidige live build (schone DOM)** |
| **2026-02-15 20:00** | **svg-layout-editor_PROD_1.5.5.html** | ⚠ **Bevroren PROD met bmpSnoop-bug — niet meer live** |

### Repo-import + recovery — Maart/Mei 2026
| Datum | Gebeurtenis |
|---|---|
| 2026-03-27 | v1.4.4 in Git gezet als `cpaglebbeek/SVGEditor` baseline (zes weken achter op werkelijkheid) |
| 2026-05-31 | Archief gerecupereerd: 68 builds uit Downloads naar `versions/`, PROD_1.5.5 als index |
| 2026-05-31 | PROD_1.5.5 verworpen (BUG-001), OAK_v1.5.9_snoop_redfix2 als live versie |
