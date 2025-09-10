# Betriebssysteme & Softwareinstallation

## Theorie: Betriebssysteme & Softwareinstallation

### 1. Das Betriebssystem (BS)

**Was ist das?** Das Betriebssystem ist die zentrale Software, die die **Hardware eines Computers verwaltet** und als Schnittstelle zwischen dem Benutzer und der Hardware dient.

#### Kernaufgaben:
* **Prozessverwaltung:** Steuert, welche Programme wann auf dem Prozessor (CPU) laufen.
* **Speicherverwaltung:** Organisiert den Hauptspeicher (RAM).
* **Dateisystemverwaltung:** Organisiert Daten in Ordnern und Dateien.
* **Geräteverwaltung:** Steuert alle angeschlossenen Geräte über Treiber.

### 2. Softwareinstallation

#### Manuelle vs. Automatisierte Installation:
* **Manuelle Installation:** Der Benutzer wird durch einen Assistenten geführt (`.exe`/`.msi`). Dies ist im privaten Umfeld üblich.
* **Automatisierte Installation (Paketmanager):** In der professionellen IT werden Kommandozeilen-Tools genutzt, um Software automatisiert zu installieren, zu aktualisieren und zu deinstallieren. Sie lösen Abhängigkeiten selbstständig auf.
    * **Linux:** `apt` (Debian/Ubuntu), `yum`/`dnf` (Red Hat/CentOS)
    * **Windows:** `winget`, `Chocolatey`

#### Softwarelizenzen:
* **Proprietäre Software:** Der Quellcode ist nicht öffentlich, die Nutzung ist oft kostenpflichtig (z.B. Microsoft Windows).
* **Open Source Software:** Der Quellcode ist frei zugänglich und darf verändert werden (z.B. Linux). Die wichtigste Lizenz ist die **GPL** (General Public License), die das "Copyleft"-Prinzip nutzt.
* **Freeware:** Kostenlos nutzbar, aber nicht veränderbar.
* **Shareware:** Für einen Testzeitraum kostenlos nutzbar.

---

## Prüfungsaufgaben (Original)

#### Quelle: IHK-Abschlussprüfung Frühjahr 2023, Teil 1, Aufgabe 3a
> **Aufgabe:** Benennen Sie im Schalenmodell eine Schicht oberhalb und eine unterhalb des Betriebssystems und beschreiben Sie ihre Funktion.

**Lösung:**
* **Schicht oberhalb:** **Anwendungssoftware** (z.B. Textverarbeitung).
    * **Funktion:** Sie stellt dem Benutzer spezifische Funktionen zur Verfügung, um Aufgaben zu erledigen.
* **Schicht unterhalb:** **Hardware** (z.B. CPU, RAM).
    * **Funktion:** Sie stellt die physischen Ressourcen zur Verfügung, die vom Betriebssystem verwaltet werden.

---

#### Quelle: IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 1c
> **Aufgabe:** Begründen Sie die Maßnahme: "Nutzung einer Minimalkonfiguration mit festgelegter Anwendungssoftware" für einen Präsentationsrechner.

**Lösung:**
Eine Minimalkonfiguration **reduziert die Angriffsfläche** des Systems. Je weniger Software installiert ist, desto weniger potenzielle Sicherheitslücken gibt es. Dies erhöht die **Sicherheit** und **Stabilität** des Rechners, da auch weniger Softwarekonflikte auftreten können.

---

#### Quelle: Lehrbuch, S. 74 (Adaptiert)
> **Aufgabe:** Definieren Sie die Begriffe Open Source und GNU/GPL.

**Lösung:**
* **Open Source:** Bezeichnet Software, deren Quelltext öffentlich zugänglich ist und von Dritten eingesehen, geändert und genutzt werden kann.
* **GNU/GPL (General Public License):** Ist die am weitesten verbreitete Lizenz für Open-Source-Software. Sie garantiert, dass die Software frei bleibt und verpflichtet jeden, der eine veränderte Version weitergibt, den Quellcode ebenfalls unter der GPL zu veröffentlichen (Copyleft-Prinzip).
