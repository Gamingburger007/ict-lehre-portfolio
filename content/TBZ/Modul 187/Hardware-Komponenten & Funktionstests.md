---
tags: [betriebssysteme, modul187, hardware]
datum: 28.10.2026
---

# Hardware-Komponenten und Funktionstests

> [!note] Prüfung
> Alles aus dieser Lektion kommt **nicht an der Prüfung**. Wir haben in der Lektion auch den Test und die Prüfung besprochen, offene Fragen werden im Plenum geklärt.

## Lernziele
Nach dieser Lektion können wir:
- die Kernkomponenten eines ICT-Endgerätes benennen und deren Kennzahlen erläutern
- die Speichertechnologien HDD, SSD und NVMe nennen
- eine strukturierte Funktionsprüfung durchführen

## Warum Funktionstests?
**Problem:** Ein Gerät läuft, heisst nicht automatisch, dass alle Komponenten fehlerfrei sind.
- Eine **strukturierte Prüfung** jeder Komponente verhindert versteckte Mängel beim Kunden bzw. Endanwender.
- Tool zum Prüfen von Festplatten: **CrystalDiskInfo** (zeigt den Zustand über die S.M.A.R.T.-Werte).

## SI-Einheiten
Für Messungen werden standardisierte Einheiten genutzt, die **SI-Einheiten**:
- Grundeinheiten: **Meter** (m), **Kilogramm** (kg), **Sekunde** (s)
- Daraus abgeleitet: **Joule** (J, Energie) und **Watt** (W, Leistung = Joule pro Sekunde)

## CPU
- **Taktfrequenz** wird in **GHz** angegeben und sagt, wie viele Takte pro Sekunde ein Kern macht. **4,7 GHz** sind 4'700'000'000 Takte pro Sekunde.
- **Cache (L1/L2/L3)** ist ein sehr schneller Zwischenspeicher direkt in der CPU für Daten, die sie oft braucht. L1 ist am schnellsten und kleinsten, L3 am grössten.
- **TDP** = Thermal Design Power. Gibt an, wie viel Wärme (in Watt) der Kühler abführen können muss.

## Arbeitsspeicher und Grafik
- **RAM** gibt es im **Dual-Channel** und **Quad-Channel**. Mehr Kanäle heisst, die CPU kann gleichzeitig auf mehr Speicher zugreifen, also mehr Bandbreite.
- **VRAM** = Video Random Access Memory. Der eigene Speicher der **Grafikkarte**, z. B. für Bilder und Texturen, die auf dem Bildschirm angezeigt werden.

## Speichertechnologien
| Typ | Technik | Geschwindigkeit |
|---|---|---|
| **HDD** | mechanisch, drehende Magnetscheiben | langsam |
| **SSD** (SATA) | Flash-Speicher | schnell |
| **NVMe** | Flash-Speicher über PCIe | am schnellsten |

- Eine HDD kann durch **Stösse** (z. B. Herunterfallen im Betrieb) oder **starke Magnete** kaputtgehen bzw. Daten verlieren.
- Daten halten auf einer HDD nicht ewig. Man rechnet je nach Lagerung mit etwa **10 bis 20 Jahren**, darum macht man regelmässig Backups.

## SATA und ATA
- **ATA** = AT Attachment. **AT** steht für **Advanced Technology** (vom IBM PC/AT).
- **SATA** = Serial ATA. Das ist die physische Verbindung (Kabel und Anschluss) für HDDs und SATA-SSDs.
- **Seriell vs. parallel:** Parallel schickt mehrere Bits gleichzeitig über viele Leitungen, seriell nacheinander über wenige Leitungen. Früher war parallel (PATA) üblich. Bei hohen Geschwindigkeiten stören sich die vielen parallelen Leitungen aber gegenseitig. Darum ist das **serielle SATA heute schneller** und hat PATA ersetzt.

## Lizenzen
Lizenzarten MAK, KMS, Retail, Digital License und OEM: siehe [[Lizenzierung – OEM, Retail, KMS, MAK]].

## Siehe auch
- [[Benchmarks & Leistungstests]]
- [[BIOS & UEFI]]
- [[Betriebssysteme Übersicht]]
