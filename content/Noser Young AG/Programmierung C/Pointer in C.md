---
tags: [programmierung, c, pointer, speicher]
datum: 20.11.2026
---

# Pointer in C

Noser Young Input: Heute ist das Thema **Pointer Teil 2**. Ein grosser Teil unseres Fokus liegt auf **Arrays und Pointern** und auf der **dynamischen Speicherallozierung** (Speicher im Heap).

## Was ist ein Pointer?
Ein Pointer ist eine **Variable, die die Speicheradresse einer anderen Variable enthält**. Man greift also nicht direkt auf den Wert zu, sondern über die **Adresse**, an der sich die Variable befindet.

Im übertragenen Sinn ist ein Pointer wie ein **Finger, der auf die Wohnadresse einer Variable zeigt**.

![[pointer-adresse.svg]]

```c
int i = 5;
int *p_i = &i;
```
- `&i` holt die **Adresse** von `i` heraus (Adressoperator).
- Das `=` speichert diese Adresse im Pointer `p_i`.
- `p_i` enthält danach also **nicht die 5**, sondern die Adresse von `i`.

## Die Operatoren `*` und `&`
Das `*` hat zwei Bedeutungen, je nachdem, wo es steht:

| Schreibweise | Bedeutung |
|---|---|
| `int *p_i;` | **Deklaration:** `p_i` ist ein Pointer auf einen `int` |
| `*p_i` | **Dereferenzieren:** zur Adresse gehen und den Wert dort lesen oder ändern |
| `&i` | **Adresse** der Variable `i` |
| `p_i` | die gespeicherte Adresse selbst |

```c
printf("%d\n", *p_i);   // gibt 5 aus
*p_i = 10;              // ändert i über den Pointer, i ist jetzt 10
printf("%p\n", (void *)p_i);   // gibt die Adresse aus, z. B. 0x7ffc10...
```

## Arrays und Pointer
Arrays und Pointer hängen eng zusammen: Der **Name eines Arrays** ist (fast immer) die **Adresse des ersten Elements**.
```c
int number[5] = {1, 2, 3, 4, 5};
int *p = number;        // gleich wie &number[0]

printf("%d\n", p[2]);       // 3
printf("%d\n", *(p + 2));   // auch 3, p + 2 springt 2 Elemente weiter
```
`p[i]` und `*(p + i)` bedeuten genau dasselbe. Darum kann man einen Pointer auf ein Array ganz normal mit `[ ]` benutzen. Mehr zu Arrays: [[Arrays in C]]

## Dynamische Speicherallozierung
Speicher im **Heap** muss man **selber reservieren (allozieren)** und **selber wieder freigeben**. Das macht C nicht automatisch.

![[stack-heap-malloc.svg]]

| Funktion | Was sie macht |
|---|---|
| `malloc(bytes)` | reserviert so viele **Bytes** im Heap und gibt die **Adresse** dieses Platzes zurück (als Pointer). Klappt es nicht, kommt `NULL` zurück. |
| `free(pointer)` | gibt den reservierten Platz wieder frei, sagt also: „Den brauche ich nicht mehr.“ |

Bei `malloc` muss man angeben, **wie gross** der benötigte Speicher ist, und zwar in **Bytes**. Am einfachsten geht das mit `sizeof`:
```c
int *zahlen = malloc(5 * sizeof(int));   // Platz für 5 ints (meist 5 × 4 = 20 Bytes)
```
Für `malloc` und `free` braucht es `#include <stdlib.h>`.

> [!important] Heap bleibt bestehen, aber nicht ewig
> Daten im Heap bleiben bestehen, **auch wenn die Funktion fertig ist**, in der sie erstellt wurden. Das ist der grosse Vorteil gegenüber normalen Variablen (Stack), die am Ende der Funktion verschwinden.
> Wenn man das **Programm schliesst**, gibt das Betriebssystem den ganzen Speicher aber wieder frei. Gespeichert wird also nichts dauerhaft, dafür braucht es Dateien ([[File Handling in C]]).

> [!warning] Nicht vergessen: `free`
> Vergisst man `free`, bleibt der Platz belegt, solange das Programm läuft (**Memory Leak**). Nach `free` sollte man den Pointer nicht mehr benutzen, am besten auf `NULL` setzen.

## Auftrag: getRandomNums
Wir sollen eine Funktion **getRandomNums** implementieren:
- Sie erzeugt **zufällige Zahlen zwischen 1 und 100**.
- Wir sollen dabei mit **`malloc`** arbeiten.
- Der **Rückgabewert ist ein Pointer**, der auf das Array zeigt, also weiss, wo im Heap die Zahlen gespeichert sind.

Hinweise:
- `rand() % 100` gibt 0 bis 99, mit `+ 1` werden es **1 bis 100**.
- `srand(time(NULL));` nur **einmal** am Anfang im `main` aufrufen, sonst kommen immer die gleichen Zahlen (braucht `#include <time.h>`).
- Das Array muss im **Heap** liegen. Ein normales `int zahlen[5];` in der Funktion wäre nach dem `return` weg, der Pointer würde dann ins Leere zeigen.

> [!example]- Lösungsbeispiel (erst selber probieren)
> ```c
> #include <stdio.h>
> #include <stdlib.h>
> #include <time.h>
>
> int *getRandomNums(int anzahl)
> {
>     int *zahlen = malloc(anzahl * sizeof(int));
>     if (zahlen == NULL)
>     {
>         return NULL;   // kein Speicher bekommen
>     }
>
>     for (int i = 0; i < anzahl; i++)
>     {
>         zahlen[i] = rand() % 100 + 1;   // 1 bis 100
>     }
>     return zahlen;   // Adresse vom Anfang des Arrays im Heap
> }
>
> int main(void)
> {
>     srand(time(NULL));   // nur einmal am Anfang
>
>     int anzahl = 5;
>     int *zahlen = getRandomNums(anzahl);
>     if (zahlen == NULL)
>     {
>         printf("Kein Speicher frei!\n");
>         return 1;
>     }
>
>     for (int i = 0; i < anzahl; i++)
>     {
>         printf("%d ", zahlen[i]);
>     }
>     printf("\n");
>
>     free(zahlen);    // Speicher zurückgeben
>     zahlen = NULL;   // Pointer zeigt jetzt auf nichts mehr
>     return 0;
> }
> ```
> Beispielausgabe: `52 51 91 3 83`

## Siehe auch
- [[Arrays in C]]
- [[Datentypen & Structs in C]]
- [[File Handling in C]] (dort ist `FILE *datei` auch ein Pointer)
