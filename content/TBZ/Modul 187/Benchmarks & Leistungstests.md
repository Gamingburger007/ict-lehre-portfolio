---
tags: [betriebssysteme, modul187, hardware, benchmark]
datum: 04.11.2026
---

# Benchmarks und Leistungstests

## Was ist ein Benchmark?
Ein Benchmark ist ein **standardisierter Test**, der einen **Messwert** liefert. Weil alle Geräte genau den gleichen Test machen, kann man die Ergebnisse **geräteübergreifend** mit anderen PCs vergleichen, um z. B. **Fehler** zu finden.

## CPU-Benchmarks: Single-Core und Multi-Core
Es gibt **Single-Core**- und **Multi-Core**-Tests (z. B. mit Cinebench oder Geekbench):
- **Single-Core:** Nur ein Kern arbeitet. Wichtig für Programme, die nur einen Kern nutzen (viele Spiele, Office).
- **Multi-Core:** Alle Kerne arbeiten gleichzeitig. Wichtig für Rendern, Videos umwandeln, Kompilieren.

Das Ergebnis bekommt man dann in **Punkten** und kann es in einer Wertetabelle mit **ähnlichen Geräten** mit **ähnlichen Spezifikationen** vergleichen. Mehr Punkte heisst schneller.

![[benchmark-vergleich.svg]]

## Speicher-Benchmark: CrystalDiskMark
**CrystalDiskMark** misst die **Schreib- und Lesegeschwindigkeit** eines Speichers (HDD, SSD, NVMe).
- **SEQ (sequenziell):** grosse, **zusammenhängende** Dateien werden am Stück gelesen bzw. geschrieben. Gibt die höchsten Werte.
- **RND4K (zufällig):** viele **kleine 4-KB-Blöcke**, die verstreut auf dem Speicher liegen. Die Werte sind viel tiefer, zeigen aber besser, wie schnell sich das System im Alltag anfühlt (Windows starten, Programme öffnen).
- Die Angabe ist in **MB/s** (Megabyte pro Sekunde). **Read** = lesen, **Write** = schreiben.

![[sequenziell-vs-zufaellig.svg]]

> [!tip] Nicht verwechseln
> **CrystalDiskMark** misst die **Geschwindigkeit**, **CrystalDiskInfo** zeigt den **Zustand** der Festplatte (S.M.A.R.T.-Werte), siehe [[Hardware-Komponenten & Funktionstests]].

## Gründe für Abweichungen
Ist ein Ergebnis deutlich schlechter als bei gleichen Geräten, können das Gründe sein:

| Grund | Was passiert? |
|---|---|
| **Thermal Throttling** | Die CPU oder GPU wird zu heiss und senkt ihren Takt, um sich zu schützen. Z. B. wegen Staub oder schlechter Wärmeleitpaste |
| **Treiberprobleme** | Veraltete oder falsche Treiber (Chipsatz, Grafik, Speicher-Controller) |
| **Hintergrundlast** | Andere Programme laufen nebenbei (Updates, Virenscan) und nehmen Leistung weg |
| **Fehlkonfiguration** | Falsche Einstellungen, z. B. Energiesparmodus aktiv, RAM nur im Single-Channel oder XMP/EXPO im BIOS nicht aktiviert |

> [!note] Fair testen
> Vor dem Benchmark alle unnötigen Programme schliessen, Höchstleistungs-Energieplan wählen und den Test **mehrmals** laufen lassen. Erst dann vergleichen.

## Siehe auch
- [[Hardware-Komponenten & Funktionstests]]
- [[BIOS & UEFI]]
