---
tags: [modul117, mathematik, zahlensysteme, binaer, hexadezimal]
quelle: M117 W02 Mathematische Grundlagen (Theorie Mathematik, Aufgaben Mathematik 1 + Lösungen, Umrechnungen, Binär mit den Händen zählen, edubs.ch), W03 Zahlensystem-Blätter, Nachschlagewerk Anhang
---

# Zahlensysteme – Binär, Dezimal, Hexadezimal

> [!info] Warum braucht man das?
> Router «verstehen» nur **binär**. IP-Adressen und Subnetzmasken rechnet man deshalb binär (→ [[IP-Adressierung & Subnetting]]). **MAC-Adressen** und **IPv6** schreibt man in **Hex**.

## Die drei Systeme

| | Dezimal (10) | Binär / Dual (2) | Hexadezimal (16) |
|---|---|---|---|
| **Basis** | 10 | 2 | 16 |
| **Ziffern** | 0–9 | 0, 1 | 0–9, **A=10, B=11, C=12, D=13, E=14, F=15** |
| **Stellenwerte** | …1000, 100, 10, 1 | …16, 8, 4, 2, 1 | …4096, 256, 16, 1 |
| Schreibweise | 13₁₀, 13d | 1101₂, 1101b | D₁₆, 0xD, D HEX |

**Prinzip (Stellenwertsystem):** Jede Ziffer hat einen **Ziffernwert** (ihre Form) und einen **Stellenwert** (ihren Platz). Wert = Ziffer × Basis^Position, alles addieren.

- Dezimal: `4627 = 4·10³ + 6·10² + 2·10¹ + 7·10⁰ = 4000 + 600 + 20 + 7`
- Binär: `1101 = 1·2³ + 1·2² + 0·2¹ + 1·2⁰ = 8 + 4 + 0 + 1 = 13`
- Hex: `2C7 = 2·16² + 12·16¹ + 7·16⁰ = 512 + 192 + 7 = 711`

## Die wichtigste Tabelle: ein Oktett (8 Bit)

| 2⁷ | 2⁶ | 2⁵ | 2⁴ | 2³ | 2² | 2¹ | 2⁰ |
|---|---|---|---|---|---|---|---|
| **128** | **64** | **32** | **16** | **8** | **4** | **2** | **1** |

> [!tip] Auswendig lernen
> **128 – 64 – 32 – 16 – 8 – 4 – 2 – 1** (Summe = **255**). Jede Stelle links hat den **doppelten** Wert.
> Typische Werte in Subnetzmasken: 128, **192**, **224**, **240**, **248**, **252**, **254**, **255**.

## Umrechnen: Binär → Dezimal
Werte aller Stellen mit einer **1** zusammenzählen.

`1100 0000` → 128 + 64 = **192**
`1010 1000` → 128 + 32 + 8 = **168**
`1001 0011` → 128 + 16 + 2 + 1 = **147**

## Umrechnen: Dezimal → Binär

**Methode 1: Subtrahieren (schnell für Oktette)**
Von links: Passt der Stellenwert hinein? → 1 schreiben und abziehen, sonst 0.

Beispiel **172**: 172−128 = 44 → 1 · 64 passt nicht → 0 · 32 passt (44−32=12) → 1 · 16 nein → 0 · 8 ja (12−8=4) → 1 · 4 ja (0) → 1 · 2 → 0 · 1 → 0
→ **172 = 1010 1100**

**Methode 2: Fortgesetzte Division durch 2** (Reste von unten nach oben lesen)

| Rechnung | Rest |
|---|---|
| 150 : 2 = 75 | 0 (1er) |
| 75 : 2 = 37 | 1 (2er) |
| 37 : 2 = 18 | 1 (4er) |
| 18 : 2 = 9 | 0 (8er) |
| 9 : 2 = 4 | 1 (16er) |
| 4 : 2 = 2 | 0 (32er) |
| 2 : 2 = 1 | 0 (64er) |
| 1 : 2 = 0 | 1 (128er) |

→ **150 = 1001 0110**

## Binär ↔ Hex (Vierergruppen)
Weil **2⁴ = 16** ist, steckt das Binärsystem «exakt» im Hexsystem: **4 Bit = 1 Hex-Ziffer** (ein «Nibble»).

- Binär → Hex: von rechts in **Vierergruppen** teilen, jede Gruppe umwandeln
  `0101 1011 1100 0010` → 5 B C 2 → **5BC2**
- Hex → Binär: jede Hex-Ziffer durch 4 Bit ersetzen
  `37F9` → 0011 0111 1111 1001

| Dez | Hex | Bin | | Dez | Hex | Bin |
|---|---|---|---|---|---|---|
| 0 | 0 | 0000 | | 8 | 8 | 1000 |
| 1 | 1 | 0001 | | 9 | 9 | 1001 |
| 2 | 2 | 0010 | | 10 | **A** | 1010 |
| 3 | 3 | 0011 | | 11 | **B** | 1011 |
| 4 | 4 | 0100 | | 12 | **C** | 1100 |
| 5 | 5 | 0101 | | 13 | **D** | 1101 |
| 6 | 6 | 0110 | | 14 | **E** | 1110 |
| 7 | 7 | 0111 | | 15 | **F** | 1111 |

## Dezimal ↔ Hex
**Dezimal → Hex:** fortgesetzt durch 16 teilen, Reste von unten lesen.
`1238 : 16 = 77 Rest 6` · `77 : 16 = 4 Rest 13 (D)` · `4 : 16 = 0 Rest 4` → **4D6**

**Hex → Dezimal:** Ziffer × Stellenwert.
`A5 = 10·16 + 5 = 165` · `C2 = 12·16 + 2 = 194`

