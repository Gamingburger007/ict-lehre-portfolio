---
tags: [programmierung, c, arrays]
datum: 04.11.2026
---

# Arrays in C

Noser Young Input: Es geht um **Arrays**.

Ein Array ist wie eine Reihe von Kästchen unter **einem Namen**. Man benutzt es, um **mehrere Werte vom gleichen Datentyp** abzuspeichern, z. B. viele Zahlen (`int`) oder viele Buchstaben (`char`). So braucht man nicht für jeden Wert eine eigene Variable.

## Ein Array erstellen (1D)
Ein neues Array erstelle ich so:
```c
int number[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```
- `int` = Datentyp der Werte
- `number` = Name des Arrays
- `[10]` = Grösse, also wie viele Werte reinpassen

Wenn ich die **1** aus dem Array haben möchte, muss ich den **Index 0** angeben, da man bei **0** beginnt zu zählen. Der letzte Index ist darum **Grösse − 1**, hier also `number[9]` → 10.

![[array-1d-index.svg]]

```c
printf("%d", number[0]);   // gibt 1 aus
printf("%d", number[9]);   // gibt 10 aus
```

> [!warning] Nicht über das Array hinaus
> `number[10]` gibt es **nicht**. C meldet dabei keinen Fehler, sondern liest einfach irgendeinen Wert aus dem Speicher. Das gibt komische Ergebnisse oder Abstürze.

## 2D-Arrays
Wir schauen uns auch 2D-Arrays an. Ein 2D-Array funktioniert ein wenig anders: Es ist wie eine **Tabelle** mit Zeilen und Spalten.
```c
int arr2[2][3] = {{1, 2, 3}, {4, 5, 6}};
```
- Die **erste Zahl** gibt an, wie viele **Zeilen** es gibt (hier 2).
- Die **zweite Zahl** gibt an, wie viele **Spalten** jede Zeile hat (hier 3).
- Jede innere `{ }` ist eine Zeile, dazwischen braucht es ein **Komma**.

> [!important] Zuerst Zeile, dann Spalte
> `arr2[Zeile][Spalte]`. Also zuerst nach unten zur richtigen Zeile, dann nach rechts zur Spalte, wie in einer Excel-Tabelle.

![[array-2d-tabelle.svg]]

## Werte lesen und ändern
```c
printf("%d", arr2[0][1]);   // Zeile 0, Spalte 1 → gibt 2 aus
arr2[1][1] = 9;             // Zeile 1, Spalte 1: aus der 5 wird eine 9
```
Zwischen den Klammern kommt **kein Punkt**: richtig ist `arr2[0][1]`, nicht `arr2[0].[1]`.

## Alles auf 0 setzen
```c
int arr3[2][3] = {{0}};
```
Damit wird ein **Standardwert** (0) in jedes Feld der Tabelle gesetzt. Gibt man nur einen Teil der Werte an, füllt C den Rest automatisch mit 0 auf.

## Ganzes 2D-Array ausgeben
Mit zwei verschachtelten `for`-Schleifen geht man jede Zeile und darin jede Spalte durch:
```c
for (int zeile = 0; zeile < 2; zeile++)
{
    for (int spalte = 0; spalte < 3; spalte++)
    {
        printf("%d ", arr2[zeile][spalte]);
    }
    printf("\n");
}
```
Ausgabe:
```
1 2 3
4 9 6
```

## Siehe auch
- [[Binäre Suche]] (sucht eine Zahl in einem sortierten Array)
- [[Auftrag 05 – Tabellengenerator]]
- [[Auftrag – Schiebepuzzle (Sliding Puzzle)]] (2D-Array als Spielfeld)
