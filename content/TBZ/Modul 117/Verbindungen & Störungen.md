---
tags: [netzwerk, modul117, stoerungen, daempfung, fehlersuche]
quelle: M117 W03 Folien «Verbindungen & Störungen», Nachschlagewerk Kap. 2.1–2.2, Skript Kap. 3 und 6
---

# Verbindungen & Störungen

## Grundbegriffe der Datenübertragung
- **Sinussignal**: Grundform jeder Schwingung. Es hat eine **Amplitude** (Ausschlag = Stärke) und eine **Periode** (Länge).
- **Frequenz** = Anzahl Schwingungen pro Sekunde, Einheit **Hertz (Hz)**. Je höher die Frequenz, desto **kürzer die Wellenlänge** und desto mehr Kanäle stehen zur Verfügung, aber man braucht mehr Sendeleistung oder hat weniger Reichweite (wichtig bei WLAN).
- **Digitale Übertragung**: nur zwei Zustände (0/1, Strom/kein Strom).
- **Abtastrate (Sampling Rate)**: Anzahl Messwerte pro Sekunde beim Digitalisieren.

## Die zwei Hauptstörungen

### 1. Dämpfung (Attenuation)
- Das Signal wird auf dem Weg **schwächer** (Widerstand des Mediums). Je länger die Strecke, desto schwächer.
- Angabe in **Dezibel (dB)**: 0 dB = verlustfrei, **negativ = Dämpfung**, positiv = Verstärkung.
- Darum gibt es **maximale Kabellängen** (TP: 100 m) und **Repeater**.

### 2. Elektromagnetische Störungen
- **Magnetfelder** (Starkstromleitungen, Motoren, Leuchtstoffröhren) stören Kupferkabel.
- Gegenmittel:
  - **Verdrillen** der Adernpaare (Twisted Pair)
  - **Abschirmung** (STP, S/FTP): Ferromagnetisches Material lenkt die Feldlinien um, im Inneren entsteht ein fast **feldfreier Raum** (Schirm muss geerdet sein)
  - **Glasfaser**: überträgt Licht, ist komplett **unempfindlich** gegen EM-Störungen

## Störungen bei Glasfaser
- zu kleiner **Biegeradius** (Faser bricht oder Licht tritt aus)
- **Multimode**: Licht nimmt verschiedene Wege, das Signal wird verschmiert → kürzere Reichweite als **Singlemode** (siehe [[Kabel, Stecker & Ethernet-Varianten#Lichtwellenleiter (LWL, Glasfaser, Fiber)]])
- verschmutzte Stecker

## Störungen bei WLAN
- **Signalverlust durch Entfernung und Hindernisse** (Wände, Beton, Metallregale, Wasser)
- **Kanalüberlappung** mit anderen APs (z. B. im Mietshaus)
- Funkübertragung nutzt mehrere Medien hintereinander (Kabel → AP → Luft → Gerät), jede Stelle kann stören
- **Infrastruktur-Modus**: Geräte verbinden sich über einen AP mit dem Kabelnetz
- Details: [[WLAN-Standards]]

## Störungen bei PowerLAN
Signale laufen über die Stromleitung → **Dimmer, Netzteile** und andere Geräte dämpfen stark.

## Typische Fehler im Netzwerk (Symptom → Ursache)

> [!warning] Zuerst die Kabel prüfen!
> Laut Studien hängen **ca. 60 % aller Netzausfälle mit Steckern und schlechten Kabeln** zusammen. Darum den Fehler zuerst bei Dosen, Patchpanel und Kabeln suchen, nicht bei den Servern.

| Symptom | Mögliche Ursache | Prüfen mit |
|---|---|---|
| Link Light aus | Kabel defekt / nicht gesteckt, Port aus, NIC deaktiviert | Kabeltester, anderer Port |
| Langsame Verbindung | gequetschtes/zu stark gebogenes Kabel, falsche Kategorie, Duplex-Fehler, Hub statt Switch | Link-Rate prüfen, Kabeltester |
| IP `169.254.x.x` (APIPA) | **kein DHCP-Server erreichbar** | `ipconfig`, DHCP prüfen |
| Ping zu PC im gleichen Netz geht nicht | **Firewall blockiert ICMP**, falsche Subnetzmaske, falsches Subnetz | `ipconfig`, Firewall-Regel |
| Lokales Netz geht, Internet nicht | **Standardgateway** falsch oder fehlt, Router/ISP down | `ping <Gateway>`, `tracert` |
| `ping 8.8.8.8` geht, `ping www.tbz.ch` nicht | **DNS** falsch oder fehlt | `nslookup` |
| Zeitweise Aussetzer, IP-Konflikt-Meldung | **doppelte IP-Adresse** | `arp -a`, IP-Konzept |
| Freigabe nicht erreichbar | Netzwerkprofil «Öffentlich», Firewall, falsche Rechte | Netzwerkprofil, `net share` |
| WLAN schwach | Distanz, Hindernisse, Kanalüberlappung | WiFi Analyzer |

Befehle dazu: [[Netzwerk konfigurieren & testen (Befehle)]]

## Siehe auch
- [[Netzwerk testen – Testkonzept & Sicherheit]]
- [[Kabel, Stecker & Ethernet-Varianten]]
- [[Universelle Gebäudeverkabelung (UGV)]]
