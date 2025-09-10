# Datenbankmodellierung

## Theorie: Datenbankmodellierung

Das Ziel der Datenbankmodellierung ist es, Daten und ihre Beziehungen zueinander **strukturiert und redundanzfrei** darzustellen. Das wichtigste Werkzeug dafür ist das **Entity-Relationship-Modell (ERM)**.

### Die Bausteine eines ER-Modells

* **Entität (Entity):** Ein "Ding", über das Informationen gespeichert werden sollen (z.B. **Kunde**, **Auftrag**).
* **Attribut (Attribute):** Eine Eigenschaft, die eine Entität beschreibt (z.B. für **Kunde**: KundenNr, Name).
* **Primärschlüssel (Primary Key / PK):** Ein Attribut, das eine Entität **eindeutig identifiziert** (z.B. **KundenNr**).
* **Beziehung (Relationship):** Beschreibt die Verbindung zwischen Entitäten (z.B. Ein **Kunde** *erteilt* einen **Auftrag**).

### Kardinalitäten: Die Beziehungsregeln

Sie geben an, *wie viele* Entitäten miteinander in Beziehung stehen können.

* **1:1 (Eins-zu-Eins):** Ein Mitarbeiter hat genau ein Firmenfahrzeug.
* **1:n (Eins-zu-Viele):** Ein Kunde kann **viele** Aufträge haben, aber jeder Auftrag gehört zu genau **einem** Kunden. (Dies ist der häufigste Fall!)
* **n:m (Viele-zu-Viele):** **Viele** Schüler besuchen **viele** Kurse.

### Die Auflösung von n:m-Beziehungen (Prüfungs-Tipp)

Eine **n:m-Beziehung** kann nicht direkt in Datenbanktabellen abgebildet werden. Man muss sie auflösen:

* **Wie?** Man erstellt eine **dritte Tabelle**, die sogenannte **Beziehungs- oder Verknüpfungstabelle**.
* **Was kommt da rein?** Diese Tabelle enthält nur die **Primärschlüssel** der beiden Entitäten, die sie verbindet. Diese beiden Schlüssel werden zu **Fremdschlüsseln (Foreign Keys / FK)** und bilden zusammen den neuen Primärschlüssel der Verknüpfungstabelle.

**Beispiel:** "Viele Schüler besuchen viele Kurse" wird zu:
1.  Tabelle `Schüler` (mit `Schueler_ID` als PK)
2.  Tabelle `Kurse` (mit `Kurs_ID` als PK)
3.  **Neue Tabelle `Schueler_Kurse`** (mit `Schueler_ID` und `Kurs_ID` als FKs und zusammengesetztem PK)

Damit wandelt man die eine n:m-Beziehung in **zwei 1:n-Beziehungen** um.

---

## Prüfungsaufgaben (Original)

#### Quelle: IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 4b

> **Aufgabe:** Erweitern Sie das Datenmodell redundanzfrei. Jeder Auftrag wird von genau einem Mitarbeiter bearbeitet. Erfassen Sie Name, Vorname des Mitarbeiters sowie Beginn und Ende der Bearbeitung.

**Lösungsweg:**
* Es gibt zwei Entitäten: **Mitarbeiter** und **Auftrag**.
* Die Beziehung ist "bearbeitet". Da ein Mitarbeiter viele Aufträge haben kann, aber jeder Auftrag nur von einem Mitarbeiter bearbeitet wird, ist die Kardinalität **1:n** (aus Sicht von Mitarbeiter zu Auftrag).
* Um die 1:n-Beziehung herzustellen, wird der Primärschlüssel der '1'-Seite (**Mitarbeiter-ID**) als **Fremdschlüssel** in die 'n'-Seite (**Auftrag**) aufgenommen.

**Ergebnis im ER-Modell:**
* **Entität `Mitarbeiter`:** mit Attributen `Mitarbeiter-ID` (PK), `Name`, `Vorname`.
* **Entität `Auftrag`:** mit Attributen `Auftrag-ID` (PK), `Bearbeitung_Beginn`, `Bearbeitung_Ende` und dem Fremdschlüssel `Mitarbeiter-ID`.
