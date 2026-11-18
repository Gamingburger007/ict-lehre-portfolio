---
tags: [netzwerk, modul117, anforderungen, dienste, cloud]
quelle: M117 Skript Kap. 1 und 5.2
---

# Anforderungen an das Netzwerk & Netzwerkdienste

> [!info] Worum geht es?
> Bevor man ein Netzwerk plant, klärt man mit dem Kunden, **was sein Geschäft wirklich braucht**. Davon hängt ab, wie das Netz aussieht. (Handlungsziel 1 im [[Modul 117 – Überblick]])

## Clients und Dienste
- **Clients** = alle Geräte, die eine IP-Adresse bekommen und am Netz hängen: Laptops, PCs, Tablets, Smartphones, Smartwatches, IoT-Geräte (Internet of Things).
- **Dienste (Services)** laufen meistens auf Servern, die Clients benutzen sie. Ob der Server in der Firma, beim Service Provider oder in der Cloud steht, spielt für den Client keine Rolle.
- Beispiele für Dienste: Mail, Websites, Speicher (Storage), **DHCP** (automatische IP-Vergabe), **DNS** (Namensauflösung), Textverarbeitung, Buchhaltung, Druck- und Scanservices.

## Intern oder extern?

| Gut auslagerbar (ISP / Datacenter) | Lieber intern (Sicherheit) |
|---|---|
| Webserver | Speicher für interne Daten |
| Mailserver | DHCP |
| DNS | Buchhaltung, Textverarbeitung |
| andere Internet-Dienste | Druck- und Scanservices |

- Kleinere Firmen lagern Dienste aus, um ihr **LAN zu entlasten**.
- Mit der Cloud verschwimmen die Grenzen: heute kann man **alles** in der Cloud betreiben.

> [!warning] Wo liegen die Daten?
> Geschäftskritische Daten dürfen unter Umständen **die Firma oder das Land nicht verlassen**. Man muss immer wissen, wo die Daten gespeichert sind. **Mitarbeiterdaten dürfen nicht im Ausland gespeichert werden.**

## Fragen an den Kunden (Bedarf feststellen)
- Wie viele Mitarbeitende und welche Geräte?
- Welche Dienste braucht es (File, Print, Internet, Mail, Cloud)?
- Wie gross soll das Netz sein, wird WLAN gebraucht?
- Welche Daten sind heikel (Personaldaten, Medizinaldaten)?
- Siehe auch Bedarfsliste in [[Netzwerk Grundlagen]].

## Cloud-Speicherung
**Vorteil:** Betrieb und Wartung eigener Infrastruktur sind aufwendig, Know-how ist teuer. Cloud-Anbieter speichern und sichern (Backup) die Daten.
**Haken:** Vertrauliche Daten liegen ausserhalb der Kontrolle des Eigentümers, Speichern im Ausland ist teilweise verboten.

Lösungen:
1. **Schweizer Cloud-Dienst**, der garantiert, dass die Daten nur in der Schweiz liegen.
2. **Peer-to-Peer-Cloud** (z. B. Cubbit): Daten sind verteilt, stark verschlüsselt und mit Blockchain-Methoden abgesichert, nie ganz an einem Ort.
3. **Private Cloud**: aufwendig, braucht viel Know-how.

> [!tip] Worauf achten bei einer Cloud-Lösung?
> Speicherort der Daten · Installation und Bedienbarkeit · Kosten · **Multi-Faktor-Authentisierung (MFA)** für den Zugang.

## Typische Aufgaben aus dem Skript
- Tabelle: *Dienst · intern/extern · viel/wenig Netzkapazität · in Cloud möglich?*
- Alle Geräte im Beispiel-LAN (Bild 1) in eigenen Worten erklären, z. B. **Router** = Vermittlungsrechner, der zwei IP-Netze verbindet (Firmennetz ↔ Netz des ISP).

## Siehe auch
- [[Netzwerk Grundlagen]]
- [[Internetzugang]]
- [[Benutzer, Gruppen & Berechtigungen]]
