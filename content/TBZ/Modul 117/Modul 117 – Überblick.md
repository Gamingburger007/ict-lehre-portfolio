---
tags: [modul117, uebersicht, netzwerk]
quelle: M117_00_b Modulidentifikation, M117_00_c Planung Unterricht, M117_00_d Termine, Teams-Kursmaterialien IT_ICT26c_M117 (Stand 09.11.2026)
---

# Modul 117 – Überblick

> [!abstract] Modul 117 in einem Satz
> **Informatik- und Netzinfrastruktur für ein kleines Unternehmen realisieren:** ein **lokales Netzwerk ohne zentrale Benutzerverwaltung** (bis ca. 10 Anschlüsse, mit Internet) planen, aufbauen, konfigurieren, Benutzer/Gruppen/Freigaben einrichten, testen und dokumentieren.
> Modulversion 5.0 (ICT-Berufsbildung Schweiz, publiziert 09.09.2025). Das Modul ist die **Basis für Modul 123**.

## 📚 Lernpfad – in dieser Reihenfolge lesen

| # | Woche | Notiz | Worum geht's |
|---|---|---|---|
| 1 | W01 | [[Anforderungen & Netzwerkdienste]] | Was braucht der Kunde? Dienste, intern/extern, Cloud |
| 2 | W01 | [[Netzwerk Grundlagen]] | Netzwerkkomponenten (Router, Firewall, DMZ, Switches, Server) |
| 3 | W01 | [[Logischer & physischer Netzwerkplan]] | Hierarchie, No-Gos, Beschriftung, Farben |
| 4 | W01 | [[OSI-Modell]] | 7 Schichten, Geräte und Protokolle, TCP/IP-Modell |
| 5 | W02 | [[Zahlensysteme – Binär, Dezimal, Hexadezimal]] | Umrechnen, Bit/Byte |
| 6 | W02 | [[IP-Adressierung & Subnetting]] | MAC, IPv4, Maske, CIDR, privat, NAT, IPv6 |
| 7 | W02 | [[IP-Berechnungen – Übungen mit Lösungen]] | alle Übungen und Repetition mit Lösungen |
| 8 | W03 | [[Netzwerktopologien]] | Bus, Ring, Stern, Baum, Masche |
| 9 | W03 | [[Kabel, Stecker & Ethernet-Varianten]] | TP, UTP/STP, Kategorien, Glasfaser, 1000BaseT … |
| 10 | W03 | [[Netzwerkgeräte & Zugriffsverfahren]] | NIC, MAC, Hub vs. Switch, Router, CSMA/CD |
| 11 | W03 | [[Netzwerkarten & Betriebsarten]] | PAN…GAN, Peer-to-Peer vs. Client-Server |
| 12 | W03 | [[Verbindungen & Störungen]] | Dämpfung, EM-Störungen, Fehlerbilder |
| 13 | W03 | [[Internetzugang]] | ISP, FTTH, DOCSIS, xDSL, Kombigerät |
| 14 | W03 | [[WLAN-Standards]] | IEEE 802.11, WPA2/3, AP-Planung |
| 15 | W04 | [[Universelle Gebäudeverkabelung (UGV)]] | EN 50173-1, Primär/Sekundär/Tertiär, Rack, Längen |
| 16 | W04/W12 | [[Offerte erstellen]] | Inhalt einer Offerte, Kalkulation LB3 |
| 17 | W07 | [[Netzwerk konfigurieren & testen (Befehle)]] | Windows-Netzwerk einrichten, ipconfig, ping … |
| 18 | W07 | [[Virtualisierung (M117)]] | Hypervisor Typ 1/2, VM-Setup |
| 19 | W07 | [[Praxisauftrag VM-Netzwerk]] | 2 VMs, Ping, SMB-Freigabe |
| 20 | W08/W10 | [[Benutzer, Gruppen & Berechtigungen]] | Wer/wem/was/wo, Rollen, Berechtigungsmatrix |
| 21 | W10 | [[Dateizugriffsrechte – NTFS & Freigaben]] | NTFS-Rechte, Vererbung, 2 Barrieren, UNC |
| 22 | W08–W11 | [[Hausaufgabe 02.11. – Benutzer, Gruppen & Berechtigungs-Matrix]] · [[Hausaufgabe 09.11. – IT-Dokumentation & Berechtigungs-Matrix]] | meine Hausaufgaben und BM |
| 23 | Skript 6/7 | [[Netzwerk testen – Testkonzept & Sicherheit]] | Testkonzept, TP/TN/FP/FN, Datenschutz |
| 24 | W04–W10 | [[LB3 – Projekt Sota GmbH]] | die Gruppenarbeit mit 4 Teilaufträgen |
| 25 | – | [[Reflexion Modul 117]] | mein Lernjournal |

