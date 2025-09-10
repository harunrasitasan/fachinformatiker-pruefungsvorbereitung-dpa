# Projektmanagement - Projektplanung (Gantt & Netzplan)

### Theorie: Projekte visuell planen

In der Prüfung musst du den zeitlichen Ablauf eines Projekts planen und die Abhängigkeiten zwischen Aufgaben verstehen können. Dafür gibt es zwei wichtige Werkzeuge: das Gantt-Diagramm und den Netzplan.

### 1. Das Gantt-Diagramm: Der schnelle Überblick

Ein **Gantt-Diagramm** ist eine einfache, visuelle Zeitleiste für ein Projekt. Es zeigt auf einen Blick, wann welche Aufgabe beginnt, wie lange sie dauert und wann sie endet.

* **Aufbau:** Links stehen die Aufgaben (Vorgänge), oben ist eine Zeitleiste (Tage, Wochen). Jede Aufgabe wird als Balken dargestellt.
* **Vorteil:** Sehr einfach zu lesen und zu verstehen, ideal für Präsentationen.
* **Nachteil:** Zeigt logische Abhängigkeiten nicht so klar wie ein Netzplan.

### 2. Der Netzplan: Die detaillierte Analyse (Prüfungs-Schwerpunkt)

Der **Netzplan** ist die Methode, die in der Prüfung am häufigsten und detailliertesten abgefragt wird. Er zeigt exakte logische Abhängigkeiten und berechnet mögliche Zeitpuffer.

#### Der Vorgangsknoten: Das Herzstück des Netzplans
Jeder Vorgang wird in einem Knoten dargestellt, der immer gleich aufgebaut ist:

| FAZ | FEZ |
| :---: | :---: |
| **Vorgang** |
| Dauer | GP | FP |
| SAZ | SEZ |

* **FAZ (Frühester Anfangszeitpunkt):** Wann kann der Vorgang frühestens beginnen?
* **FEZ (Frühester Endzeitpunkt):** Wann ist der Vorgang frühestens fertig?
* **SAZ (Spätester Anfangszeitpunkt):** Wann muss der Vorgang spätestens beginnen, um das Projekt nicht zu verzögern?
* **SEZ (Spätester Endzeitpunkt):** Wann muss der Vorgang spätestens fertig sein?
* **GP (Gesamtpuffer):** Wie viel Zeitpuffer hat dieser Vorgang insgesamt?
* **FP (Freier Puffer):** Wie viel Zeitpuffer hat der Vorgang, ohne den Start des *direkten Nachfolgers* zu verschieben?

#### Der Kritische Pfad: Hier darf nichts schiefgehen!
Der **Kritische Pfad** ist die Kette von Vorgängen, bei denen **alle Pufferzeiten (GP und FP) gleich Null** sind.
* **Bedeutung:** Jeder Vorgang auf diesem Pfad ist "kritisch". Eine Verzögerung hier führt **unmittelbar** zu einer Verzögerung des gesamten Projekts und gibt die Mindestprojektdauer an.

---

### Rezept für die Prüfung: Den Netzplan in 5 Schritten lösen

1.  **Struktur aufbauen:** Zeichne alle Vorgangsknoten und verbinde sie mit Pfeilen gemäß der Vorgänger-Tabelle. Trage die **Dauer** in jeden Knoten ein.
2.  **Vorwärtsterminierung (links nach rechts):** Berechne **FAZ** und **FEZ**.
    * `FEZ = FAZ + Dauer`
    * `FAZ (Nachfolger) = FEZ (Vorgänger)`. Bei mehreren Vorgängern nimm den **höchsten** FEZ-Wert.
3.  **Rückwärtsterminierung (rechts nach links):** Berechne **SAZ** und **SEZ**.
    * Beim letzten Vorgang ist `SEZ = FEZ`.
    * `SAZ = SEZ - Dauer`
    * `SEZ (Vorgänger) = SAZ (Nachfolger)`. Bei mehreren Nachfolgern nimm den **niedrigsten** SAZ-Wert.
4.  **Puffer berechnen:**
    * Gesamtpuffer: `GP = SAZ - FAZ`
    * Freier Puffer: `FP = FAZ (nächster) - FEZ (aktueller)`
5.  **Kritischen Pfad markieren:** Identifiziere und markiere die Kette aller Vorgänge, bei denen **GP und FP gleich 0** sind.

---

### Prüfungsaufgaben (Original)

Der Netzplan ist ein absoluter Klassiker in der Prüfung.

#### Quelle: IHK-Abschlussprüfung Herbst 2021, Teil 1, Aufgabe 1c & 1d

> **Aufgabe:** Vervollständigen Sie einen fast leeren Netzplan, indem Sie die Vorwärts- und Rückwärtsterminierung sowie die Pufferzeiten berechnen. Markieren Sie anschließend den kritischen Pfad.
>
> **Lösungsweg:** Hier musste das oben beschriebene 5-Schritte-Rezept exakt angewendet werden. Die Prüfung testet hier rein methodisches Wissen. Der kritische Pfad wurde durch die Vorgänge mit `GP = 0` und `FP = 0` identifiziert und lautete: **A → B → D → G → I → J → K**.

#### Quelle: IHK-Abschlussprüfung Frühjahr 2025, Teil 1, Aufgabe 3a

> **Aufgabe:** Ähnlich wie 2021, ein unvollständiger Netzplan musste komplett berechnet und der kritische Pfad benannt werden.
>
> **Lösungsweg:** Erneut wurde das 5-Schritte-Rezept angewendet. Der kritische Pfad in dieser Aufgabe lautete: **A → B → D → E → I → J**.

**Tipp für die Prüfung:** Übe die Vorwärts- und Rückwärtsterminierung, bis du sie im Schlaf kannst. Es ist eine rein mechanische Rechenaufgabe, bei der du leicht Punkte sammeln kannst, wenn du die Regeln kennst – insbesondere die **"höchster FEZ vorwärts, niedrigster SAZ rückwärts"**-Regel bei Verzweigungen.
