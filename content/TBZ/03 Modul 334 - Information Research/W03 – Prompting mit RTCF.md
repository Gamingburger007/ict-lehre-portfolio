---
tags: [m334, week03, prompting, ki]
---

# Week 03 – Prompting mit RTCF

RTCF = **Role, Task, Context, Format**. Je mehr dieser vier Elemente ein Prompt enthält, desto präziser und nützlicher ist die KI-Antwort.

- **R – Role:** Welche konkrete Rolle/Fachperson soll die KI einnehmen?
- **T – Task:** Was genau soll die KI tun?
- **C – Context:** Welcher Hintergrund ist relevant?
- **F – Format:** Wie soll die Ausgabe strukturiert sein?

## Praxis-Szenario: The AI Ticketing Optimisation (HZ2)

**Firma:** Müller & Partner AG. Ticketing: E-Mail + Tabelle, kein Helpdesk-Tool. ≈200 Tickets/Woche, 30 Agents. Compliance: GDPR/nDSG hat Priorität. Aktuell keine KI-Tools im Einsatz.

> **Thomas Berger, IT Director:** "I've read that AI tools can handle 40% of repetitive tickets automatically — password resets, VPN errors, software questions. Find out what's available, what it costs, how easy it is to set up, and whether it integrates with our Microsoft 365. I also need to know about any data protection issues. Two weeks."

### Prompt 1 – vague (Beispiel)
*"find me an ai that can create ticketing system"*
→ Ergebnis: generische Vorschläge (Lovable, Base44, Replit Agent …), aber nichts auf die Firma zugeschnitten.

### Prompt 2 – Role + Task (Beispiel)
*"im working with microsoft 365 at an IT departement"*
→ Deutlich besseres Ergebnis: Microsoft Power Apps + Power Automate + Dataverse, Microsoft Copilot Studio, Jira Service Management als Alternativen – bereits auf das bestehende M365-Ökosystem zugeschnitten.

### Prompt 3 – Full RTCF (Beispiel)
Der komplette Brief von Thomas Berger als Prompt eingegeben → die KI erkennt die eigentliche Aufgabe (eine kleine **Technologie-Evaluation/Empfehlung**, kein reiner Tool-Vorschlag) und liefert:
- Eine strukturierte Research-Checkliste (Was ist verfügbar? Was kostet es? Wie einfach einzurichten? M365-Integration? Datenschutz?)
- Eine Kurzliste: **Microsoft Copilot Studio + Power Automate** (empfohlen), ServiceNow + AI Agents (Enterprise-Alternative), bestehendes M365 + Copilot Chat (Low-Cost-Einstieg)
- Wichtiger Hinweis: Die 40%-Automatisierungs-Behauptung aus dem Brief nicht einfach übernehmen, sondern selbst prüfen, welche Ticket-Kategorien realistisch automatisierbar sind.

> **Welcher Prompt hat am meisten gebracht?** Der dritte Prompt (volles RTCF) gab die nützlichste Antwort, weil er die relevantesten und detailliertesten Informationen für die Aufgabe lieferte – Kosten, M365-Integration, Aufwand und Datenschutz, also genau die Punkte aus dem Brief.

## Wichtige Lektion
Ein guter Prompt verwandelt eine vage Bitte ("find me an AI…") in eine klare Aufgabenstellung (eine Technologie-Empfehlung für einen bestimmten Entscheidungsträger, mit bestimmten Kriterien). Je mehr RTCF-Elemente enthalten sind, desto handlungsrelevanter die Antwort.

> Dieses Szenario (HZ2) kehrt in Woche 6 und Woche 11 zurück ("Advanced Prompting") – die drei Prompts + Antworten lohnt es sich aufzuheben.

## Siehe auch
- [[W01 – WH-Fragen & Problemanalyse]]
- [[KI Grundlagen]]
- [[W06 – Big-6-Modell & Research-Plan]]
