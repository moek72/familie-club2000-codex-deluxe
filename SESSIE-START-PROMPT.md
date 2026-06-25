# Sessie-startprompt voor WK Poule

> **LAATSTE UPDATE: 25 juni 2026** — lees dit blok eerst.

## ⚡ ACTUELE STAND (waar zijn we gebleven)

| Onderdeel | Status |
|-----------|--------|
| **Leidende/live branch** | `main` van `moek72/wk-poule` (NIET meer `claude/nieuwsbrief`) |
| **Lokale clone** | `G:\Mijn Drive\wk 26\repo\` — staat op `main`, push-rechten werken |
| **Live app** | https://moek72.github.io/wk-poule/wkpoule.html (GitHub Pages volgt `main`) |
| **Shirt-avatars** | ✅ KLAAR & LIVE — alle 20 in `assets/shirts/`, ranglijst + spelerskaart, Shyam- en Oetra-fix gedaan |
| **Auto-backup** | ✅ Draait automatisch (GitHub Action pusht Firebase-export naar `main`, meermaals per dag) |
| **8e finale w73** | ✅ INGEVULD & LIVE (25 jun): Zuid-Afrika vs Canada (2e A vs 2e B) |

### 🔴 VOLGENDE TAAK — vrijdag 27 juni 2026
**De rest van de achtste finales invullen.** Op 25 jun zijn alleen groepen A, B, C klaar:
- A: 1e Mexico, 2e Zuid-Afrika
- B: 1e Zwitserland, 2e Canada
- C: 1e Brazilië, 2e Marokko

Vanaf vrijdag 27 jun zijn D t/m L klaar → dan in één keer de overige ~15 8e-finales (w74 t/m w88) invullen, inclusief de 3e-plaats-slots (die kunnen pas als ÁLLE groepen gespeeld zijn).

**Werkwijze:** bereken groepsstanden uit Firebase `_r` (uitslagen), NOOIT uit voorspellingen. Vervang in `wkpoule.html` de placeholders ("Winnaar Poule X", "2e Poule X", "3e ...") door echte landnamen. Gebruik exact dezelfde spelling als in de groepsfase (bv. "Zuid-Afrika", "Verenigde Staten"). Daarna committen + pushen naar `main`.

---

## Waar zijn de bestanden te vinden?

| Bestand | Locatie | Waarvoor |
|---------|---------|----------|
| `WKPOULE.md` | repo root (`moek72/wk-poule`, branch `main`) | Volledige project-context, Firebase structuur, puntensysteem |
| `SESSIE-START-PROMPT.md` | repo root | Dit bestand |
| `wkpoule.html` | repo root | De volledige app (single file, alles erin) |
| `wk-gazette-presentatie.html` | repo root | HTML nieuwsbrief slideshow (13 slides) |
| `assets/shirts/` | repo root | 20 voetbalshirt PNG's per deelnemer (KLAAR) |
| `backups/` | repo root | Firebase backups als JSON (auto + handmatig) |
| `remotion-poule/` | repo root | Video-generator (puppeteer + ffmpeg) |

**Lokaal werken:** open `G:\Mijn Drive\wk 26\repo\` (op `main`). Daar staat alles, push werkt.

⚠️ **Valkuil:** `C:\Games\familie-club2000-codex-deluxe` lijkt de poule maar is een ÁNDER project (remote = `familie-runner`). Niet gebruiken.

---

## Kopieer dit als sessie-startprompt

```
Lees eerst WKPOULE.md én de "ACTUELE STAND" bovenin SESSIE-START-PROMPT.md.

Dit is de WK 2026 poule-app voor de Jaikaran-familie.
Repo: moek72/wk-poule — LEIDENDE/LIVE branch: main
Lokale clone: G:\Mijn Drive\wk 26\repo (staat op main, push werkt)
Live app: https://moek72.github.io/wk-poule/wkpoule.html
Firebase: https://wk-2026-poule-867ae-default-rtdb.europe-west1.firebasedatabase.app (pad: v/)

⚠️ NOOIT deelnemersdata verwijderen uit Firebase.
Filter altijd: k !== '_r' && k !== '_k' && k !== '_bbq' && k !== '_quiz'
⚠️ Stats/scores ALTIJD live uit Firebase REST API halen, nooit uit statische bestanden.

GEDAAN (t/m 25 jun 2026):
- Shirt-avatars: 20 stuks live in app (assets/shirts/), Shyam+Oetra gefixt
- Stats-tegels (ONTDEK-sectie): spelerskaart, speler v/d dag, streaks, etc.
- WK Gazette: HTML-presentatie + MP4-pipeline + slides
- 8e finale w73 ingevuld & live: Zuid-Afrika vs Canada

VOLGENDE TAAK (vanaf 27 jun): rest van de 8e finales (w74-w88) invullen
zodra groepen D-L klaar zijn. Standen uit Firebase _r berekenen.

Puntensysteem: exacte score +5pt | juiste winnaar +2pt | kampioen +10pt

WAT IK NU WIL DOEN:
[VUL HIER IN]
```
