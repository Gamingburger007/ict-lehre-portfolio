---
tags: [reflexion, modul117]
datum: 08.11.2026
---

# Reflexion Modul 117

> [!info] Worum ging es?
> Benutzer, Gruppen, Berechtigungen und Freigaben: meine Berechtigungs-Matrix für VM2 nach der neuen Theorie verbessern und eine IT-Doku-Vorlage aufbauen. Passende Notizen: [[Hausaufgabe 09.11. – IT-Dokumentation & Berechtigungs-Matrix]], [[Hausaufgabe 02.11. – Benutzer, Gruppen & Berechtigungs-Matrix]], [[Praxisauftrag VM-Netzwerk]], [[IP-Adressierung & Subnetting]]

## Was habe ich gelernt?
- Benutzer = **wer**, Gruppe = **wem**, Berechtigung = **was**, Freigabe = **wo**.
- Rechte nur an Gruppen geben. Die Standardgruppen GroupMA und GroupAdmin erstellt man immer, auch wenn der Kunde sie nicht verlangt.
- Immer zwei Tabellen machen: zuerst wer in welcher Gruppe ist, dann die Berechtigungs-Matrix.
- In eine IT-Dokumentation gehören Namen, Pfade, Passwortrichtlinien und das IP-Konzept, aber keine Passwörter.

## Was hat gut funktioniert?
- Meine BM vom 01.11. war schon gut aufgebaut (Freigabe grosszügig, feine Rechte über NTFS). Ich musste sie nur anpassen, nicht neu machen.

## Wo hatte ich Schwierigkeiten?
- Dass Freigabe- und NTFS-Rechte zusammen wirken und übers Netzwerk das strengere gilt.
- Die Vererbung: Rechte von oben kommen automatisch mit, wenn man sie nicht unterbricht.

%% Screenshot vom Fehler oder Problem hier einfügen: Win+Shift+S, dann Strg+V %%

## Wie habe ich es gelöst?
- Mit `icacls` und `net share` geprüft, ob die Einstellungen auf der VM zur Tabelle passen.

## Was mache ich nächstes Mal anders?
- Zuerst die zwei Tabellen planen (IPERKA: Planung), erst dann Benutzer und Ordner in der VM einrichten.
- Von Anfang an die Kürzel R / M / X / F verwenden.

## Bilder zum Lernprozess
%% Zwischenstände, Fehlermeldungen, Endergebnis. Unter jedes Bild eine kurze Zeile, was man sieht. %%


---

## 26.11.2026 – LB2 SolarConcept: Phase 1 abgeschlossen, Phase 2 begonnen

> [!info] Worum ging es?
> Mit Puro plane ich die komplette IT für die SolarConcept AG (HQ in Wollishofen, Branch in der Enge). Phase 1: Fragenkatalog, Grobplanung, Internetanschluss abklären, IT-Doku und Projektablage vorbereiten. Phase 2: Rack, Grundrisspläne, logischer Netzwerkplan und Offerte. Passende Notizen: [[Internetzugang]], [[Universelle Gebäudeverkabelung (UGV)]], [[Logischer & physischer Netzwerkplan]], [[Offerte erstellen]]

### Was habe ich gelernt?
- Am Anfang die richtigen Fragen stellen ist das Wichtigste. Ohne die Antworten von Herrn Perret hätten wir falsch geplant (z. B. war die Adresse der Branch falsch: Sternenstrasse **24**, nicht 74).
- Eine Antwort kann das ganze Konzept ändern: Weil die Branch auf Fileserver, Datenbank und PBX im HQ zugreifen muss, verbinden wir die Standorte mit einem **Site-to-Site-VPN** statt sie getrennt zu lassen.
- Internetanbieter vergleicht man nach Technologie, Up-/Download, einmaligen und monatlichen Kosten. Gewählt haben wir Salt mit 1 Gbit/s Glasfaser.
- Eine IT-Doku braucht von Anfang an eine feste Struktur (Titel, Änderungsverzeichnis, Inhaltsverzeichnis, Seitenzahlen), sonst wird sie später chaotisch.

### Was hat gut funktioniert?
- Die Fragen nach Priorität sortieren (A = in der 5-Minuten-Besprechung fragen, B = später klären). So hat die kurze Besprechung gereicht.
- Die gemeinsame Projektablage in OneDrive: Puro und ich haben immer den gleichen Stand.

### Wo hatte ich Schwierigkeiten?
- An alles denken, was es für die Installation braucht: Wanddurchbrüche, Klima im Serverraum, USV, Strom fürs Rack.
- Realistische Preise für die Offerte finden, weil es so viele Positionen sind.

### Wie habe ich es gelöst?
- Mit der Checkliste von Herrn Perret geprüft, ob alles für Phase 1 erledigt ist, bevor wir mit Phase 2 begonnen haben.

### Was mache ich nächstes Mal anders?
- Die Aufgabenteilung mit Puro früher festlegen und im Projektplan eintragen.
- Preise in der Offerte direkt mit aktuellen Händlerpreisen vergleichen und die Offerten von Elektriker und Klima früher anfragen.
