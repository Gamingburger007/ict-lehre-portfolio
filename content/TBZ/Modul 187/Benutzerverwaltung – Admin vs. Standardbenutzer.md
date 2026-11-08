---
tags: [betriebssysteme, modul187, benutzerverwaltung]
datum: 19.10.2026
---

# Benutzerverwaltung – Admin vs. Standardbenutzer

Unter Windows gibt es hauptsächlich zwei Arten von Benutzerkonten: **Administrator** und **Standardbenutzer**. Fast alle Benutzer in einer Firma sind eines von beiden.

## Kontotypen

### Standardbenutzer
Der Standardbenutzer kann nur die alltäglichen Funktionen gebrauchen und ausführen (Programme starten, eigene Dateien bearbeiten, eigene Einstellungen wie Hintergrund ändern). Er hat **keine Adminrechte** und kann nichts am System ändern:
- ❌ keine Software installieren, die ins System eingreift
- ❌ keine Treiber installieren (ausser solche, die Windows automatisch über Windows Update holt)
- ❌ keine Benutzerkonten verwalten
- ❌ kein Zugriff auf Systemdateien und -einstellungen

### Administrator
Der Admin hat **volle Zugriffsrechte**: Er kann neue Software und Treiber installieren, Systemeinstellungen ändern, Benutzerkonten verwalten und auf Systemdateien zugreifen.

Eine Installation geht tief ins System, auch in die Registry. Wenn man da etwas falsch macht, kann man den Computer so beschädigen, dass Windows nicht mehr richtig startet und neu aufgesetzt werden muss.

> [!warning] Verantwortung
> Der Admin muss aufpassen, dass er seine Macht nicht missbraucht, denn er kann auch Systemfehler verursachen und grossen Schaden anrichten. Darum gilt das **Prinzip der minimalen Rechte**: Im Alltag arbeitet man als Standardbenutzer und gibt nur dann Adminrechte ein, wenn es wirklich nötig ist (die **Benutzerkontensteuerung/UAC** fragt dann nach).

## Die Windows-Registry
Die Registry ist eine **Datenbank**, in der Windows und die Programme ihre Einstellungen als Werte speichern. Bei jeder Installation einer Software wird dort etwas eingetragen oder geändert. Wenn man da selbst etwas falsch ändert, kann sehr viel schiefgehen. Deshalb sollte das nur der Admin machen (Tool: `regedit`, vorher am besten einen Wiederherstellungspunkt erstellen).

## Lokales Konto vs. Microsoft-Konto
Ein **Microsoft-Konto** läuft über Microsoft (Anmeldung mit E-Mail-Adresse), ein **lokales Konto** gibt es nur auf dem Rechner, der vor einem steht.

| | Lokales Konto | Microsoft-Konto |
|---|---|---|
| **Anmeldung** | Benutzername + Passwort/PIN | E-Mail-Adresse + Passwort/PIN |
| **Gespeichert** | nur auf diesem PC | online bei Microsoft |
| **Internet nötig** | nein | bei der ersten Anmeldung ja |
| **Synchronisierung** | keine | Einstellungen, OneDrive, Passwörter auf allen Geräten |
| **Passwort vergessen** | nur Sicherheitsfragen, sonst schwierig | online zurücksetzen |
| **Datenschutz** | mehr Kontrolle, weniger Daten an Microsoft | mehr Daten bei Microsoft |
| **Typisch für** | Firmen-PCs, Test-VMs, Offline-Geräte | private PCs |

> [!tip] In der Firma
> In Firmen meldet man sich meistens weder mit einem lokalen noch mit einem privaten Microsoft-Konto an, sondern mit einem **Firmenkonto** (Active Directory / Microsoft Entra ID), das zentral vom Admin verwaltet wird.

## Siehe auch
- [[Erweiterte Installationsoptionen – Imaging & Sysprep]]
- [[Betriebssysteme Übersicht]] (Kernaufgabe 6: Sicherheit & Rechteverwaltung)
