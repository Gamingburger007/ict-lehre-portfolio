---
tags: [netzwerk, modul117]
---

# Netzwerk – Grundlagen

## Netzwerkpläne

Netzwerkpläne dienen als **Landkarte eines Netzwerks**. Sie zeigen, welche Geräte vorhanden sind, wie sie miteinander verbunden sind und wo sie sich befinden.

### Logischer Netzwerkplan
Eine grafische Darstellung der **logischen Struktur** eines Netzwerks. Man sieht beispielsweise:
- IP-Adressen bzw. Subnetze
- Router
- Switches
- Firewalls
- Server
- logische Verbindungen

### Physischer Netzwerkplan
Zeigt den **tatsächlichen Aufbau** eines Gebäudes und der Netzwerk-Infrastruktur. Zum Beispiel:
- Räume
- Türen und Fenster
- Netzwerkdosen
- Kabel
- Switches
- Access Points
- Server-/Netzwerkschränke

Der Plan hilft dabei zu entscheiden, **wo Netzwerkkomponenten installiert werden müssen**, damit eine gute Netzwerkabdeckung entsteht.

### Bedarf feststellen
Bevor ein Netzwerk geplant wird, muss der **Bedarf des Kunden** ermittelt werden:
- Wie viele Mitarbeitende gibt es?
- Welche Geräte werden verwendet?
- Welche Dienste werden benötigt?
- Wie gross soll das Netzwerk sein?
- Wird WLAN benötigt?
- Gibt es besondere Sicherheitsanforderungen?

## Netzwerkkomponenten

### Firewall
Eine Firewall kontrolliert den **ein- und ausgehenden Netzwerkverkehr** anhand von Regeln. Sie entscheidet, welche Verbindungen erlaubt oder blockiert werden.
> **Merksatz:** Eine Firewall ist wie ein Türwächter – sie entscheidet, wer hinein- oder hinausdarf.

Eine Firewall kann beispielsweise in einem Router integriert sein.

### DMZ
DMZ = **Demilitarisierte Zone**. Ein separates Netzwerksegment, das zwischen dem internen Netzwerk und dem Internet liegt. Dort platziert man Systeme, die **aus dem Internet erreichbar sein müssen**, aber nicht direkt im internen Netzwerk stehen sollen.
Beispiele: Webserver, Mailserver, VPN-Server.

Die DMZ dient dazu, das interne Netzwerk zusätzlich zu schützen.

### VPN Concentrator
Bündelt und verwaltet **mehrere VPN-Verbindungen**, damit z. B. Mitarbeitende von ausserhalb sicher auf das Unternehmensnetzwerk zugreifen können.
VPN = Virtual Private Network.

### Router
Verbindet **verschiedene Netzwerke** miteinander und leitet Datenpakete zwischen diesen Netzwerken weiter.
Beispiel: Internes Netzwerk → Router → Internet

### Core Switch
Bildet einen zentralen Teil des Netzwerks und verbindet verschiedene **Netzwerkbereiche bzw. Switches** miteinander. Wird vor allem in grösseren Netzwerken eingesetzt.

### Distribution Switch
Verbindet beispielsweise **Access Switches mit dem Core-Netzwerk**. Bildet eine Verbindung zwischen der Zugriffsebene (Access) und der Kernschicht (Core).

### Access Switch
Verbindet **Endgeräte mit dem Netzwerk** (PCs, Drucker, IP-Telefone, Access Points). Normalerweise mit einem Distribution Switch oder direkt mit dem Core-Netzwerk verbunden.

### Directory Server
Verwaltet Informationen über **Benutzer, Gruppen, Computer und andere Netzwerkressourcen** zentral, damit Benutzer und Berechtigungen nicht auf jedem einzelnen Gerät separat verwaltet werden müssen. Beispiele: Benutzerkonten, Gruppen, Passwörter, Zugriffsrechte. Bekanntes Beispiel: **Active Directory**.

### File Server / NAS
Stellt zentralen **Speicherplatz für Dateien** zur Verfügung (Word-Dokumente, Bilder, Videos, Projektdateien). Ein NAS (Network Attached Storage) ist ein Gerät, das Speicher über das Netzwerk bereitstellt.

### Database Server
Speichert und verwaltet **strukturierte Daten**, z. B. eine Kundendatenbank mit Vorname, Nachname, Adresse, Telefonnummer. **SQL** ist die Sprache, mit der Datenbanken abgefragt und bearbeitet werden können.

### Endgeräte
Geräte, die von Benutzern verwendet werden oder Daten im Netzwerk erzeugen bzw. empfangen: Computer, Notebook, Smartphone, Tablet, Drucker.

### Perimeternetzwerk
Befindet sich am **Übergang zwischen dem internen Netzwerk und externen Netzwerken** (z. B. dem Internet). Eine DMZ kann Teil des Perimeternetzwerks sein.

## Das Einführungsbild (W01, Aufgabe 1)
In der ersten Woche mussten alle Begriffe aus diesem Bild in eigenen Worten erklärt werden:

![[einfuehrung-netzwerk-kleine-firma.jpg]]

Begriffe, die oben noch fehlen:

| Begriff | Erklärung |
|---|---|
| **Internet** | weltweiter Zusammenschluss vieler IP-Netze, siehe [[Internetzugang]] |
| **WWW-Server** | Webserver, liefert Webseiten (HTTP/HTTPS) aus, steht in der DMZ |
| **IP-TV-Server** | verteilt Fernsehprogramme über das IP-Netz |
| **VoIP-Server** | Telefonanlage über IP (Voice over IP), vermittelt Anrufe der IP-Telefone |
| **Streamer** | Streaming-Server für Audio/Video (oder Bandlaufwerk für Backups) |
| **Standard Host** | gewöhnlicher Server/Rechner, der Dienste anbietet |
| **Storage** | zentraler Speicher (z. B. SAN), auf den Server zugreifen |
| **Network Management** | Station zum Überwachen und Verwalten des Netzes (Monitoring, z. B. per SNMP) |
| **WLAN Access Point** | bringt Tablets, Phones, Laptops drahtlos ins LAN, siehe [[WLAN-Standards]] |
| **Access Switch** | verbindet Endgeräte (PC, Drucker, AP) mit dem Netz |

## Was ein Gerät braucht, um ins IP-Netz zu kommen
Der Netzverantwortliche (oder automatisch der **DHCP-Server**) muss vier Angaben liefern:
1. **IP-Adresse** des Geräts, z. B. `192.168.12.21`
2. **Subnetzmaske** (dezimal `255.255.255.0` oder als Suffix `/24`)
3. **Standardgateway** = IP des Router-Ports, an dem das LAN hängt
4. **DNS-Server** = wandelt Namen (www.tbz.ch) in IP-Adressen um

Mit DHCP stellt man am Gerät nur **«IP-Adresse automatisch beziehen»** ein. Prüfen mit `ipconfig /all`. Details: [[IP-Adressierung & Subnetting]] und [[Netzwerk konfigurieren & testen (Befehle)]].

## Siehe auch
- [[Modul 117 – Überblick]]
- [[Anforderungen & Netzwerkdienste]]
- [[Logischer & physischer Netzwerkplan]]
- [[Netzwerkgeräte & Zugriffsverfahren]]
- [[IP-Adressierung & Subnetting]]
- [[Netzwerktopologien]]
- [[OSI-Modell]]
