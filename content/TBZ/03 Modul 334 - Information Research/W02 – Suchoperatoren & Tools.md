---
tags: [m334, week02, suchoperatoren]
---

# Week 02 – Suchoperatoren & Tool-Auswahl

## Suchoperatoren

| Operator | Bedeutung | Beispiel |
|---|---|---|
| `site:` | Suche nur auf einer bestimmten Webseite | `site:support.apple.com forgot Apple ID password` |
| `filetype:` | Sucht nur ein bestimmtes Dateiformat, der Suchmaschine wird gesagt, welches Format ausgespuckt werden soll | `IT helpdesk ticket template filetype:xlsx` |
| `"genaue Phrase"` | Sucht exakt diesen Wortlaut | `"the print spooler service is not running"` |
| `-ausschluss` | Minus schliesst ein Wort/Thema aus den Resultaten aus | `Antivirus software -free` (zeigt nur Resultate, die nicht gratis sind) |
| `OR` | Zeigt Resultate, die das eine ODER das andere Wort enthalten | `TeamViewer OR AnyDesk for remote Support` |
| `*` | Platzhalter für etwas, das man nicht mehr weiss | |
| `cache:` | Zeigt eine gespeicherte (ältere) Version einer Webseite, auch wenn sie nicht mehr verfügbar ist/entfernt wurde | `cache:url` |

### Wichtige Grundregeln beim Suchen
- Keine dummen/unpräzisen Fragen stellen.
- Nicht "immer" oder ähnliche vage Wörter benutzen, weil schwierig zu definieren ist, was "immer" wirklich heisst.
- Die Suchmaschine sucht jedes Wort, das man eingibt, einzeln ab. Beispiel: "How do turtles drink" → sie sucht "How", "do", "turtles" und "drink" separat.
- Suchmaschinen werden ständig aktualisiert für unsere Sicherheit, damit Betrüger nicht so leicht Geld damit machen können.
- Machine Learning ist eine Art künstlicher Intelligenz, damit die Suchmaschine versteht, wonach man eigentlich sucht.
- **Indexierung** ist der gesamte Kontext, der in einer Datenbank gespeichert ist.

## Vokabular rund um Suchmaschinen

| Begriff | Definition |
|---|---|
| Index | Die Datenbank aller Seiten, die eine Suchmaschine gespeichert hat |
| Crawler / Spider | Automatisches Programm, das Links auf Webseiten liest und verfolgt |
| Algorithmus | Das Regelwerk, nach dem die Suchmaschine Ergebnisse rankt |
| Organic Result | Ein nicht bezahltes, nach Algorithmus gerankt Resultat |
| Cache | Eine gespeicherte Kopie einer Webseite |
| Sponsored Result | Eine bezahlte Werbung, die oben in den Resultaten erscheint |
| Personalisation | Anpassung der Resultate basierend auf Standort, Verlauf und Präferenzen |

## Fünf Tools – wann welches benutzen

| Tool | Am besten für | Limitation |
|---|---|---|
| Google Search | Breite Fragen, Vergleiche, allgemeine Konzepte | Werbung, Personalisierung, Qualität variiert |
| Microsoft Docs | Windows, Azure, Office – Fehlercodes und Spezifikationen | Nur für Microsoft-Produkte |
| Manufacturer site (Herstellerseite) | Offizielle Treiber, Firmware, Produkt-Datenblätter | Nur für die eigenen Produkte |
| YouTube | Schritt-für-Schritt Video-Anleitungen | Beworbene/falsche Infos möglich, Qualität variiert stark |
| Community Forums | Reale Lösungen für seltene/ungewöhnliche Fehler | Nicht sicher, anonym, Risiko für Viren/Trolling |

### Tool-Sorting-Beispiele (aus dem Unterricht)

| Aufgabe | Bestes Tool |
|---|---|
| Offiziellen Treiber für HP LaserJet 4001n finden | Manufacturer site |
| Windows-Fehler 0x80070005 erklären | Microsoft Docs |
| Multi-Faktor-Authentifizierung einrichten (visuelle Anleitung) | YouTube |
| Seltener Cisco-SG350-Switch-Fehler | Community Forum |
| Welche Windows-10-Versionen noch unterstützt werden | Microsoft Docs / Manufacturer site |
| Offiziellen Client für Fortinet FortiGate VPN herunterladen | Manufacturer site |
| Cloud-Speicher für KMU vergleichen | Google Search |
| Was ist ein Proxy-Server (schnelle Erklärung) | Google Search / Microsoft Docs |

## Search Challenge – eigene Beispiele
- `"Windows 11 Bluetooth issues"` – Microsoft-Support-Artikel finden
- `network security basics filetype:pdf` – PDF-Guide zu Netzwerksicherheit
- `"Your account has been disabled. Please see your system administrator"` – exakte Fehlermeldung suchen
- `cloud storage comparisons -ads` – Cloud-Storage-Vergleiche ohne Werbung
- `OneDrive OR Google Drive business price` – Business-Preise vergleichen

## Siehe auch
- [[W01 – WH-Fragen & Problemanalyse]]
- [[W04 – Dokumente lesen & Quellen bewerten]]
