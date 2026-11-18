---
tags: [modul117, ip-adressierung, uebungen, pruefungsvorbereitung]
quelle: M117 W02 «IP Berechnungen» (Formular + Musterlösung), W02 Theorie Aufgabe 6, W11 «Repetition IP-Adressierung» (Formular + Musterlösung)
---

# IP-Berechnungen – Übungen mit Lösungen

> [!info] Lernziel
> Sämtliche Berechnungen mit IP-Adressen beherrschen und binär ↔ dezimal sicher umrechnen. Theorie: [[IP-Adressierung & Subnetting]] und [[Zahlensysteme – Binär, Dezimal, Hexadezimal]].

## Das Rezept

> [!abstract] In 5 Schritten
> 1. **Maske** binär aufschreiben (Suffix /n = n Einsen von links).
> 2. **Netzadresse** = alle **Host-Bits auf 0** (logisches UND von IP und Maske).
> 3. **Broadcast** = alle **Host-Bits auf 1**.
> 4. **Erster Host** = Netzadresse + 1, **letzter Host** = Broadcast − 1.
> 5. **Anzahl Hosts** = 2^(Host-Bits) − 2 (Netz- und Broadcast-Adresse sind reserviert).

### Spickzettel /24 bis /30

| Suffix | Maske (letztes Oktett) | Host-Bits | Adressen | **nutzbare Hosts** |
|---|---|---|---|---|
| /24 | 255.255.255.**0** | 8 | 256 | **254** |
| /25 | 255.255.255.**128** | 7 | 128 | **126** |
| /26 | 255.255.255.**192** | 6 | 64 | **62** |
| /27 | 255.255.255.**224** | 5 | 32 | **30** |
| /28 | 255.255.255.**240** | 4 | 16 | **14** |
| /29 | 255.255.255.**248** | 3 | 8 | **6** |
| /30 | 255.255.255.**252** | 2 | 4 | **2** |

