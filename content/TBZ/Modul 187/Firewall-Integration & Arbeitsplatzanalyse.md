---
tags: [betriebssysteme, modul187, firewall, netzwerk, protokolle]
datum: 18.11.2026
---

# Firewall-Integration & Arbeitsplatzanalyse

> [!info] Heutiges Thema
> Firewall-Integration und Arbeitsplatzanalyse.

## Auftrag
- [ ] Die **OPNsense-Firewall** einbinden und den **Internetzugang testen**
- [ ] **Firewall-Zonen** und **Firewall-Regeln** erklären
- [ ] Einen **Arbeitsplatz analysieren**, die passende Firewall wählen und einstellen

## Was ist eine Firewall?
Eine Firewall steht zwischen zwei Netzen (z. B. Internet und Firmennetz) und entscheidet für jedes Paket mit **Regeln**, ob es durchdarf oder nicht. **OPNsense** ist eine kostenlose Open-Source-Firewall, die man z. B. als VM betreiben kann. Wo die Firewall im Netz steht, zeigt [[Internetzugang]].

### Firewall-Zonen
| Zone | Was ist das? | Vertrauen |
|---|---|---|
| **WAN** | die Seite zum Internet | gering |
| **LAN** | das interne Netz mit den Arbeitsplätzen | hoch |
| **DMZ** | eigenes Netz für Server, die vom Internet erreichbar sein müssen (z. B. Webserver) | mittel |

### Firewall-Regeln
Eine Regel sagt: **Von** wo (Quelle) **nach** wo (Ziel), über welches **Protokoll/welchen Port**, **erlauben oder blockieren**.

| Aktion | Quelle | Ziel | Port | Bedeutung |
|---|---|---|---|---|
| erlauben | LAN | beliebig | 443 (HTTPS) | Arbeitsplätze dürfen sichere Webseiten öffnen |
| erlauben | LAN | DNS-Server | 53 (DNS) | Namen auflösen |
| blockieren | WAN | LAN | alle | aus dem Internet kommt niemand direkt ins LAN |

> [!important] Grundprinzip
> Alles ist **verboten**, was nicht ausdrücklich **erlaubt** ist. In OPNsense werden die Regeln **von oben nach unten** geprüft, die erste passende Regel gilt.

## Transportschicht: TCP und UDP
Im [[OSI-Modell]] liegen ganz unten die **Bitübertragungsschicht** (Physical Layer), darüber die **Sicherungsschicht** (Data Link Layer), die **Vermittlungsschicht** (Network Layer) und dann die **Transportschicht** (Transport Layer). **TCP und UDP** liegen auf der Transportschicht (Schicht 4).

- **TCP:** zuverlässig. Wenn etwas nicht ankommt, merkt das der Empfänger und sagt sinngemäss: „Mir fehlen diese Pakete, schick sie nochmal.“ Darum für Fotos, Mails und Webseiten.
- **UDP:** schnell, ohne Nachfragen. Was verloren geht, bleibt weg. Darum für **Live-Video**, Videocalls und Games, wo ein kurzes Ruckeln besser ist als Warten.

> [!note] Korrektur zu meinen Notizen
> Netflix und YouTube laden Videos meistens über **HTTPS, also TCP**, weil sie vorausladen (puffern) können. UDP ist typisch für Videos, die **live** sein müssen (Videocalls, Livestreams). Mehr Details: [[Arbeitsplatzaufbau & IPv4-Netzwerkkonfiguration]].

## Protokolle und Ports
Was sind FTP, HTTP und SMTP? Es sind **Protokolle**, also abgemachte Regeln, um verschiedene Sachen zu verschicken. Jedes Protokoll hat einen **Standard-Port**, an dem die Firewall es erkennt.

| Protokoll | Wofür | Port | Transport |
|---|---|---|---|
| **HTTP** | Webseiten (unverschlüsselt) | **80** | TCP |
| **HTTPS** | Webseiten (verschlüsselt) | **443** | TCP |
| **FTP** | Dateien übertragen | 20/21 | TCP |
| **SMTP** | E-Mails versenden | 25 (587 mit Anmeldung) | TCP |
| **DNS** | Namen in IP-Adressen übersetzen | **53** | UDP (und TCP) |
| **SSH** | Fernzugriff auf Server | 22 | TCP |

> [!warning] HTTP ist Port 80
> In meinen Notizen stand HTTP = 53. Richtig ist **HTTP = 80**, Port **53 ist DNS**.

## Siehe auch
- [[Arbeitsplatzaufbau & IPv4-Netzwerkkonfiguration]]
- [[Internetzugang]]
- [[OSI-Modell]]
- [[Netzwerk testen – Testkonzept & Sicherheit]]
