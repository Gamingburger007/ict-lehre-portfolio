---
tags: [netzwerk, modul117, wlan]
quelle: M117 Skript Kap. 2.8 und 2.10
---

# WLAN-Standards

WLAN-Access-Points nutzen eine **Funkfrequenz** als Übertragungsmedium. Die Frequenzen werden weltweit von der **ITU** (International Telecommunication Union) zugewiesen. Alle WLAN-Standards sind in **IEEE 802.11** genormt (IEEE = Institute of Electrical and Electronics Engineers).

- **2,4 GHz:** am weitesten verbreitet, grössere Reichweite, aber weniger Daten
- **5 GHz:** mehr Daten, weniger Reichweite
- Neuere Standards: **60 GHz** (802.11ad)

## Übersicht der Normen

| Norm | Übertragungsrate | Frequenz |
|---|---|---|
| 802.11 | 2–11 Mbit/s | 2,4 GHz |
| 802.11b | bis 44 Mbit/s | 2,4 GHz |
| 802.11g | bis 108 Mbit/s | 2,4 GHz |
| 802.11a | bis 108 Mbit/s | 5 GHz |
| 802.11n (Wi-Fi 4) | bis 200 Mbit/s (1 Antenne) / 800 Mbit/s (4 Antennen) | 2,4 oder 5 GHz |
| 802.11ac (Wi-Fi 5) | bis 866 Mbit/s (1 Antenne) / 6'933 Mbit/s (8 Antennen) | 5 GHz |
| 802.11ad | bis 6'700 Mbit/s | 60 GHz |
| 802.11ax (Wi-Fi 6) | bis 1'200 Mbit/s (1 Antenne) / 9'608 Mbit/s (8 Antennen) | 2,4 oder 5 GHz |

> [!note] Shared Medium
> Alle Geräte an einem AP **teilen sich** dessen Übertragungskapazität. Es stimmt aber nicht, dass 8 Geräte bei 800 Mbit/s nur je 100 Mbit/s bekommen, effektiv ist es viel mehr.

## Sicherheit
- Weil das Medium geteilt ist, muss der Zugang zum AP **abgesichert** sein.
- Nur noch **WPA2** oder **WPA3** (Wi-Fi Protected Access) verwenden, alles andere ist zu unsicher.
- Grosse Firmen nutzen für die Anmeldung einen **RADIUS-Server**.

## Reichweite und Planung
- Wände, Metallregale und andere Hindernisse **dämpfen** das Signal. 200–300 m Reichweite ist nur ein theoretischer Wert.
- Verbessern: **WLAN-Repeater** oder **mehrere APs** gut verteilt.
- **Funkplanung (Radio-Planung)** mit Profi-Geräten wie dem *Ekahau Sidekick* (3'000–9'000 $). Ergebnis: eine Abdeckungskarte auf dem Grundriss. Oft einfacher: **ein AP pro grösserem Büroraum**.
- **Kanäle:** Viele APs im gleichen Haus (z. B. Mietshaus) stören sich, wenn sie denselben Kanal nutzen. Neue APs suchen den besten Kanal selbst, sonst den Kanal von Hand ändern. Belegte Kanäle mit Apps prüfen (WiFi Analyzer, AirPort-Dienstprogramm).

> [!tip] Regeln für den Gebäudeplan
> - APs **nicht an Aussenwänden** montieren: das WLAN soll intern genutzt werden und von aussen nicht sichtbar sein.
> - Jeder AP hat eine **eigene Netzwerkdose** und ist mit einem Patchkabel angeschlossen (siehe [[Universelle Gebäudeverkabelung (UGV)]]).

## WLAN einrichten (Arbeitsschritte)
1. Standort(e) der APs planen (Abdeckung, nicht an Aussenwand)
2. Dose + Patchkabel zum Switch, Strom (oder PoE)
3. AP konfigurieren: **SSID**, **WPA2/WPA3** mit starkem Passwort, Kanal
4. Optional ein getrenntes **Gästenetz**
5. Testen: Verbindung, IP-Adresse, Übertragungsrate in jedem Raum

## Siehe auch
- [[Internetzugang]]
- [[Kabel, Stecker & Ethernet-Varianten]]
- [[Logischer & physischer Netzwerkplan]]
