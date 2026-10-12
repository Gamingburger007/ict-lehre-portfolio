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

## Siehe auch
- [[IP-Adressierung & Subnetting]]
- [[Netzwerktopologien]]
- [[OSI-Modell]]
