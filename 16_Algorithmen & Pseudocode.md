# Algorithmen & Pseudocode

## Theorie: Logische Abläufe planen

Bevor man Code schreibt, muss man den logischen Ablauf einer Lösung planen. Dafür nutzt man Algorithmen, die oft in Pseudocode oder als Struktogramm dargestellt werden.

### 1. Was ist ein Algorithmus?

Ein **Algorithmus** ist eine **eindeutige, schrittweise Anleitung** zur Lösung eines Problems. Stell es dir wie ein Kochrezept vor: Jeder Schritt ist klar definiert und die Reihenfolge ist festgelegt, um am Ende immer zum gleichen Ergebnis zu kommen.

### 2. Was ist Pseudocode?

**Pseudocode** ist eine informelle, textbasierte Beschreibung eines Algorithmus. Er ist eine Mischung aus normaler menschlicher Sprache und Elementen einer Programmiersprache.

* **Zweck:** Den logischen Ablauf eines Programms zu planen und zu dokumentieren, ohne sich um die genaue Syntax einer bestimmten Programmiersprache kümmern zu müssen.
* **Vorteil:** Er ist für jeden (auch Nicht-Programmierer) leicht verständlich und kann einfach in jede beliebige Programmiersprache übersetzt werden.

**Wichtige Elemente im Pseudocode:**
* **Variablen:** `Variable_A = 10`
* **Schleifen:** `FÜR i VON 1 BIS 10 ... ENDE FÜR` oder `SOLANGE Bedingung ... ENDE SOLANGE`
* **Bedingungen:** `WENN Bedingung DANN ... SONST ... ENDE WENN`
* **Funktionsaufrufe:** `ergebnis = BERECHNE_SUMME(a, b)`

---

## Prüfungsaufgaben (Original)

In der Prüfung musst du oft Pseudocode lesen, verstehen und das Ergebnis eines Funktionsaufrufs ermitteln ("Schreibtischtest").

#### Quelle: IHK-Abschlussprüfung Frühjahr 2025, Teil 1, Aufgabe 3d

> **Aufgabe:** Sie werden beauftragt, einen Schreibtischtest durchzuführen. Berechnen Sie die drei Rückgabewerte des folgenden Funktionsaufrufs.
>
> **Pseudocode:**
> ```
> funktion analytics_berechnen(besucher, seitenaufrufe, besucherSuchmaschinen, anzahlBounces):
>     durchschnittSeitenaufrufeProBesucher = seitenaufrufe / besucher
>     prozentsatzSuchmaschinenBesucher = (besucherSuchmaschinen / besucher) * 100
>     nonBounceRate = ((besucher - anzahlBounces) / besucher) * 100
>     RÜCKGABE (durchschnittSeitenaufrufeProBesucher, prozentsatzSuchmaschinenBesucher, nonBounceRate)
> ```
> **Aufruf:** `ergebnis = analytics_berechnen(12000, 33000, 5562, 7554)`

**Schritt-für-Schritt-Lösung:**
1.  **Durchschnittliche Seitenaufrufe:**
    `33000 / 12000 = 2.75`
2.  **Prozentsatz Suchmaschinenbesucher:**
    `(5562 / 12000) * 100 = 0.4635 * 100 = 46.35`
3.  **Non-Bounce-Rate:**
    `((12000 - 7554) / 12000) * 100 = (4446 / 12000) * 100 = 0.3705 * 100 = 37.05`

**Endergebnis:**
* Durchschnittliche Seitenaufrufe pro Besucher: **2,75**
* Prozentsatz der Besucher, die über Suchmaschinen kommen: **46,35 %**
* Non-Bounce-Rate: **37,05 %**

---

#### Quelle: IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 2e

> **Aufgabe:** Ermitteln und begründen Sie den Rückgabewert, der bei Aufruf der Funktion mit `id = 3` und `roomNr = 236` geliefert wird.
>
> **Pseudocode:**
> ```
> Funktion checkAuthority(id, roomNr)
>     Für i von 0 bis (AnzahlZeilen von keyData)
>         Für j von 1 bis (AnzahlBelegteSpalten von keyData)
>             Wenn id gleich keyData[i][0] UND roomNr gleich keyData[i][j] dann
>                 Rückgabe Wahr
>             Ende Wenn
>         Ende Für
>     Ende Für
>     Rückgabe Falsch
> Ende Funktion
> ```
> **Daten-Array `keyData` (Auszug):**
> | Mitarbeiter-ID | Room1 | Room2 | Room3 | ... |
> | :---: | :---: | :---: | :---: | :---: |
> | 1 | 223 | 312 | ... | 236 |
> | 2 | 103 | 401 | ... | 236 |
> | 3 | 20 | 312 | 235 | ... |

**Schritt-für-Schritt-Lösung (Logik des Algorithmus):**
1.  Die äußere Schleife (`Für i...`) geht die Zeilen des Arrays durch, um den richtigen Mitarbeiter zu finden.
2.  Wenn die `id` (hier: 3) in der ersten Spalte `keyData[i][0]` gefunden wird, startet die innere Schleife (`Für j...`).
3.  Die innere Schleife durchsucht nun alle weiteren Spalten dieser Zeile und vergleicht die Raumnummern mit der `roomNr` (hier: 236).
4.  **Schreibtischtest:**
    * Die äußere Schleife findet in der dritten Zeile die `id = 3`.
    * Die innere Schleife prüft die Räume für Mitarbeiter 3: `20`, `312`, `235`, ...
    * Der gesuchte Raum `236` ist in dieser Zeile **nicht enthalten**.
5.  Die Schleifen laufen komplett durch, ohne dass die `Wenn`-Bedingung jemals `Wahr` wird.
6.  Nachdem die Schleifen beendet sind, wird die letzte Anweisung der Funktion ausgeführt: `Rückgabe Falsch`.

**Endergebnis:** Der Rückgabewert ist **Falsch**.
