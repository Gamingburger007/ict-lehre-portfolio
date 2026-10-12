---
tags: [betriebssysteme, modul187, bios, uefi]
---

# Bootmanager, BIOS und UEFI

## Was passiert beim Starten?
Wenn wir den PC starten, startet zuerst das BIOS.
- **BIOS** = Basic Input Output System
- **POST** (Power On Self Test) passiert vor dem BIOS-Start
- Das BIOS ist das **erste Programm**, das startet, wenn man den PC anmacht – gesteuert vom BIOS-Chip
- Das BIOS-Programm prüft die Existenz von CPU, RAM und Tastatur
- Das BIOS ist in einem Chip gespeichert
- BIOS ist von 1975, veraltet, und das Original ist proprietär

## UEFI
- **UEFI** = Unified Extensible Firmware Interface
- Kann mehr Discspace (Festplattenspeicher) ansprechen
- Kann sich selbst reparieren, wenn es einen Fehler hat
- Wird von einem **Consortium** verwaltet (eine Gruppe verschiedener Firmen, die sich zusammengeschlossen haben)
- **Interface** ist eine Schnittstelle zwischen 2 Dingen
- Kann bis zu 5 PB (Petabyte) ansprechen
- MBR ist BIOS, **GPT ist UEFI**
- BIOS kann maximal 4 verschiedene Partitionssysteme haben, mit UEFI sind es 128

## Bootvorgang
- **BOOT** kommt vom Wort "boot strapping", heisst starten
- Der **Bootloader** ist das Programm, das den Boot startet
- **Bootreihenfolge** ist wichtig, falls man z. B. 5 Betriebssysteme auf der SSD hat, damit das BIOS weiss, was es starten soll

## Automatisierte Installation im Überblick
- **Imaging**: fertiges Systemabbild auf mehrere Geräte übertragen
- **Antwortdateien**: vordefinierte Installationsantworten
- Werkzeuge: **MDT, Windows Autopilot, PXE-Boot-Server**
- Eine XML-Datei ist ähnlich wie ein Programmcode aufgebaut
- **PXE** ist die Umgebung, in der das BIOS läuft (Netzwerk-Boot)

## Secure Boot
- Verhindert das Laden von nicht signierten Bootloadern
- Schutz vor Boot-Level-Malware/Rootkits
- Ein **signiertes Programm** ist ein unterschriebenes Programm
- **Malware** ist Schadsoftware

## Virtualisierung & Partitionierung
- Virtualisierung ist etwas, das auf Hardware läuft, auf der Software laufen soll.
- Ein **Hypervisor** ist eine Software, die virtualisiert (siehe auch [[Virtualisierung & VM-Netzwerke]])
- **Partitionierung**: Eine physische Festplatte wird in mehrere logisch getrennte Bereiche aufgeteilt
- Das Betriebssystem kann überall auf dem Rechner liegen – es gibt einen Unterschied zwischen logisch getrennt und physisch getrennt
- Partitionierung ist auch sicherer bei Updates

### Dateisysteme
- **NTFS** – Windows
- **ext4** – Linux
- **APFS** – das System von Apple
- Es sind Dateisysteme, die mit unterschiedlicher Kryptografie funktionieren

## Schnittstellen für Peripheriegeräte
Wir schauen uns gängige Schnittstellen für Peripheriegeräte an und benennen und lernen diese zu unterscheiden:

| Schnittstelle | Bemerkung |
|---|---|
| USB | |
| HDMI | |
| DP (DisplayPort) | |
| Bluetooth | |
| Netzwerk | |
| MagSafe 3 | |
| TRS | Klinke |
| RJ45 | Netzwerk-Stecker |
| VGA | |
| DVI-D | |
| Thunderbolt | |

Wir brauchen eine **Netzwerkkarte**, damit man sich mit dem Internet verbinden kann. Sie liegt auf dem Mainboard, wird zum Teil von der UEFI angesprochen. **NIC** = Network Interface Controller.

## Siehe auch
- [[Betriebssysteme Übersicht]]
- [[Virtualisierung & VM-Netzwerke]]
- [[Lizenzierung – OEM, Retail, KMS, MAK]]
