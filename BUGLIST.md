# BUGLIST — SVG Editor

## BUG-001 — Rechthoek-knop onzichtbaar door verbroken DOM in bmpSnoop-builds

**Status:** Vermeden door versie-rollback (niet gefixt in bron). PROD_1.5.5 + 5 OAK bmpSnoop-builds blijven defect in `versions/`.

**Gevonden:** 2026-05-31 — tijdens redeploy van PROD_1.5.5 naar `icthorse.nl/SVG/`.

**Symptoom:**
- `▭ Rechthoek` knop ontbreekt zichtbaar in de toolbox.
- HTML-bron bevat `<button id="rectToolBtn">` correct, JS-binding werkt, geen JS-fouten.

**Affected versies** (alle bouwbestanden met `bmpSnoop` in naam):
- `svg-layout-editor_PROD_1.5.5.html` ← werd live tot rollback
- `svg-layout-editor_OAK_v1.5.3_bitmapSnoop.html`
- `svg-layout-editor_OAK_v1.5.4_bitmapSnoop_line_text.html`
- `svg-layout-editor_OAK_v1.5.5_bitmapSnoop_uiFix.html`
- `svg-layout-editor_OAK_v1.5.6_bitmapSnoop_uiOrderFix.html`

**Niet getroffen** (zelfde versie-range, andere snoop-implementatie):
- `*_snoop*.html` varianten (OAK v1.5.4 → v1.5.9)
- `*_pipetteCursor*.html` varianten

## Root Cause Analysis

**Functioneel:** Gebruiker mist een toolbox-knop die volgens release-info aanwezig zou moeten zijn.

**Technisch:** In de toolbox-template wordt `<div class="toolGroup" id="bmpSnoopBox" style="display:none;">` geopend rond regel 507 maar de bijbehorende `</div>` ontbreekt vóór `<button id="rectToolBtn">` op regel 529. Daardoor zit de rechthoek-knop (en alles daarna tot de eerstvolgende ongekoppelde sluit-tag) **binnen** een container met `display:none`. Browser rendert de knop niet.

**Architectonisch:** De bmpSnoop-feature is in 5 OAK-builds en in PROD_1.5.5 geïntegreerd zonder DOM-structuurvalidatie of UI-rookbeleid. Het PROD-stempel werd toegekend zonder visuele regressietest van de toolbox. Geen build-pipeline met HTML-linting (single-file edit-flow).

## Workaround live (2026-05-31)

Live-versie teruggerold naar `svg-layout-editor_OAK_v1.5.9_snoop_redfix2.html` (14 Feb 14:00), de hoogste OAK-build die de oude "snoop"-implementatie gebruikt en een schone DOM heeft (rectToolBtn zit niet binnen een display:none container).

## Fix-richting (open)

Eén van:
1. **Bron-fix in PROD_1.5.5**: ontbrekende `</div>` invoegen vóór `rectToolBtn`, verifiëren dat alle volgende sluit-tags consistent kloppen, opnieuw als PROD-build uitbrengen.
2. **Refactor bmpSnoop → snoop**: bmpSnoop-feature opnieuw integreren bovenop OAK v1.5.9 met dezelfde "snoop" UI-conventie.
3. **Accepteren**: PROD_1.5.5 als historisch artefact in `versions/` laten staan, v1.5.9 OAK als nieuwe productie-lijn voortzetten.

Geen acute keuze nodig — workaround is stabiel.