## 🎯 Kompetenz und Handlungsziele
**Kompetenz:** Installiert ein lokales Netzwerk ohne zentrale Benutzerverwaltung.
**Objekt:** LAN ohne zentrale Benutzerverwaltung mit **bis zu 10 Anschlüssen** und Internetanschluss, das Computer und Drucker in verschiedenen Räumen **des gleichen Gebäudes** verbindet. Kompetenzfeld: *Network Management*.

| HZ | Handlungsziel | Handlungsnotwendige Kenntnisse (HANOK) | Notizen |
|---|---|---|---|
| 1 | Anforderungen mit dem Auftraggeber klären, Dienste bestimmen (File, Print, Internet) | 1.1 lokale Netzwerkdienste und ihre Anforderungen | [[Anforderungen & Netzwerkdienste]] |
| 2 | Logischen und physischen Aufbau definieren, **Netzwerkschema** und **Verkabelungsplan** | 2.1 Inhalt eines Netzwerkschemas · 2.2 Regeln der Netzwerkkonfiguration (IP, Maske, private Adressen, Gateway, DNS) · 2.3 Switch, Accesspoint, Router · 2.4 OSI und TCP/IP · 2.5/2.6 Kabel, Stecker, Ethernet-Varianten (TP, UTP, STP, Glasfaser, RJ45, 100BaseTX, 1000BaseFX, 1000BaseTX) · 2.7 logische und physische Darstellung · 2.8 WLAN-Standards · 2.9 WLAN einrichten | [[Logischer & physischer Netzwerkplan]] · [[IP-Adressierung & Subnetting]] · [[Netzwerkgeräte & Zugriffsverfahren]] · [[OSI-Modell]] · [[Kabel, Stecker & Ethernet-Varianten]] · [[WLAN-Standards]] |
| 3 | Arbeitsschritte für Installation planen (Netzausbau, bauliche Verhältnisse) | 3.1 bauliche Gegebenheiten, Installationsmöglichkeiten, Auswirkung auf Aufwand, Zugänglichkeit, Kosten | [[Universelle Gebäudeverkabelung (UGV)]] · [[Offerte erstellen]] |
| 4 | Netzwerk aufbauen, Komponenten nach Herstellerdoku installieren und konfigurieren | 4.1 Netzwerkeinstellungen von PC, Router, AP · 4.2 Inhalt der Dokumentation eines einfachen Netzes | [[Netzwerk konfigurieren & testen (Befehle)]] · [[Hausaufgabe 09.11. – IT-Dokumentation & Berechtigungs-Matrix]] |
| 5 | Ressourcenverwaltung (Gruppen, Shares), File- und Printsharing, Datensicherheit und Verfügbarkeit | 5.1 Lese-/Schreibrecht, Benutzer, Gruppen, Shares · 5.2 Cloud-Speicherung · 5.3 Rechte dokumentieren (Matrix) | [[Benutzer, Gruppen & Berechtigungen]] · [[Dateizugriffsrechte – NTFS & Freigaben]] |
| 6 | Netzwerk und Systeme testen, Ergebnisse nachvollziehbar dokumentieren | 6.1 Testmethoden und -szenarien · 6.2 funktionaler Test · 6.3 Symptome und Ursachen von Netzwerkfehlern · 6.4 Datenschutz/-sicherheit testen · 6.5 alle Netzelemente testen | [[Netzwerk testen – Testkonzept & Sicherheit]] · [[Verbindungen & Störungen]] |

## 🗓️ Semesterplan (3 Lektionen pro Woche)

