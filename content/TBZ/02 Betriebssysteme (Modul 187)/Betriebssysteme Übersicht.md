---
tags: [betriebssysteme, modul187]
---

# 1. Betriebssysteme (OS) & Dateisysteme

## Vor- und Nachteile der 3 grossen Betriebssysteme

### Windows (NTFS)
- **Vorteile:** Riesige Software- & Spiele-Auswahl, hohe Hardware-Kompatibilität, sehr verbreitet im Büroalltag.
- **Nachteile:** Anfallende Lizenzkosten, hohe Systemanforderungen (Ressourcenhunger), sammelt viele Telemetriedaten (Datenschutz), anfälliger für Malware.

### macOS (APFS)
- **Vorteile:** Nahtlose Integration ins Apple-Ökosystem, sehr stabile Hardware-Software-Abstimmung, hohe Sicherheitsstandards, sehr performant bei Bild-/Videobearbeitung.
- **Nachteile:** Hohe Anschaffungskosten für die Hardware, kaum aufrüstbar, eingeschränkte Spiele-Auswahl, nur auf Apple-Hardware nutzbar.

### Linux (ext4)
- **Vorteile:** Open Source (kostenlos), sehr anpassbar, viele Distributionen (Ubuntu, Debian, Fedora, Red Hat), extrem ressourcenschonend.
- **Nachteile:** Nicht so nutzerfreundlich, offizieller Support fast nicht vorhanden (Community-abhängig), manche Spezialsoftware/Spiele fehlen, höhere Einarbeitungszeit.

## 2. Die 6 Kernaufgaben eines Betriebssystems
1. **Prozessverwaltung:** Steuert und verteilt Rechenzeit (eine CPU/Kern kann zeitgleich nur eine Aufgabe verarbeiten).
2. **Speichersysteme:** Verwaltet den Arbeitsspeicher (RAM).
3. **Dateisystemverwaltung:** Leitet Dateien weiter an das Speichermedium (HDD/SSD).
4. **Geräteverwaltung:** Treiber sorgen dafür, dass Peripherie-Geräte miteinander kommunizieren können.
5. **Benutzerschnittstelle:** GUI = Graphical User Interface (grafische Oberfläche), CLI = Command Line Interface (Kommandozeile/Eingabeaufforderung).
6. **Sicherheit & Rechteverwaltung:** Regelt Zugriffsrechte für Benutzer und Programme.

## 3. Merkmale & Begriffe der Betriebssysteme
- **Linux:** Monolithischer Kernel, Open Source (GPL), diverse Varianten.
- **macOS:** Darwin-Kernel, proprietär, geschlossenes Ökosystem, hohe Integration mit Apple-Geräten.
- **Windows:** Grösster Marktanteil auf Desktop-PCs.

## 4. Software & Browser

### Software-Kategorien
- **Büroanwendungen:** Microsoft 365, LibreOffice (Word-Dokumente können auch mit Google Docs geöffnet werden).
- **Kommunikation:** Outlook, Teams.
- **Browser:** Edge, Chrome, Firefox, Safari (Chrome läuft auf fast allen Systemen).
- **Systemnahe Tools:** PDF-Reader, 7-Zip, Antivirus.

### Browser & Cloud
- **Rendering-Engine:** Wandelt HTML- & JavaScript-Code in eine sichtbare Website um.
- **Chromium:** Die Open-Source-Basisversion von Chrome (ist nicht direkt von Google).
- **Cloudbasiert:** Daten/Programme liegen auf externen Servern, Zugriff erfolgt per Abo oder kostenlos über das Internet.

## 5. Rechtliches, Sicherheit & Emulation
- **EULA:** End User License Agreement (Endbenutzer-Lizenzvereinbarung).
- **Open Source:** Nicht alle Open-Source-Lizenzen erlauben eine uneingeschränkte Nutzung ("Open-Use").
- **Netzwerk:** Router besitzen eine integrierte Hardware-Firewall.
- **Emulation:** Ermöglicht z. B. das Nutzen von Windows auf Apple-Geräten (benötigt aber deutlich mehr Ressourcen und ist RAM-intensiv).

