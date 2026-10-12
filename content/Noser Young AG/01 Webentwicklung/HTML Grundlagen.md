---
tags: [webentwicklung, html]
---

# HTML

HTML ist eine Abkürzung für **Hyper Text Markup Language**. Sie ist der einfachste Grundbaustein einer Website.

## Wichtige Grundregeln
- Wir schreiben Projektdateien immer klein, wenn wir ein neues Projekt erstellen.
- Die Hauptdatei einer Website nennt man `index.html`, wenn sie die Website steuern/laufen lassen soll.
- Man hat immer nur **ein `<h1>`-Element** auf der Website – weil das `<h1>` das wichtigste Überschriften-Element der Seite ist (die Haupt-Überschrift).

## Aufbau eines HTML-Dokuments

Ganz oben, auf der ersten Zeile, steht immer:
```html
<!DOCTYPE html>
```
Das deklariert das Format des HTML-Dokuments.

![[html-struktur.svg]]

- Alles, was im `<head>` steht, ist **nicht** auf der Website sichtbar – hier speichert man gewöhnlich Metadaten, z. B.:
  ```html
  <meta charset="UTF-8">
  <meta name="Author" content="Tim Buergin">
  <meta name="description" content="This page shows all the things I am learning with html.">
  ```
- Man sollte beim `<html>`-Tag `lang="en"` (oder `lang="de"`) angeben, damit klar ist, in welcher Sprache der Inhalt verfasst ist:
  ```html
  <html lang="en">
  ```

### Favicon

> Das Element, das neben dem Tab-Symbol im Browser angezeigt wird, setzt man über:
> ```html
> <link rel="icon" href="gaming_pc.png" type="image/x-icon">
> ```
> `rel` steht für **relation** (Beziehung) – es sagt dem Browser, in welcher Beziehung die verlinkte Datei zur Seite steht.

![[favicon-beispiel.svg]]

## Markup validieren (W3C)

Man kann seine HTML-Dateien (z. B. aus Visual Studio Code) beim **W3C Markup Validation Service** hochladen und auf "Check" klicken. Man bekommt dann Fehlermeldungen (Errors) und Warnungen/Hinweise zum eigenen Code angezeigt – sehr nützlich, um sauberes HTML zu schreiben.

![[w3c-validator.jpg]]

> [!tip] Link: [validator.w3.org](https://validator.w3.org)

## Siehe auch
- [[CSS Grundlagen]]
- [[Wie das Web funktioniert]]
