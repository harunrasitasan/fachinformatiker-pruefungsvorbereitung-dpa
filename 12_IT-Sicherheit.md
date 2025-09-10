# IT-Sicherheit

## Theorie: IT-Sicherheit

Das Ziel der IT-Sicherheit ist es, die drei grundlegenden **Schutzziele** der Informationssicherheit für IT-Systeme und Daten zu gewährleisten:

* **Vertraulichkeit:** Nur befugte Personen dürfen auf Daten zugreifen.
    * *Maßnahmen:* Verschlüsselung, Zugriffskontrollen, Passwortrichtlinien.
* **Integrität:** Daten müssen korrekt und vollständig bleiben und dürfen nicht unbemerkt verändert werden.
    * *Maßnahmen:* Hashwerte, digitale Signaturen, Berechtigungskonzepte.
* **Verfügbarkeit:** IT-Systeme und Daten müssen bei Bedarf für berechtigte Nutzer funktionsfähig sein.
    * *Maßnahmen:* Backups, redundante Systeme (z.B. RAID), Virenschutz.

### Die Praxis: Schutzbedarfsfeststellung nach BSI IT-Grundschutz

Um zu entscheiden, wie stark ein System geschützt werden muss, führt man eine **Schutzbedarfsfeststellung** durch. Dabei wird für jedes Schutzziel bewertet, wie hoch der Schaden bei einer Verletzung wäre. Die Bewertung erfolgt meist in drei Stufen:

* **Normal:** Ein Schaden wäre ärgerlich, aber verkraftbar.
* **Hoch:** Ein Schaden wäre beträchtlich und teuer.
* **Sehr hoch:** Ein Schaden wäre existenzbedrohend.

**Beispiel:** Für einen **Online-Shop** wäre die **Verfügbarkeit "sehr hoch"** (jeder Ausfall kostet Geld), die **Integrität der Bestelldaten "hoch"** und die **Vertraulichkeit der öffentlichen Produktbilder "normal"**.

### Typische Bedrohungen (Malware)

* **Viren:** Nisten sich in andere Dateien ein, um sich zu verbreiten.
* **Würmer:** Verbreiten sich selbstständig über Netzwerke.
* **Trojaner:** Tarnen sich als nützliche Programme, führen aber schädliche Aktionen aus.
* **Ransomware:** Verschlüsselt Daten und fordert Lösegeld für die Entschlüsselung.
* **Phishing:** Versuch, über gefälschte E-Mails oder Webseiten an sensible Daten (z.B. Passwörter) zu gelangen.

### Wichtige Abwehrmaßnahmen

* **Firewall:** Kontrolliert den Netzwerkverkehr und blockiert unerwünschte Verbindungen.
* **Virenschutz:** Erkennt und entfernt bekannte Malware.
* **Backups:** Regelmäßige Datensicherungen zur Wiederherstellung nach einem Datenverlust.
* **Updates/Patch-Management:** Schließt bekannte Sicherheitslücken in Software.

---

## Prüfungsaufgaben (Original)

#### Quelle: IHK-Abschlussprüfung Frühjahr 2024, Teil 1, Aufgabe 1c

> **Aufgabe:** Begründen Sie die Maßnahme: "Anschluss eines Präsentationsrechners an ein vom LAN der Institution getrenntes Datennetz".

**Lösung:**
Der Anschluss an ein separates Netzwerk **isoliert den Präsentationsrechner** vom internen Firmennetz. Sollte der Rechner (z. B. durch einen USB-Stick eines Gastes) mit Malware infiziert werden, kann sich diese **nicht auf die kritischen Server und Arbeitsplätze im Firmennetz ausbreiten**. Dies schützt die **Vertraulichkeit** und **Integrität** der internen Unternehmensdaten.

---

#### Quelle: IHK-Abschlussprüfung Herbst 2021, Teil 1, Aufgabe 4a

> **Aufgabe:** Ordnen Sie die Sicherheitsmaßnahme dem richtigen Schutzziel zu und begründen Sie es. Maßnahme: Regelmäßige Datensicherung der Patientendaten.

**Lösung:**
* **Schutzziel:** **Verfügbarkeit**.
* **Begründung:** Durch eine regelmäßige Datensicherung wird sichergestellt, dass die Patientendaten auch nach einem Systemausfall, einem Angriff oder versehentlichem Löschen schnell wiederhergestellt werden können und somit für die berechtigten Personen verfügbar sind.

---

#### Quelle: IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 3cb

> **Aufgabe:** Nennen Sie drei Anzeichen, an denen ein User erkennen kann, dass es sich um eine Phishing-Mail handelt.

**Lösung:**
1.  **Absenderadresse:** Die E-Mail-Adresse des Absenders wirkt unseriös, enthält Tippfehler oder passt nicht zum angeblichen Unternehmen (z.B. `paypal@service123.com`).
2.  **Unpersönliche Anrede & Grammatikfehler:** Allgemeine Anreden wie "Sehr geehrter Kunde" und auffällige Rechtschreib- oder Grammatikfehler.
3.  **Dringender Handlungsbedarf & Drohungen:** Die Mail erzeugt Druck (z.B. "Ihr Konto wird in 24 Stunden gesperrt...") und fordert zum Klick auf einen verdächtigen Link auf.
