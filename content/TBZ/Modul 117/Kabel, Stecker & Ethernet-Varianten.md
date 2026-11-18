---
tags: [netzwerk, modul117, kabel, ethernet, glasfaser]
quelle: M117 W03 Teilthema 2+3 (Kabel, Ethernetvarianten, Verkabelungsarten), Nachschlagewerk Kap. 2.3, Skript Kap. 2.7
---

# Kabel, Stecker & Ethernet-Varianten

## Ethernet
**Ethernet** ist die Technologie, um Daten in einem **LAN** (bis einige 100 m) zu übertragen. Es legt Kabel, Stecker **und** die Regeln der Kommunikation fest:
1. Wer darf wann senden? (damit nicht alle gleichzeitig senden → [[Netzwerkgeräte & Zugriffsverfahren#CSMA/CD]])
2. Beide Enden brauchen **dieselbe Geschwindigkeit**.
3. Bits werden in **Päckchen fester Grösse** (Frames) zusammengefasst.
4. Jede Station hat eine **Adresse** (MAC-Adresse).

- In den **70er-Jahren von Xerox** entwickelt. Konkurrent war **Token Ring** von IBM (heute praktisch weg).
- Heute in **> 99 % aller LANs** → das wichtigste LAN-Protokoll. Genormt in **IEEE 802.3**.

### Geschwindigkeiten heute
| Einsatz | Geschwindigkeit |
|---|---|
| normale PCs | 1 Gbit/s (1000 Mbit/s) |
| zwischen Switches, Server | 10 Gbit/s |
| Hochleistungsserver, Backbone grosser LANs | 100 Gbit/s |

> [!warning] Einheiten-Fallen
> - Übertragungsraten immer in **Bit/s** (Mbit/s, Mbps), nicht nur «Mbit».
> - **Bit ≠ Byte:** 8 Bit = 1 Byte. Eine 100-Mbit/s-Leitung schafft höchstens **12,5 MB/s**.
> - Die Rate ist nur die «Reisegeschwindigkeit» auf der Autobahn. Netzwerkkarte oder Festplatte können der Flaschenhals sein.

## Twisted-Pair-Kabel (TP)
Kupferkabel, bei dem **je zwei Adern verdrillt** sind (twisted = verdrillt), das verringert Störungen. **8 Adern = 4 Paare**.
- Bis **100 Mbit/s**: nur **2 Paare** (4 Adern) genutzt
- **Gigabit-Ethernet**: alle **4 Paare** (8 Adern)
- Max. Länge eines TP-Kabels bei Ethernet: **100 m**
- Stecker: **RJ45** (8 Pins)

### Draht vs. Litze

| | UGV-Kabel (fest verlegt) | Patchkabel (fliegend) |
|---|---|---|
| Leiter | **starrer, massiver Draht** | **Litze**: 20–40 feine verdrillte Kupferleiter |
| Eigenschaft | bleibt in Form, langlebig | weich, biegsam |
| Enden | **Buchse** in Dose / Patchpanel | **Stecker** (RJ45) |
| Kategorie heute | **Cat 6 und höher** | **Cat 5 und höher** |

### Geschirmt oder ungeschirmt?

| Typ | Bedeutung |
|---|---|
| **UTP** | Unshielded Twisted Pair, **nicht abgeschirmt** (günstiger, mechanisch robuster) |
| **STP** | Shielded Twisted Pair, **jedes Adernpaar abgeschirmt** (besser gegen Störungen) |
| **S/…** | **Screened**: Geflecht um das ganze Kabel |
| **F/…** | **Foiled**: Folie um das ganze Kabel |
| Beispiele | S/UTP, F/UTP, S/STP, **S/FTP** (Cat 7a) |

> [!important] Schirm muss geerdet sein
> Ein Schirm nützt nur, wenn er **geerdet** ist (über den **metallischen Steckermantel**). Sonst ist er im Extremfall schlechter als gar kein Schirm. STP-Kabel kauft man deshalb **fertig konfektioniert**.
> **Erkennen:** STP hat einen **silbernen Steckermantel**, ist dicker und weniger flexibel.

Im Modul 117 ist UTP vs. STP zweitrangig, man richtet sich nach dem Lehrbetrieb.

### Kabelkategorien
Die **Kategorie** gibt die **maximale Übertragungsfrequenz** an. Höher = schneller, aber teurer (Material, Verarbeitung, vor allem der Stecker).

| Kategorie | Max. Frequenz | Einsatz |
|---|---|---|
| Cat 1 | – | Telefon, Klingeldraht |
| Cat 2 | 1 MHz | Telefon |
| Cat 3 | 16 MHz | 10BaseT |
| Cat 4 | 20 MHz | Token Ring |
| Cat 5 | 100 MHz | 100BaseTX |
| Cat 5e | 100 MHz | 1000BaseT |
| **Cat 6** | **250 MHz** | 1000BaseT, Multimedia |
| **Cat 6a** | **500 MHz** | 10GBaseT auf 100 m (*augmented* = erweiterte Cat 6), im M187-Unterricht erwähnt |
| **Cat 7** | **600 MHz** | 10GBaseT |
| Cat 8 | 800 MHz (laut TBZ-Unterlage; nach Norm eigentlich 2000 MHz, 25/40 Gbit/s bis 30 m) | 10GBaseT, Kabel-TV |

> [!tip] Merksatz
> Heute: **Cat 5e und Cat 6**. Für **Neuinstallationen mindestens Cat 6, besser Cat 7**, dann ist man für die Zukunft gerüstet.

### Farbcodierung RJ45
Zwei Standards: **T568A** und **T568B** (T568B ist verbreiteter). Adern: Farbe X und Farbe X + weiss. Auf die richtige Lage von **Pin 1** achten.

| Pin | T568B | T568A |
|---|---|---|
| 1 | weiss-orange | weiss-grün |
| 2 | orange | grün |
| 3 | weiss-grün | weiss-orange |
| 4 | blau | blau |
| 5 | weiss-blau | weiss-blau |
| 6 | grün | orange |
| 7 | weiss-braun | weiss-braun |
| 8 | braun | braun |

## Lichtwellenleiter (LWL, Glasfaser, Fiber)
- Daten als **Lichtimpulse** durch eine sehr dünne Glasfaser (ca. 0,05 mm)
- **unempfindlich gegen elektromagnetische Störungen**
- Einsatz: bei EM-Störungen, **über 100 m**, **zwischen Gebäuden** (galvanische Trennung: bei Blitzschlag keine Überspannung ins andere Gebäude), explosionsgefährdete Zonen
- Früher schneller als Kupfer, heute schafft Kupfer ähnliche Raten.
- **Biegeradius** beachten: Patchkabel ca. **10×**, Installationskabel **20–25×** den Kabeldurchmesser. Auch Zug- und Druckbelastung einhalten.
- Stecker: **SC**, **ST** (und LC)

| | Multimode | Singlemode (Monomode) |
|---|---|---|
| Kern | dicker, Licht läuft auf vielen Wegen (Moden) | sehr dünn, Licht läuft fast gerade |
| Signal | wird «verschmiert» (Dispersion) | bleibt scharf |
| Reichweite | kürzer (einige 100 m) | sehr lang (km) |
| Beispiel | 1000BaseSX | 1000BaseLX, Primärbereich |

## Ethernet-Varianten

> [!tip] Name lesen: **1000 Base T**
> **1000** = Geschwindigkeit in Mbit/s · **Base** = Basisband · **T** = Twisted Pair (F/S/L = Glasfaser, S = short, L = long)

| Name | Geschwindigkeit | Kabel (min. Kategorie) | Max. Reichweite | Einsatz |
|---|---|---|---|---|
| 10BaseT | 10 Mbit/s | TP Cat 3 | 100 m | alte Geräte, Drucker |
| **100BaseTX** | 100 Mbit/s | TP Cat 5 | 100 m | Standard mit Switch, gutes Preis-Leistungs-Verhältnis |
| **100BaseFX** | 100 Mbit/s | Glasfaser | 2000 m | EM-Störungen, zwischen Gebäuden, Ex-Zonen |
| **1000BaseT** | 1 Gbit/s | TP Cat 5e, 4 Paare | 100 m | Server, zwischen Switches, Backbone |
| 1000BaseSX | 1 Gbit/s | Glasfaser (Multimode) | 270 / 550 m | Server, zwischen Switches |
| 1000BaseLX | 1 Gbit/s | Glasfaser | 550 / 5000 m | Langstrecken |
| **1000BaseFX** | 1 Gbit/s | Glasfaser | | (in den Handlungszielen erwähnt) |
| 10GBaseT | 10 Gbit/s | TP Cat 7, 4 Paare | 100 m | Server, Backbone |
| 10GBaseSR | 10 Gbit/s | Glasfaser | 300 m | Server, zwischen Switches |

### IEEE-802.3-Übersicht (Folie)

| Standard | Topologie | Segmentlänge |
|---|---|---|
| 802.3u (100BASE-T) | Stern | 100 m mit UTP |
| 802.3ab (1GBASE-T) | Stern | 100 m mit UTP |
| 802.3z (1GBASE-L/SX) | Stern | 5 km mit LWL |
| 802.3ae (10GBASE-L/SX) | Stern | 10 km mit LWL |

## Kabel prüfen
- **Kabeltester**: prüft, ob alle Adern richtig verbunden sind
- **Link Lights** (LEDs) an Netzwerkkarte und Switch: Verbindung da? Mit welcher Rate (100/1000 Mbit/s)?
- Brennt das Link Light nicht → Kabel mit dem Tester prüfen.

## Siehe auch
- [[Universelle Gebäudeverkabelung (UGV)]]
- [[Netzwerkgeräte & Zugriffsverfahren]]
- [[Verbindungen & Störungen]]
- [[WLAN-Standards]]
