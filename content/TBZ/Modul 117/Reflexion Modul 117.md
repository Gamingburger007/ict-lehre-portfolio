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