| Woche | Thema |
|---|---|
| **W01** | Einführung M117, erste Einführung Netzwerk, Kommunikationsmodell, **OSI-Modell**, **logischer Netzwerkplan** |
| **W02** | **Netzwerkadressierung**, mathematische Grundlagen (Grössenordnungen, binär, hexadezimal), **IP-Berechnungen** |
| **W03** | Netzwerkgrundlagen: Topologien, Verkabelungsarten, Kabelvarianten, Zugriffsverfahren, Ethernet-Geräte, Betriebsarten, Verbindungen & Störungen, Architekturen · **Lernziele LB1** |
| **W04** | Repetition W03, **UGV**, **physischer Netzwerkplan**, **Offerten erstellen**, **Start LB3** (Gruppenbildung, Teilauftrag 1, Abgabezeitplan) |
| **W05** | **LB1 – Theorieprüfung** · Arbeit an LB3 |
| **W06** | Arbeit an LB3 |
| **W07** | Konfigurationen: Netzwerkprotokolle, Netzwerkeinstellungen, Netzwerkdienste, Kontrollieren · LB3 |
| *Herbstferien* | |
| **W08** | Konfigurationen: **Gruppen/User, Berechtigungen, Freigaben**, Kontrollieren · LB3 |
| **W09** | **LB2 – Theorieprüfung** (Lernziele in W07) · LB3 |
| **W10** | Kontakt mit «Kunde», Abgabe Teilauftrag 4 |

> Die Ordner in Teams heissen etwas anders (W01–W12), weil die Unterlagen nach Kalenderwoche abgelegt sind: W03 = Zahlensystem-Blätter, W04 = Netzwerkgrundlagen, W06 = UGV & Netzplan, W07 = Konfiguration & Virtualisierung, W10 = Benutzer & Rechte, W11 = IT-Doku & Repetition, W12 = Offerten.

## 📝 Termine & Leistungsbeurteilungen ICT26c

| LB | Was | Woche | Datum |
|---|---|---|---|
| **LB1** | Theorieprüfung (Skript Kap. 1–2.8). Ohne Buch und Internet, **Spick: 1 A4-Seite handgeschrieben** erlaubt | W05 | **21.09.2026** |
| **LB2** | Theorieprüfung **ganzer Stoff** | W09 | **02.11.2026** |
| **LB3** | Praktische Gruppenarbeit mit **vier Abgabepräsentationen** → [[LB3 – Projekt Sota GmbH]] | Start W06, letzte Abgabe W10 | spätestens **09.11.2026** |

> [!tip] Lerntempo-Duett (W03)
> Die Netzwerkgrundlagen (4 Teilthemen) wurden im **Lerntempo-Duett** erarbeitet: Text lesen, auf A3 visualisieren, **5 Prüfungsfragen** formulieren, mit einem Partner tauschen. Brauchbare Fragen kamen in die **LB1**.

## ⚡ Das Wichtigste auf einen Blick (Spick)

> [!summary]- Netzwerk & Plan
> - Logischer Plan **hierarchisch**: Perimeter → (DMZ) → Core → Distribution → Access → Clients. Keine kreuzenden Linien.
> - Kleinstfirma bis 20 MA: 1 Switch · bis 100 MA: Distribution + Access (ca. 20 Geräte pro Switch)
> - Physischer Plan: **rot = UGV**, **blau = Patchkabel**, APs nicht an Aussenwänden, jeder AP eigene Dose
> - Ein Gerät braucht: **IP, Maske, Gateway, DNS** (oder DHCP)

> [!summary]- OSI
> 1 Bitübertragung (Hub, Repeater) · 2 Sicherung (**MAC, Frame, Switch**) · 3 Vermittlung (**IP, Paket, Router**) · 4 Transport (**TCP/UDP, Ports**) · 5 Sitzung · 6 Darstellung (Zeichensätze) · 7 Anwendung (**HTTP, Firewall, Gateway**). Medium gehört **nicht** zu Schicht 1, es gibt keinen Layer 8.

> [!summary]- IP
> - IPv4 = **32 Bit** (4 Oktette), IPv6 = **128 Bit** (8 × 16 Bit hex), MAC = **48 Bit** (24 Bit Hersteller)
> - Privat: **10.0.0.0/8 · 172.16.0.0/12 · 192.168.0.0/16** · Loopback **127.0.0.0/8** · APIPA **169.254.0.0/16**
> - Hosts = 2^(Host-Bits) − 2 · /24 = 254 · /25 = 126 · /26 = 62 · /27 = 30 · /28 = 14 · /29 = 6 · /30 = 2
> - Kein Gateway → nur lokales Netz · kein DNS → nur IPs, keine Namen