## 6. Auswahlkriterien für Software
- **Kompatibilität:** Funktioniert die Software mit der vorhandenen Hardware und dem Betriebssystem?
- **Kostenmodell:** Einmalkauf, Abonnement oder kostenlos?
- **Update-Fähigkeit:** Wie lange und wie regelmässig werden Updates bereitgestellt?
- **Interoperabilität:** Ist die Software aktuell und harmoniert sie mit anderen Schnittstellen?
- **Sicherheitsaspekte:** Gibt es bekannte Schwachstellen und wie häufig kommen Sicherheitspatches?

## 7. Vorgehen bei der Software-Auswahl
1. **Anforderungen analysieren:** Welche Aufgabe soll die Software genau erfüllen?
2. **Kriterien gewichten:** Was hat die höchste Priorität (z. B. Preis vs. Sicherheit)?
3. **Optionen vergleichen:** Mindestens 2 Optionen gegenüberstellen.
4. **Entscheidung begründen:** Vorgehen schriftlich dokumentieren, um es nachvollziehbar zu machen.

> [!note] Praxistipps
> - In Dokumenten immer als PDF abgeben und in ganzen Sätzen schreiben, damit man wie mit dem Lehrer redet, da man ja auch mit Kunden redet. Immer gut begründen, da es kein Richtig und Falsch gibt.
> - Es gibt etwa 20'000 Abkürzungen in der ICT, z. B. LTS = Longtermsystem – am besten in einer Legende angeben.
> - **Docker** ist eine Container-Technologie, eine Software, die verschiedene VMs laufen lässt (genauer: Container).
> - Wir müssen sehr spezifisch sein, wenn wir bsp. Fedora oder Mint vorschlagen – dann direkt sagen, wieso und warum genau.
> - **Hypervisor** ist eine Software, die verschiedene virtuelle Maschinen launcht.

## Plattform, Supportmodell und Kundenberatung

**Plattform**
- Hardware ist der physische Computer: Grafikkarte, CPU, RAM, SSD/HDD etc.
- Eingebettete Systeme sind Mikrocomputer, die irgendwo in der Welt sind – wie kleine Handwerker, die die App warten oder reparieren.
- Betriebssystem: macOS, Windows, Linux
- BIOS ist proprietäre Software
- Software: alle Applikationen – Word, PowerPoint, Fortnite etc.

Plattformentwicklung heisst, alles oben Genannte aufzusetzen und es betriebsbereit zu machen. **Unsere 6-Punkte-Checkliste ist sehr wichtig.**

## IT Support
Es liegen Fehler vor und diese müssen behoben werden. Es gibt 3 verschiedene Support-Modelle:

### 1. Hersteller-Support
Direkter Support vom Hersteller, hohe Kosten, aber sehr schnell & verfügbar (Premier Support).

### 2. Partner-Support
Man geht auf eine IT-Firma. Mittel-teure Kosten. Diese Firma kümmert sich dann meistens um alles.

### 3. Interner Support
Individuelle Mitarbeiter bei einer Firma. Sofortiger Support. Billig/Fixkosten, aber nur ab einer gewissen Grösse der Firma sinnvoll.

### Support-Modell nach SLA
SLA = **Service Level Agreement**. Definiert:
- Wie viel er kostet und was er beinhaltet
- Reaktionszeit bei Ausfällen
- Verfügbarkeit, meistens 99 % oder noch höher
- Eskalationsstufen Level 1/2/3 Support

### Beispiel – Kleines Fallbeispiel
Ein Architektbüro mit 8 Mitarbeitenden benötigt neue Arbeitsplätze.
- Anforderungen: CAD-Software, Windows exklusiv
- Gelegentliche HO-Nutzung, begrenztes IT-Budget, keine eigene IT-Abteilung

## Siehe auch
- [[BIOS & UEFI]]
- [[Lizenzierung – OEM, Retail, KMS, MAK]]
- [[Virtualisierung & VM-Netzwerke]]