**Abkürzung über 2 Hex-Ziffern (1 Byte):** `1001 0011` = (9)·16 + (3) = 147 = **93 HEX**

## Grössen und Vorsätze

| Dezimal (SI) | Wert | | Binär (IEC) | Wert |
|---|---|---|---|---|
| Kilo (k) | 10³ = 1'000 | | Kibi (Ki) | 2¹⁰ = 1'024 |
| Mega (M) | 10⁶ | | Mebi (Mi) | 2²⁰ = 1'048'576 |
| Giga (G) | 10⁹ | | Gibi (Gi) | 2³⁰ = 1'073'741'824 |
| Tera (T) | 10¹² | | Tebi (Ti) | 2⁴⁰ |
| Peta, Exa, Zetta, Yotta | 10¹⁵ … 10²⁴ | | | |

**Bit und Byte:** 1 Bit = 0 oder 1 (kleinste Einheit, «binary digit») · **1 Byte = 8 Bit** = 2⁸ = **256** Möglichkeiten (0–255) · ASCII nutzt 7 Bit = 128 Zeichen, «A» = `0100 0001`.

**Anzahl Bits → Anzahl Zustände: 2ⁿ**

| Bits | 1 | 4 | 5 | 8 | 10 | 16 | 24 | 32 |
|---|---|---|---|---|---|---|---|---|
| Zustände | 2 | 16 | 32 | 256 | 1'024 | 65'536 | 16,7 Mio. | 4,29 Mrd. |
| Höchste Zahl | 1 | 15 (F) | 31 | 255 (FF) | 1'023 | 65'535 (FFFF) | | 4'294'967'295 |

> **Mit 10 Fingern binär zählen:** Jeder Finger ist ein Bit (1, 2, 4, 8, 16 an der einen Hand, 32 … 512 an der anderen) → bis **1023** zählen.

## Rechnen im Binärsystem
- **Addition** wie gewohnt, aber **Übertrag schon bei 2** (weil 2 = 10₂): `1 + 1 = 10`, `1 + 1 + 1 = 11`
- Beispiel: `10101 + 11110 = 110011` (21 + 30 = 51 ✓)
- Multiplikation, Subtraktion und Division funktionieren auch, sind aber ungewohnt.

## Übungen mit Lösungen

> [!example]- Binär → Dezimal (W03-Blatt)
> | Binär | Dezimal |
> |---|---|
> | 0100 | 4 |
> | 1111 1111 | 255 |
> | 1111 0000 | 240 |
> | 100 0001 | 65 |
> | 10 1000 | 40 |
> | 1100 0000 | 192 |
> | 1010 1010 | 170 |
> | 1010 1100 | 172 |
> | 1010 1001 | 169 |
> | 1010 1000 | 168 |
> | 1111, 10001, 101010, 101, 1000000, 111111 | 15, 17, 42, 5, 64, 63 |

> [!example]- Dezimal → Binär
> | Dezimal | Binär |
> |---|---|
> | 4 | 100 |
> | 13 | 1101 |
> | 20 | 1 0100 |
> | 34 | 10 0010 |
> | 60 | 11 1100 |
> | 127 | 111 1111 |
> | 128 | 1000 0000 |
> | 1024 | 100 0000 0000 |
> | 2016 | 111 1110 0000 |

> [!example]- Hex ↔ Dezimal
> | Aufgabe | Lösung |
> |---|---|
> | A, F, C2, A8, C0 (hex → dez) | 10, 15, 194, 168, 192 |
> | 16, 172, 220 (dez → hex) | 10, AC, DC |
> | 72, B3, 6E, D9 (hex → dez) | 114, 179, 110, 217 |
> | FA18, 6BAC (hex → dez) | 64'024, 27'564 |
> | 133, 179, 212, 108 (dez → hex) | 85, B3, D4, 6C |
> | 32'673, 37'090 (dez → hex) | 7FA1, 90E2 |
> | 1100 0110, 0101 1010, 0100 1111 (bin → hex/dez) | C6 = 198, 5A = 90, 4F = 79 |
> | 1110 0111, 0010 1011, 1101 0000 | E7 = 231, 2B = 43, D0 = 208 |
> | 1000 = ? | 0000 0011 1110 1000 = 03E8 |
> | 43'981 = ? | 1010 1011 1100 1101 = ABCD |

> [!example]- IP-Adresse und Farben (Mathematik 1, Aufgaben 14–15)
> **IP 164.2.100.4** → hex `A4.02.64.04` → binär `1010 0100 . 0000 0010 . 0110 0100 . 0000 0100`
> **Wie viele Adressen liegen zwischen 164.2.100.4 und 164.2.120.15** (Grenzen nicht mitgezählt)?
> Nur die letzten zwei Oktette unterscheiden sich: 100·256 + 4 = 25'604 und 120·256 + 15 = 30'735. Differenz 5'131, minus 1 → **5'130 Adressen**.
> **RGB-Farbe** R 131, G 53, B 173 → hex `83 35 AD` → binär `1000 0011 · 0011 0101 · 1010 1101` (24 Bit)

> [!example]- Weiterzählen
> 0101 → 0110, 0111, 1000, 1001 · 1011 → 1100, 1101, 1110, 1111 · A9D → A9E, A9F, AA0, AA1 · 4FE → 4FF, 500, 501, 502

## Online-Hilfen aus Teams
- Umrechner: arndt-bruenner.de/mathe/scripts/Zahlensysteme.htm
- Übungen: gut-erklaert.de (Binärzahlen), serlo.org (Zahlensysteme), burgnetz.de (Dual & Hex)

## Siehe auch
- [[IP-Adressierung & Subnetting]]
- [[IP-Berechnungen – Übungen mit Lösungen]]
