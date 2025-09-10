# Speichermedien (HDD, SSD, NVMe)
## Theorie: Speichermedien

Hier geht es um die drei wichtigsten Arten von Massenspeichern in modernen Computern.

### 1. HDD (Hard Disk Drive)

* **Wie funktioniert sie?** **Mechanisch**. Eine oder mehrere magnetische Scheiben drehen sich, und ein Schreib-/Lesekopf bewegt sich darüber, um Daten zu lesen oder zu schreiben.
* **Vorteile:**
    * **Günstig:** Bietet sehr viel Speicherplatz für wenig Geld.
    * **Hohe Kapazitäten:** Ideal für große Datenarchive.
* **Nachteile:**
    * **Langsam:** Der mechanische Zugriff auf die Daten dauert vergleichsweise lange.
    * **Empfindlich:** Anfällig für Erschütterungen und Stöße.
    * **Laut:** Die beweglichen Teile erzeugen Betriebsgeräusche.

---

### 2. SSD (Solid State Drive)

* **Wie funktioniert sie?** **Elektronisch**. Daten werden auf Flash-Speicherchips (ähnlich wie bei einem USB-Stick) gespeichert, ohne bewegliche Teile.
* **Vorteile:**
    * **Sehr schnell:** Deutlich schnellere Lese- und Schreibzeiten als eine HDD.
    * **Robust:** Unempfindlich gegenüber Erschütterungen.
    * **Lautlos** und energieeffizient.
* **Nachteile:**
    * **Teurer** pro Gigabyte als eine HDD.
    * Begrenzte Anzahl an Schreibzyklen.

---

### 3. NVMe-SSD (Non-Volatile Memory Express)

* **Wie funktioniert sie?** Auch eine SSD, aber mit einer viel schnelleren Anbindung. Sie wird direkt über den **PCIe-Bus** mit dem Prozessor verbunden, ähnlich wie eine Grafikkarte.
* **Vorteile:**
    * **Extrem schnell:** Die schnellste verfügbare Speichertechnologie.
    * **Kompakte Bauform** (meist im M.2-Format).
* **Nachteile:**
    * **Am teuersten.**
    * Erzeugt unter Last mehr Wärme.

---

## Aufgaben & Lösungen

#### Aufgabe: Nennen Sie drei Vorteile einer SSD gegenüber einer HDD.

**Lösung:**

* **Schnellere Datenzugriffszeiten:** Das Betriebssystem startet schneller und Programme laden zügiger.
* **Höhere Stoßfestigkeit:** Da eine SSD keine beweglichen Teile hat, ist sie unempfindlich gegenüber Erschütterungen.
* **Geräuschloser Betrieb:** Eine SSD arbeitet lautlos, während eine HDD hörbare Betriebsgeräusche erzeugt.

---

#### Aufgabe: Es bieten sich eine externe Festplatte (HD) oder ein Solid State Drive (SSD) an. Beantworten Sie folgende Fragen mit Ja oder Nein.

**Lösung (Auszug):**

* Solid State Drives sind mindestens doppelt so schnell wie konventionelle Festplatten. → **Ja.**
* Festplatten sind resistenter gegen Erschütterungen als Solid State Drives. → **Nein.**
* Festplatten sind deutlich lauter im Betrieb als Solid State Drives. → **Ja.**

---

#### Aufgabe: Nennen Sie einen Vorteil und einen Nachteil einer M.2 SSD gegenüber einer SATA SSD.

**Lösung:**

* **Vorteil:** Eine M.2 SSD (insbesondere eine NVMe M.2) bietet **deutlich höhere Übertragungsgeschwindigkeiten** als eine SATA SSD, da sie direkt über den schnellen PCIe-Bus angebunden ist.
* **Nachteil:** M.2 SSDs sind in der Regel **teurer** als SATA SSDs mit der gleichen Speicherkapazität.
