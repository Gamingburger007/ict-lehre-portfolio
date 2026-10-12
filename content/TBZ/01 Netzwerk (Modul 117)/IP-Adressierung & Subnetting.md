---
tags: [netzwerk, modul117, ip-adressierung]
---

# Netzwerkadressierung

## MAC-Adresse
Die MAC-Adresse ist eine **physische bzw. hardwarebezogene Adresse** einer Netzwerkschnittstelle.
- 48 Bit bei klassischen Ethernet-MAC-Adressen
- wird auf **OSI-Schicht 2** verwendet (siehe [[OSI-Modell]])
- dient zur Kommunikation innerhalb eines lokalen Netzwerks
- Beispiel: `00:1A:2B:3C:4D:5E`
- Formatierung: 2er-Päckchen mit Stichen oder Punkten getrennt

## IP-Adresse
Eine IP-Adresse ist eine **logische Netzwerkadresse**, um Geräte bzw. Netzwerkschnittstellen in einem Netzwerk zu adressieren.

### IPv4
- 32 Bit, besteht aus 4 Oktetten
- Beispiel: `192.168.1.10`
- gehört zur **OSI-Schicht 3**

### IPv6
- 128 Bit, deutlich grösserer Adressraum als IPv4

## Subnetzmaske und CIDR

### Subnetzmaske
Bestimmt, welcher Teil einer IP-Adresse das **Netzwerk** und welcher Teil den **Host** beschreibt.
Beispiel: `192.168.1.0/24` → Subnetzmaske: `255.255.255.0`

### CIDR
CIDR = **Classless Inter-Domain Routing**. Ermöglicht eine flexible Aufteilung von IP-Netzen. Der CIDR-Suffix gibt an, wie viele Bits für den **Netzwerkanteil** verwendet werden.

Beispiel `192.168.1.0/24`:
- 24 Bit Netzwerkanteil
- 8 Bit Hostanteil (da IPv4 insgesamt 32 Bit hat: 32 − 24 = 8 Host-Bits)

### Beispiele für CIDR

| CIDR/Suffix | Subnetzmaske | Host-Bits |
|---|---|---|
| /8 | 255.0.0.0 | 24 |
| /16 | 255.255.0.0 | 16 |
| /24 | 255.255.255.0 | 8 |
| /30 | 255.255.255.252 | 2 |

> [!important] Bei einem normalen IPv4-Subnetz sind die **Netzwerkadresse** und **Broadcast-Adresse reserviert**. Deshalb gilt bei einem /30-Netz: 2² = 4 IP-Adressen insgesamt, davon 1 Netzwerkadresse, 2 nutzbare Host-Adressen, 1 Broadcast-Adresse.

### Netzwerkadresse
Die **erste Adresse** eines Subnetzes.
Beispiel `192.168.1.0/24` → Netzwerkadresse: `192.168.1.0`

### Broadcast-Adresse
Die **letzte Adresse** eines IPv4-Subnetzes. Mit ihr können alle Geräte eines Subnetzes gleichzeitig angesprochen werden.
Beispiel `192.168.1.0/24` → Broadcast: `192.168.1.255`

### Host-Adresse
Eine **nutzbare IP-Adresse** innerhalb eines Subnetzes, die einem Gerät bzw. einer Netzwerkschnittstelle zugewiesen werden kann.
Beispiel `192.168.1.0/24`:
- Netzwerkadresse: 192.168.1.0
- mögliche Host-Adressen: 192.168.1.1 – 192.168.1.254
- Broadcast: 192.168.1.255

### Gateway-Adresse
Das Standard-Gateway ist normalerweise die IP-Adresse eines **Routers**, über den ein Gerät andere Netzwerke erreichen kann.
Beispiel: PC `192.168.1.20`, Gateway `192.168.1.1`.
> Ein Gateway ist keine zusätzliche reservierte Adresse wie Netzwerk- oder Broadcast-Adresse. Eine normale Host-Adresse kann als Gateway verwendet werden.

### Gerätename
Der Gerätename (Hostname) identifiziert ein Gerät innerhalb eines Netzwerks.
Beispiele: `PC-01`, `SERVER-01`, `LAPTOP-TIM`, `NAS-01`

## Private IPv4-Adressen
Private Adressen werden innerhalb von lokalen Netzwerken verwendet und **nicht direkt im öffentlichen Internet geroutet**.

| Klasse | Bereich | CIDR | Adressanzahl |
|---|---|---|---|
| A / grosse Netzwerke | 10.0.0.0 – 10.255.255.255 | 10.0.0.0/8 | 2²⁴ = 16'777'216 |
| B / mittlere Netzwerke | 172.16.0.0 – 172.31.255.255 | 172.16.0.0/12 | 2²⁰ = 1'048'576 |
| C / kleine Netzwerke | 192.168.0.0 – 192.168.255.255 | 192.168.0.0/16 | 2¹⁶ = 65'536 |

> [!note] Die alten Bezeichnungen Klasse A, B und C werden bei CIDR nicht mehr für die eigentliche Netzplanung verwendet. Sie können aber zum Lernen der privaten Bereiche als Eselsbrücke vorkommen.

## APIPA
APIPA = **Automatic Private IP Addressing**. Bereich: `169.254.0.0/16`.
Ein Gerät kann sich selbst eine APIPA-Adresse geben, wenn es beispielsweise **keine IP-Adresse von einem DHCP-Server erhält**. APIPA-Adressen werden normalerweise nur für die lokale Kommunikation verwendet. Ein Standard-Gateway wird dabei normalerweise **nicht** verwendet.

## Localhost
Der Localhost bezeichnet **das eigene Gerät**. Bei IPv4: `127.0.0.0/8`. Die bekannteste Adresse ist `127.0.0.1`. Wenn ein Dienst auf dem eigenen Computer läuft, kann man ihn beispielsweise über `http://127.0.0.1` erreichen – die Verbindung bleibt dabei auf dem eigenen Computer.

## Spoofing
Spoofing bedeutet, dass ein Angreifer eine Identität bzw. Adresse **fälscht oder vortäuscht**. Beispiele: MAC-Spoofing, IP-Spoofing, E-Mail-Spoofing.
> Spoofing ist nicht automatisch dasselbe wie eine Man-in-the-Middle-Attacke, kann jedoch bei bestimmten Angriffen eingesetzt werden.

## CSMA/CD
CSMA = **Carrier-Sense Multiple Access**. Legen die Regeln fest wie ein Austausch zwischen 2 Rechnern in einem Netzwerk abläuft.
CSMA-CD ist die bekannteste Variante: **CD = Collision Detection**.
Die Rechner hören das Netzwerk die ganze Zeit ab, um zu schauen, ob gerade Dateien ausgetauscht werden oder ob die Bahn frei ist, um Daten zu senden. Kommt es zu einer Kollision, sendet der Rechner, der das Problem als erstes erkannt hat, ein JAM-Signal. Dadurch erfahren alle Rechner, dass es zu einer Kollision kam, und die Übertragung kann ordnungsgemäss funktionieren.

## Siehe auch
- [[Netzwerk Grundlagen]]
- [[Netzwerktopologien]]
- [[OSI-Modell]]