> [!summary]- Kabel & Ethernet
> - TP max. **100 m** (90 m UGV + 2 × 5 m Patch) · Multimode 500 m · Singlemode 80 km
> - Neu verlegen: **mind. Cat 6** (250 MHz), besser Cat 7 · UGV = starrer Draht, Patch = Litze
> - 100BaseTX (Cat 5) · 1000BaseT (Cat 5e, 4 Paare) · 10GBaseT (Cat 7) · …FX/SX/LX = Glasfaser
> - STP-Schirm nur nützlich, wenn **geerdet** · 60 % aller Ausfälle = Stecker/Kabel
> - Switch statt Hub: keine Kollisionen, volle Rate pro Port · CSMA/CD: hören, senden, bei Kollision JAM + zufällig warten

> [!summary]- Benutzer & Rechte
> - Benutzer = **wer**, Gruppe = **wem**, Berechtigung = **was**, Freigabe = **wo**
> - Rechte **nur an Gruppen** · immer **GroupMA** und **GroupAdmin** · **zwei Tabellen** (Mitglieder, BM)
> - R / M / X / F / nR · Freigabe + NTFS → **das strengere gilt** · Vererbung standardmässig an
> - UNC: `\\IP\Freigabe` · FAT32 hat keine Rechte, NTFS schon

> [!summary]- Testen
> 3 Plattformen (Entwicklung, Integration, Produktion = keine Tests) · Testkonzept a–f · alle vier Fälle **TP/TN/FP/FN** diskutieren · keine «Hurra, es läuft»-Tests

## 📖 Bücher & Nachschlagewerke in Teams (Ordner «Books»)
Die Bücher sind **Nachschlagewerke** und gehen weit über M117 hinaus. Für M117 relevant:

| Buch | Seiten | Für M117 wichtige Kapitel |
|---|---|---|
| **HERDT: Netzwerke – Protokolle und Dienste** | 182 | 3 Netzwerkmodelle · 4 TCP/IP · 5 IP · 6 TCP und UDP · 7 NAT · 9 DNS · 11 Netzwerkkonfigurationsdienste (DHCP) · 13 DSL · 17 WLAN · 18 Firewall und DMZ |
| **Windows Server 2022 – Aufbau und Verwaltung** | 231 | 3 Netzwerk mit Windows · 13 Berechtigungen anpassen · 14 Dateidienste · 15 Drucker verwalten. (Active Directory, GPO, DHCP-Server = **Modul 123**) |
| **Windows Server 2022 – Erweiterte Netzwerkadministration** | 172 | 2 IP-Adressen und Subnetze · 3 Routing. (DNS, DHCP, VPN, DFS = spätere Module) |

Weitere Unterlagen:
- **Vollständiges Skript M117** (TBZ, Johann Widmer et al., V4.0, 74 Seiten) → in diesen Notizen verarbeitet
- **Nachschlagewerk zu den Netzwerkgrundlagen** (Philipp Rohr, V3.0) → in diesen Notizen verarbeitet
- Weiterführend: *CompTIA Network+* (Markus Kammermann) · *Modul 117* (Compendio)

## 🔗 Nützliche Links aus Teams
- Zeichnen: **app.diagrams.net** (draw.io) oder Visio · Vorlage Büroplan: gitlab.com/ch-tbz-it/Stud/m117
- Simulation: **Filius** (lernsoftware-filius.de)
- Zahlensysteme: arndt-bruenner.de · gut-erklaert.de · serlo.org · burgnetz.de
- IP: de.wikipedia.org (IP-Adresse, IPv4, IPv6) · elektronik-kompendium.de (IPv4, IPv6, CIDR) · vultr.com (IPv4/IPv6-Rechner)
- OSI vs. TCP/IP: community.fs.com
- NAS-Demo: demo.synology.com · Sicherheit: kb.cert.org/vuls · nvd.nist.gov
- Kabel: de.wikipedia.org/wiki/Twisted-Pair-Kabel · Ethernet: de.wikipedia.org/wiki/Ethernet

## Siehe auch
- [[Netzwerk (Modul 117)]]
