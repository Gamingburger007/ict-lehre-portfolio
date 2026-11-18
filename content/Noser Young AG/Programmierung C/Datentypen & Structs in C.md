---
tags: [programmierung, c, datentypen, structs]
datum: 18.11.2026
---

# Datentypen & Structs in C

Repetition der Datentypen und neu: **Structs**, mit denen man eigene Datentypen baut. Das brauchen wir für den **Auftrag Personen-Manager**, der uns am 18.11. den ganzen Tag beschäftigt hat.

## Datentypen (Repetition)
| Datentyp | Was er speichert | Beispiel | Format-Specifier |
|---|---|---|---|
| `short` | kleine Ganzzahl | `short s = 120;` | `%hd` |
| `int` | Ganzzahl | `int alter = 16;` | `%d` |
| `long` | grosse Ganzzahl | `long l = 100000L;` | `%ld` |
| `long long` | sehr grosse Ganzzahl | `long long ll = 9000000000LL;` | `%lld` |
| `float` | Kommazahl, weniger genau | `float pi = 3.14f;` | `%f` |
| `double` | Kommazahl, doppelt so genau | `double d = 3.14159;` | `%lf` (bei `scanf`) |
| `char` | ein einzelnes Zeichen | `char c = 'a';` | `%c` |
| `char[]` | Text (char-Array) | `char name[] = "Tim";` | `%s` |
| `bool` | wahr oder falsch (`true` / `false`) | `bool fertig = false;` | `%d` |

> [!important] `bool` braucht eine Bibliothek
> In C gibt es `bool`, `true` und `false` erst mit `#include <stdbool.h>`.

## Char-Arrays und `\0`
Ein Text ist in C ein **Array aus `char`** (siehe [[Arrays in C]]). Am Ende steht immer das Zeichen **`\0`**: Es zeigt an, wo der Text **zu Ende** ist. Darum braucht das Array **ein Feld mehr**, als der Text Buchstaben hat.

```c
char test[6 + 1] = "abcdef";                          // 6 Buchstaben + 1 Feld für \0
char test2[6 + 1] = {'a', 'b', 'c', 'd', 'e', 'f', '\0'}; // gleich, nur von Hand
```

| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|---|
| Inhalt | `a` | `b` | `c` | `d` | `e` | `f` | `\0` |

> [!warning] Häufiger Fehler
> Bei `"abcdef"` hängt C das `\0` automatisch an. Ist das Array zu klein (`char test[6]`), fehlt der Platz dafür und `printf("%s", test)` gibt Müll aus.

## Structs: eigene Datentypen
Mit einem **Struct** kann man mehrere Werte, die zusammengehören, unter **einem Namen** speichern, auch mit verschiedenen Datentypen. So entsteht ein **eigener Datentyp**.

```c
struct Coordinates {
    int x;
    int y;
};

struct Coordinates coords1;   // eine Variable vom neuen Typ
coords1.x = 5;                 // mit dem Punkt spricht man x an
coords1.y = 2;                 // und so y
printf("x = %d, y = %d\n", coords1.x, coords1.y);
```

- Mit dem **Punkt** (`coords1.x`) greift man auf ein Feld des Structs zu und kann ihm einen **neuen Wert** geben.
- Der Struct-Name wird in **PascalCasing** geschrieben (`Coordinates`), die Variablen in camelCasing.

### Beispiel für den Personen-Manager
```c
struct Person {
    char vorname[50];
    char nachname[50];
    int alter;
};

struct Person p1 = {"Anna", "Muster", 17};
printf("%s %s ist %d Jahre alt\n", p1.vorname, p1.nachname, p1.alter);
```

> [!tip] Viele Personen speichern
> Mehrere Personen passen in ein **Array aus Structs**: `struct Person personen[10];` und dann `personen[0].alter = 17;`.

## Siehe auch
- [[Arrays in C]]
- [[Modulares Programmieren]]
- [[File Handling in C]] (Personen in einer Datei speichern)