Grössere Netze: /16 = 255.255.0.0 (65'534 Hosts) · /8 = 255.0.0.0 (16'777'214 Hosts) · /21 = 255.255.248.0 · /12 = 255.240.0.0

> [!example] Durchgerechnet: `192.168.10.77/27`
> - Maske: /27 → 255.255.255.**224** → im letzten Oktett 3 Netz-Bits, **5 Host-Bits**
> - 77 binär = `010 01101` → Netzteil `010` = 64
> - **Netz:** 192.168.10.**64** · **Broadcast:** 64 + 31 = 192.168.10.**95**
> - **Hosts:** .65 bis .94 → **30** nutzbare Adressen

## Aufgabe 1 (W02): Binär ↔ dezimal, Klasse, privat?

| IP binär | Maske binär | IP dezimal | Maske | Klasse | Privat? |
|---|---|---|---|---|---|
| 10000100.01111110.00100001.00010101 | 11111111.11111111.00000000.00000000 | 132.126.33.21 | 255.255.0.0 | B | nein |
| 00001010.00001100.00000010.01101000 | 11111111.00000000.00000000.00000000 | 10.12.2.104 | 255.0.0.0 | A | **ja** |
| 11000011.10111010.00001010.11101010 | 11111111.11111111.11111111.00000000 | 195.186.10.234 | 255.255.255.0 | C | nein |
| 11000000.10101000.00000000.01101000 | 11111111.11111111.11111111.00000000 | 192.168.0.104 | 255.255.255.0 | C | **ja** |
| 01101101.00001011.01100111.01010010 | 11111111.00000000.00000000.00000000 | 109.11.103.82 | 255.0.0.0 | A | nein |
| 10101100.00010011.01111011.01001010 | 11111111.11111111.00000000.00000000 | 172.19.123.74 | 255.255.0.0 | B | **ja** |
| 00001010.01110001.00110110.00111110 | 11111111.00000000.00000000.00000000 | 10.113.54.62 | 255.0.0.0 | A | **ja** |
| 01011000.10110010.00010001.00100010 | 11111111.00000000.00000000.00000000 | 88.178.17.34 | 255.0.0.0 | A | nein |
| 00001010.00000001.11010011.11001011 | 11111111.00000000.00000000.00000000 | 10.1.211.203 | 255.0.0.0 | A | **ja** |
| 10111100.00000001.11010011.11001011 | 11111111.11111111.00000000.00000000 | 188.1.211.203 | 255.255.0.0 | B | nein |

## Aufgabe 2 (W02): Klasse, Netz, Maske, Broadcast

| IP-Adresse | Klasse | Netzwerkadresse | Standard-Maske | Broadcast |
|---|---|---|---|---|
| 122.1.113.98 | A | 122.0.0.0 | 255.0.0.0 | 122.255.255.255 |
| 222.2.2.22 | C | 222.2.2.0 | 255.255.255.0 | 222.2.2.255 |
| 191.1.66.80 | B | 191.1.0.0 | 255.255.0.0 | 191.1.255.255 |
| 9.33.43.0 | A | 9.0.0.0 | 255.0.0.0 | 9.255.255.255 |
| 192.168.111.155 | C **privat** | 192.168.111.0 | 255.255.255.0 | 192.168.111.255 |
| 192.1.1.1 | C | 192.1.1.0 | 255.255.255.0 | 192.1.1.255 |
| 172.17.17.254 | B **privat** | 172.17.0.0 | 255.255.0.0 | 172.17.255.255 |
| 10.33.43.0 | A **privat** | 10.0.0.0 | 255.0.0.0 | 10.255.255.255 |

Die **Hostadresse** ist jeweils die IP selbst (z. B. 122.1.113.98). Achtung: 9.33.43.0 und 10.33.43.0 enden zwar auf .0, sind in einem /8-Netz aber ganz normale Host-Adressen.

## Aufgabe 3 (W02): Welche Maske für n Geräte? (Bereich 192.168.0.0)
Rechnung: **Geräte + 2** (Netz + Broadcast) → auf die nächste **Zweierpotenz** aufrunden.

| Geräte | benötigt | Block | Maske | Suffix |
|---|---|---|---|---|
| 2 | 4 | 4 | 255.255.255.252 | /30 |
| 4 | 6 | 8 | 255.255.255.248 | /29 |
| 8 | 10 | 16 | 255.255.255.240 | /28 |
| 10 | 12 | 16 | 255.255.255.240 | /28 |
| 12 | 14 | 16 | 255.255.255.240 | /28 |
| 16 | 18 | 32 | 255.255.255.224 | /27 |
| 30 | 32 | 32 | 255.255.255.224 | /27 |
| 32 | 34 | 64 | 255.255.255.192 | /26 |
| 64 | 66 | 128 | 255.255.255.128 | /25 |
| 80 | 82 | 128 | 255.255.255.128 | /25 |
| 128 | 130 | 256 | 255.255.255.0 | /24 |
| 255 | 257 | 512 | **geht nicht** im 192.168.0.x-Bereich (max. 254 Geräte, sonst /23 nötig) | |

> [!warning] Typischer Fehler
> Bei **4 Geräten** reicht /30 **nicht** (nur 2 Hosts). Man braucht /29 (6 Hosts). Immer die **2 reservierten Adressen** mitrechnen!

## Aufgabe 6 (Theorie W02): Binär, Netzadresse, sinnvoller Suffix

| IP | Binär | Sinnvoller Suffix | Netzadresse |
|---|---|---|---|
| 192.168.22.34 | 11000000.10101000.00010110.00100010 | /24 (privat, Klasse C) | 192.168.22.0 |
| 170.23.213.224 | 10101010.00010111.11010101.11100000 | /16 (Klasse B) | 170.23.0.0 |
| 10.0.0.21 | 00001010.00000000.00000000.00010101 | /8 (privat, Klasse A) | 10.0.0.0 |
| 123.213.**256**.12 | – | **ungültig**: 256 > 255 | – |

## Repetition (W11)

**Aufgabe 1 – Was ist das?**
| Angabe | Bezeichnung |
|---|---|
| 255.255.0.0 | **Netzmaske** (/16, 65'536 Adressen) |
| 157.16.0.0 – 157.16.255.255 | **Adressbereich** des Netzes 157.16.0.0 |
| 202.33.89.8 | eine konkrete **Hostadresse** |
| 10.0.0.0 – 10.255.255.255 | Adressbereich des **privaten** Netzes 10.0.0.0 |
| mustergmbh.ch | **DNS-Name** (Domain) |

**Aufgabe 2 – Netz-ID und Host-ID**
| Gerät | IP / CIDR | Netz-ID | Host-ID |
|---|---|---|---|
| 1 | 177.77.117.17 /16 | 177.77 | 117.17 |
| 2 | 177.77.117.11 /24 | 177.77.117 | 11 |
| 3 | 17.77.117.17 /8 | 17 | 77.117.17 |
| 4 | 225.17.3.1 /16 | – | **225 ist Klasse D (Multicast)**, keine gültige Host-Adresse |
| 5 | 25.17.31.1 /24 | 25.17.31 | 1 |

> [!note] Abweichung in der Musterlösung
> Die Musterlösung rechnet mit leicht anderen Angaben (Gerät 2 /16, Gerät 4 = 172.17.3.1/24, Gerät 5 /8). Dort: Netz-ID 177.77 / 172.17.3 / 25, Host-ID 117.11 / 1 / 17.31.1. Der Rechenweg ist derselbe.

**Aufgabe 3 – Wer kann ohne Router kommunizieren?** → **Gerät 1 und 2** (beide im Netz 177.77.x.x, 177.77.117.17 liegt auch im /24 von Gerät 2).

**Aufgabe 4 – Gültig?**
| Adresse | Gültig? | Warum |
|---|---|---|
| 2.254.254.254 | ✅ IP | alle Oktette 0–255 |
| 222.22.222.2222 | ❌ | 2222 > 255 |
| 55.256.265.55 | ❌ | 256 und 265 > 255 |
| 1.17.1.7.17 | ❌ | 5 Oktette statt 4 |
| 10-45-7A-95-V1-22 | ❌ MAC | «V» ist keine Hex-Ziffer |
| 95-B1-6F-98-27-10-9D | ❌ MAC | 7 Bytes statt 6 (die Musterlösung zählt nur die ersten 6 → dann gültig) |
| 10010110.01100101 | ❌ | nur 16 Bit |
| 19.f3.35.16.1a | ❌ | nur 5 Bytes, gemischte Schreibweise |

**Aufgaben 5–7 – Private Bereiche:** Klasse C 192.168.0.0 – 192.168.255.255 · Klasse A 10.0.0.0 – 10.255.255.255 · Klasse B 172.16.0.0 – 172.31.255.255

**Aufgabe 8 – `ipconfig /all` lesen**
```
Host-Name . . . . . . : e48-03.tbz-au.ch
Physikalische Adresse : 00-30-05-4B-39-36
DHCP aktiviert. . . . : Nein
IP-Adresse. . . . . . : 192.168.37.133
Subnet Mask . . . . . : 255.255.255.0
Standard-Gateway. . . :            ← leer!
DNS-Server. . . . . . :            ← leer!
```
| Frage | Antwort |
|---|---|
| A) Hersteller-Teil der MAC | **00-30-05** (die ersten 3 Bytes / 24 Bit) |
| B) Host- und Netz-ID | Host **133**, Netz-ID **192.168.37** |
| C) Was ist speziell an der Netz-ID? | **privater** Adressbereich |
| D) `ping 192.168.37.254` geht, `ping 137.1.1.1` nicht | **kein Standardgateway** eingetragen → kein Weg in fremde Netze |
| E) `ping 192.168.37.254` geht, `ping www.tbz.ch` nicht | **kein DNS-Server** eingetragen → Name kann nicht aufgelöst werden |

## Aufgabe 5 (Skript): `ipconfig` am eigenen Rechner
1. IPv4-Adresse ablesen (z. B. 192.168.1.x zuhause, an der TBZ anders)
2. Vergeben hat sie der **DHCP-Server** (im Router)
3. Standardgateway = IP des Routers
4. DNS-Server mit `ipconfig /all`

## Siehe auch
- [[IP-Adressierung & Subnetting]]
- [[Zahlensysteme – Binär, Dezimal, Hexadezimal]]
- [[Netzwerk konfigurieren & testen (Befehle)]]
- [[Hausaufgabe 09.11. – IT-Dokumentation & Berechtigungs-Matrix#🔢 IP-Repetition]]
