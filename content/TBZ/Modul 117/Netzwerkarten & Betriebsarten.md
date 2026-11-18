---
tags: [netzwerk, modul117, lan, wan, peer-to-peer, client-server]
quelle: M117 W03 Folien «Architekturen» und «Betriebsarten», Nachschlagewerk Kap. 1.1–1.2
---

# Netzwerkarten (PAN bis GAN) & Betriebsarten

> [!quote] Was ist ein Netzwerk?
> Eine Anzahl voneinander entfernter, intelligenter Maschinen, die über Kommunikationsleitungen verbunden sind und an denselben Daten und Informationen teilhaben.

Hauptthemen eines Netzwerks: **Elemente** (was gehört dazu, wie gross?) · **Modell/Topologie** (wie gebaut?) · **Dienste** · **Leistung** (Übertragungsrate, Anzahl Hosts) · **Management** (wie verwaltet?)

## Netzwerkarten nach Grösse

```mermaid
graph LR
    BAN["BAN<br/>Körper"] --> PAN["PAN<br/>wenige Meter"] --> LAN["LAN<br/>Büro / Gebäude"] --> CAN["CAN<br/>Firmengelände"] --> MAN["MAN<br/>Stadt / Region"] --> WAN["WAN<br/>Länder"] --> GAN["GAN<br/>weltweit"]
```

| Art | Bedeutung | Beschreibung |
|---|---|---|
| **BAN / WBAN** | Body Area Network | am Körper, z. B. Gesundheitsüberwachung |
| **PAN / WPAN** | Personal Area Network | wenige Meter um eine Person. **Piconet** = Geräte per Bluetooth verbunden |
| **LAN / WLAN** | Local Area Network | alle lokalen Geräte (PC, Drucker, Server, Smartphone), **ohne öffentliche Übertragungsdienste**, meist ein Büro/Gebäude |
| **CAN** | Campus Area Network | mehrere Gebäude auf dem **eigenen Firmengelände**, private Leitungen, gehört einer Firma |
| **MAN** | Metropolitan Area Network | Filialen und Hauptsitz einer **regionalen** Firma/Verwaltung (verschmilzt heute mit WAN) |
| **WAN** | Wide Area Network | Standorte z. B. **europaweit**, Provider verkauft Nutzung |
| **GAN** | Global Area Network | **weltweit** verteilte Standorte, z. B. Satellit. **Das Internet gilt als GAN.** |

### PAN-Technologien
- **Drahtgebunden:** USB, Thunderbolt, Ethernet
- **Drahtlos (Reichweite):** NFC bis 5 cm · IrDA bis 10 cm · Bluetooth bis 20 m · Wi-Fi ad hoc bis 20 m · ANT+ bis 30 m · WHDI bis 30 m · ZigBee / Z-Wave (Hausautomation) bis 100 m

### LAN-Übertragungsraten (Nachschlagewerk)
- Wi-Fi: ca. 300 Mbit/s (abhängig von Standard, Anzahl Teilnehmer, Distanz)
- Twisted Pair: 100 Mbit/s oder 1 Gbit/s, **max. 100 m** Switch ↔ Endgerät
- Glasfaser: 1 Gbit/s bis 500 m (und mehr, je nach Typ)

### Vergleich

| Kriterium | WAN | MAN | CAN | LAN | PAN |
|---|---|---|---|---|---|
| Kosten | am grössten | sehr gross | sehr gross | klein | sehr klein |
| Grösse | am grössten | sehr gross | sehr gross | klein–mittel | sehr klein |
| Geschwindigkeit | schnell | sehr schnell | sehr schnell | **am schnellsten** | schnell–mittel |
| Medium | Glasfaser, Funk, Satellit | TP, Glasfaser | TP, Glasfaser | TP | Bluetooth, USB, IR |
| Anzahl Geräte | Millionen | Tausende | Tausende | Hunderte | Zehner |

## Betriebsarten: Peer-to-Peer vs. Client-Server

![[peer-to-peer-vs-client-server.png]]

| | **Peer-to-Peer** (Arbeitsgruppe) | **Client-Server** (Domäne) |
|---|---|---|
| Benutzerverwaltung | **auf jedem PC lokal** (Benutzer, Gruppen, Passwörter) | **zentral auf dem Server** (z. B. Active Directory) |
| Alle PCs | gleichberechtigt, jeder kann Dienste anbieten | Server bietet Dienste, Clients nutzen sie |
| Vorteil | einfach, günstig, kein Server nötig | zentrale Verwaltung, sicherer, skaliert gut |
| Nachteil | jede Änderung auf **jedem PC** einzeln, unübersichtlich ab ca. 10 PCs | Server kostet, braucht Know-how |
| Geeignet für | kleine Netze | ab mittleren Firmen |

> [!important] Modul 117 = Peer-to-Peer
> Das Modul verlangt ein **lokales Netzwerk ohne zentrale Benutzerverwaltung**. Darum werden Benutzer und Gruppen auf jedem PC **einzeln** angelegt (Arbeitsgruppe, z. B. `SOTA`). Siehe [[Benutzer, Gruppen & Berechtigungen]] und [[LB3 – Projekt Sota GmbH]].
> In der Praxis stösst man damit schnell an Grenzen, darum setzt man oft doch einen Windows- oder Linux-Server ein.

## Siehe auch
- [[Netzwerktopologien]]
- [[Netzwerk Grundlagen]]
