---
tags: [programmierung, c, dateien]
datum: 21.10.2026
---

# File Handling in C

**File Handling** (Datei-Verarbeitung) beschreibt, wie ein Programm Dateien auf der Festplatte **erstellt, liest, aktualisiert und löscht**. Es gehört zu den wichtigsten Grundlagen, weil fast jede echte Anwendung Daten dauerhaft speichern muss: Variablen sind nach dem Programmende weg, eine Datei bleibt.

> [!note] Wofür?
> Ausgangspunkt war eine Übersicht mit KI. Gebraucht wird das für den [[Auftrag 05 – Tabellengenerator]].

%% To-do: Take-away ins Arbeitsjournal übertragen %%

## Die vier Grundoperationen (CRUD)
| Operation | Bedeutung | In C |
|---|---|---|
| **C**reate | Datei erstellen | `fopen("datei.txt", "w")` |
| **R**ead | Datei lesen | `fopen("datei.txt", "r")` + `fgets` / `fscanf` |
| **U**pdate | Text anhängen oder ändern | `fopen("datei.txt", "a")` + `fprintf` |
| **D**elete | Datei löschen | `remove("datei.txt")` |

## Ablauf: öffnen, arbeiten, schliessen
```mermaid
flowchart LR
    A["fopen: Datei öffnen"] --> B{"NULL?"}
    B -- ja --> E["Fehler ausgeben"]
    B -- nein --> C["schreiben oder lesen"]
    C --> D["fclose: Datei schliessen"]
```

## Die wichtigsten Funktionen
| Funktion | Was sie macht |
|---|---|
| `FILE *datei` | Zeiger auf die geöffnete Datei, über ihn greift man auf die Datei zu |
| `fopen(name, modus)` | Öffnet oder erstellt eine Datei, gibt `NULL` zurück, wenn es nicht klappt |
| `fprintf(datei, ...)` | Schreibt wie `printf`, aber in die Datei |
| `fputs(text, datei)` | Schreibt einen Text in die Datei |
| `fgets(puffer, grösse, datei)` | Liest eine Zeile aus der Datei |
| `fscanf(datei, ...)` | Liest wie `scanf`, aber aus der Datei |
| `fclose(datei)` | Schliesst die Datei, erst dann ist sicher alles gespeichert |
| `remove(name)` | Löscht eine Datei |

## Modi bei `fopen`
| Modus | Bedeutung | Datei fehlt | Datei existiert |
|---|---|---|---|
| `"r"` | lesen (read) | Fehler, `NULL` | wird gelesen |
| `"w"` | schreiben (write) | wird erstellt | wird **überschrieben**, alter Inhalt ist weg |
| `"a"` | anhängen (append) | wird erstellt | neuer Text kommt ans Ende |
| `"r+"` | lesen und schreiben | Fehler, `NULL` | Inhalt bleibt |

## Beispiel: schreiben und wieder lesen
```c
#include <stdio.h>

int main(void) {
    FILE *datei = fopen("notizen.txt", "w");
    if (datei == NULL) {
        printf("Datei konnte nicht geoeffnet werden\n");
        return 1;
    }
    fprintf(datei, "Hallo Datei!\n");
    fclose(datei);

    char zeile[100];
    datei = fopen("notizen.txt", "r");
    if (datei == NULL) {
        return 1;
    }
    while (fgets(zeile, sizeof(zeile), datei) != NULL) {
        printf("%s", zeile);
    }
    fclose(datei);
    return 0;
}
```

> [!warning] Typische Fehler
> - `fclose` vergessen: Der Text wird eventuell nicht gespeichert.
> - `"w"` statt `"a"`: Der bestehende Inhalt wird gelöscht.
> - Nicht auf `NULL` prüfen: Das Programm stürzt ab, wenn die Datei nicht geöffnet werden kann.
> - Datei nicht gefunden: In CLion liegt sie im Ordner `cmake-build-debug` (siehe [[Auftrag 05 – Tabellengenerator]]).

## Siehe auch
- [[Auftrag 05 – Tabellengenerator]]
