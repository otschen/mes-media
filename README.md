# FlexxLink MES — LinkedIn Carousel Media Repository

**Zweck:** Public CDN für LinkedIn Carousel-Posts via GitHub Pages. Enthält PDFs und PNG-Thumbnails für die Buffer-Integration.

---

## 1. Projektübersicht

| Element | Wert |
|---------|------|
| **Serie** | MES Integration — Shopfloor trifft ERP |
| **Produkt** | FlexxLink MES |
| **Topics** | 20 |
| **Sprachen** | 7 (DE, EN, IT, FR, DK, NO, SE) |
| **Total Assets** | 140 PDFs + 140 PNGs |
| **Format** | 1080 × 1350 px (LinkedIn Portrait 4:5) |

---

## 2. Ordnerstruktur

```
flexxlink-mes-media/
├── README.md
└── docs/
    ├── topic-01/
    │   ├── flexxlink-mes-topic01-mes-trifft-d365-de.pdf
    │   ├── flexxlink-mes-topic01-mes-trifft-d365-de.png
    │   ├── flexxlink-mes-topic01-mes-meets-d365-en.pdf
    │   ├── flexxlink-mes-topic01-mes-meets-d365-en.png
    │   └── ... (7 Sprachen × 2 Dateien = 14 Dateien)
    ├── topic-02/
    ├── topic-03/
    └── ... (20 Topics)
```

---

## 3. Benennungskonventionen

### 3.1 Topic-Ordner
```
topic-<NN>
```
`NN` = zero-padded Topic-Nummer (01, 02, ... 20)

### 3.2 PDF-Dateinamen
```
flexxlink-mes-topic<NN>-<slug>-<lang>.pdf
```
Beispiele:
- `flexxlink-mes-topic01-mes-trifft-d365-de.pdf`
- `flexxlink-mes-topic01-mes-meets-d365-en.pdf`
- `flexxlink-mes-topic12-multi-order-fr.pdf`

### 3.3 PNG-Thumbnails
```
flexxlink-mes-topic<NN>-<slug>-<lang>.png
```
Identisch zu PDF, nur mit `.png` Extension. Thumbnail = Slide 1.

### 3.4 Sprach-Codes
| Code | Sprache |
|------|---------|
| `de` | Deutsch |
| `en` | English |
| `it` | Italiano |
| `fr` | Français |
| `dk` | Dansk |
| `no` | Norsk |
| `se` | Svenska |

---

## 4. GitHub Pages URLs

Nach Aktivierung von GitHub Pages (Branch: `main`, Folder: `/docs`):

```
https://otschen.github.io/flexxlink-mes-media/topic-<NN>/<filename>.pdf
https://otschen.github.io/flexxlink-mes-media/topic-<NN>/<filename>.png
```

Beispiele:
```
https://otschen.github.io/flexxlink-mes-media/topic-01/flexxlink-mes-topic01-mes-trifft-d365-de.pdf
https://otschen.github.io/flexxlink-mes-media/topic-01/flexxlink-mes-topic01-mes-trifft-d365-de.png
https://otschen.github.io/flexxlink-mes-media/topic-12/flexxlink-mes-topic12-multi-order-en.pdf
```

---

## 5. Topic-Liste

| # | Slug (DE) | Thema |
|---|-----------|-------|
| 01 | mes-trifft-d365 | MES trifft Dynamics 365 |
| 02 | fertigungsstart-echtzeit | Fertigungsstart in Echtzeit |
| 03 | fertigmeldung-optimieren | Fertigmeldung optimieren |
| 04 | auftrag-abschliessen | Auftrag abschliessen (BOM) |
| 05 | prozessfertigung-formula | Prozessfertigung (Formula) |
| 06 | material-entnahme | Material-Entnahme |
| 07 | arbeitsgang-zeiten | Arbeitsgang-Zeiten |
| 08 | maschinen-personalzeiten | Maschinen- und Personalzeiten |
| 09 | zentrale-ueberwachung | Zentrale MES-Überwachung |
| 10 | datenqualitaet | Datenqualität sicherstellen |
| 11 | buchungsverhalten | Buchungsverhalten steuern |
| 12 | multi-order | Mehrere Aufträge gleichzeitig |
| 13 | performance-async | Performance optimieren (Async) |
| 14 | multi-threading | Multi-Threading nutzen |
| 15 | status-api | Status-Transparenz (Push API) |
| 16 | related-info | Sichtbarkeit in Dynamics 365 |
| 17 | middleware | Middleware anbinden |
| 18 | retry-backoff | Automatische Wiederholung |
| 19 | automatisierung | Die richtige Automatisierung |
| 20 | kostenstellen | Kostenstellen zuordnen |

---

## 6. Buffer Integration

### 6.1 Kanal
- **Profil:** Horst Fischer (LinkedIn)
- **Profile-ID:** `6962712d457dae6a34f75a6d`

### 6.2 Zeitplan
```
07:00 Europe/Zurich
12:00 Europe/Zurich
17:00 Europe/Zurich
```
→ 3 Posts pro Tag

### 6.3 Sprach-Rotation
```
DE → EN → IT → FR → DK → NO → SE
```

### 6.4 Rhythmus
- Tag 1: Topic N — DE (07:00), EN (12:00), IT (17:00)
- Tag 2: Topic N — FR (07:00), DK (12:00), NO (17:00)
- Tag 3: Topic N — SE (07:00), Topic N+1 — DE (12:00), EN (17:00)
- ...

### 6.5 Gesamtdauer
```
20 Topics × 7 Sprachen = 140 Posts
140 Posts ÷ 3 Posts/Tag = ~47 Tage
```

---

## 7. Buffer API Dokumenten-Posts

Für LinkedIn Document Posts (Carousels):

```json
{
  "profileIds": ["6962712d457dae6a34f75a6d"],
  "text": "<Post-Text aus posts/*.txt>",
  "assets": {
    "documents": [{
      "url": "https://otschen.github.io/flexxlink-mes-media/topic-01/flexxlink-mes-topic01-mes-trifft-d365-de.pdf",
      "title": "MES trifft Dynamics 365",
      "thumbnailUrl": "https://otschen.github.io/flexxlink-mes-media/topic-01/flexxlink-mes-topic01-mes-trifft-d365-de.png"
    }]
  },
  "schedulingType": "automatic"
}
```

---

## 8. Design-Spezifikation

| Element | Wert |
|---------|------|
| **Canvas** | 1080 × 1350 px |
| **Slides** | 4 pro Carousel |
| **Font** | Outfit (Google Fonts) |
| **Gradient** | 170° Winkel |
| **S1** | Teal (#0d9488 → #115e59) |
| **S2** | Navy (#1e3a5f → #172554) |
| **S3** | Purple (#6366f1 → #8b5cf6) |
| **S4** | Orange (#f97316 → #c2410c) |
| **Accent** | #f97316 (Orange) |

---

## 9. Verwandte Ressourcen

| Resource | Location |
|----------|----------|
| Post-Texte | `flexxlink-mes-series/topic-XX-*/posts/*.txt` (lokal) |
| Master PDFs | `flexxlink-mes-series/topic-XX-*/carousel/*.pdf` (lokal) |
| Buffer Handover | `BUFFER-POSTING-AUTOMATION-HANDOVER.md` |

---

## 10. Autor

**Horst Fischer**  
MCP · 30 Jahre Dynamics-Erfahrung  
Soluvine GmbH · [soluvine.com](https://soluvine.com)

---

**Stand:** April 2026  
**Serie:** MES Integration — Shopfloor trifft ERP
