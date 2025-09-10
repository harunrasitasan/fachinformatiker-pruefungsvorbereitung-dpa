# Netzwerktechnik – OSI-Modell

## Theorie-Überblick

[cite_start]Das **OSI-Modell (Open Systems Interconnection Model)** ist ein Referenzmodell, das die Netzwerkkommunikation in **sieben abstrakte Schichten (Layers)** unterteilt. [cite: 3372, 3376] Es dient als theoretische Grundlage, um die Funktionen und Protokolle der Datenübertragung zu strukturieren und zu verstehen. [cite_start]Jede Schicht hat eine klar definierte Aufgabe und übergibt ihre Daten an die darunterliegende Schicht. [cite: 3377]

### Die 7 Schichten (von oben nach unten)

| Schicht | Name (Deutsch/Englisch) | Hauptaufgabe & Protokolle | Adressen/Einheit |
|:---:|:---|:---|:---|
| **7** | **Anwendung (Application)** | Bereitstellung von Netzwerkdiensten für Anwendungen. [cite_start]**Protokolle:** HTTP, FTP, SMTP, DNS, DHCP. [cite: 3383, 3411] | Daten |
| **6** | **Darstellung (Presentation)** | Umwandlung und Übersetzung der Daten in ein unabhängiges Format (z.B. Verschlüsselung, Komprimierung). [cite_start]**Protokolle:** SSL/TLS, XDR. [cite: 3387, 3388, 3411] | Daten |
| **5** | **Sitzung (Session)** | Steuerung der Kommunikation und des Dialogs zwischen den Systemen. [cite_start]**Protokolle:** SAP, NetBIOS. [cite: 3392, 3411] | Daten |
| **4** | **Transport (Transport)** | Sicherstellung der fehlerfreien End-zu-End-Übertragung der gesamten Nachricht. [cite_start]**Protokolle:** TCP, UDP. [cite: 3393] | **Ports** / Segmente |
| **3** | **Vermittlung (Network)** | Routing von Datenpaketen durch das Netzwerk von einem Start- zu einem Zielknoten. [cite_start]**Protokolle:** IPv4, IPv6, ICMP. [cite: 3401, 3411] | **IP-Adressen** / Pakete |
| **2** | **Sicherung (Data Link)** | Fehlerfreie Übertragung von Datenblöcken (Frames) in einem lokalen Netzwerk. [cite_start]**Protokolle:** Ethernet, WLAN, ARP. [cite: 3402, 3411] | **MAC-Adressen** / Frames |
| **1** | **Bitübertragung (Physical)** | Übertragung der rohen Bits über das physikalische Medium. [cite_start]**Komponenten:** Kabel, Hub, Repeater, Netzwerkkarte. [cite: 3406] | Bits |

**Merksatz (von unten nach oben):** **A**lle **S**einer **T**ollen **V**erwandten **D**ürfen **S**onntags **P**addeln.

### Datenkapselung: Die Reise der Daten
Wenn eine Anwendung Daten sendet, wandern diese von Schicht 7 nach unten zu Schicht 1. Auf jeder Schicht wird ein Header (ein "Umschlag") mit spezifischen Informationen hinzugefügt. Diesen Prozess nennt man **Datenkapselung**.

-   **Schicht 4 (Transport):** Hier wird der **Port** hinzugefügt. Er stellt sicher, dass die Daten auf dem Zielcomputer dem richtigen Programm (z.B. Browser) zugeordnet werden. Die Dateneinheit heißt hier **Segment**.
-   **Schicht 3 (Vermittlung):** Hier wird die **IP-Adresse** hinzugefügt. Sie funktioniert wie eine Postanschrift und findet den richtigen Computer im globalen Netzwerk. Die Dateneinheit heißt hier **Paket**.
-   **Schicht 2 (Sicherung):** Hier wird die **MAC-Adresse** hinzugefügt. Sie ist die Hardware-Adresse der Netzwerkkarte und sorgt dafür, dass die Daten im lokalen Netzwerk das richtige Gerät erreichen. Die Dateneinheit heißt hier **Frame**.
-   **Schicht 1 (Bitübertragung):** Die Frames werden in **Bits** umgewandelt und als Signale über das Medium gesendet.

### Das Zusammenspiel der Adressen (Prüfungs-Tipp)
Für die Prüfung ist es entscheidend, den Zweck der drei Adresstypen zu verstehen:
1.  **IP-Adresse (Schicht 3):** Findet den richtigen **Computer** im Netzwerk.
2.  **MAC-Adresse (Schicht 2):** Findet die richtige **Netzwerkkarte** im lokalen Netz.
3.  **Port (Schicht 4):** Findet das richtige **Programm** auf dem Computer.

---

### Fehlersuche mit dem OSI-Modell
[cite_start]Bei der Fehlersuche beginnt man systematisch auf der untersten Ebene (Schicht 1) und arbeitet sich nach oben. [cite: 3414]

| Schicht | Name (Deutsch/Englisch) | Typische Fehler |
| :---: |:---|:---|
| **7** | Anwendung (Application) | [cite_start]Die Anwendung ist abgestürzt, Konfigurationsfehler in der Software. [cite: 3438] |
| **6** | Darstellung (Presentation) | [cite_start]Konvertierungsfehler, falsches Dateiformat, ungültige Verschlüsselung. [cite: 3435] |
| **5** | Sitzung (Session) | [cite_start]Verbindungsabbruch, z.B. durch Serverüberlastung oder Timeout. [cite: 3430] |
| **4** | Transport (Transport) | [cite_start]Port durch Firewall blockiert, Paketverlust. [cite: 3427] |
| **3** | Vermittlung (Network) | [cite_start]Falsche IP-Adresse, falsche Subnetzmaske, falsches Gateway konfiguriert. [cite: 3424] |
| **2** | Sicherung (Data Link) | [cite_start]MAC-Adressenkonflikt, defekter Switch-Port, falsches VLAN. [cite: 3421] |
| **1** | Bitübertragung (Physical) | [cite_start]Kabel nicht eingesteckt oder defekt, WLAN ausgefallen, Netzwerkkarte defekt. [cite: 3417, 3418] |

---

## Prüfungsaufgaben (Original)

#### Quelle: Prüfung Frühjahr 2024, Teil 1, Aufgabe 2b
> **Aufgabe:** Benennen Sie die OSI-Schichten und ordnen Sie die Begriffe `Physische Adresse`, `DHCP`, `Verbindungslokale IPv6-Adresse`, `Buchse mit LED` zu.

**Lösung:**
| OSI-Schicht | Name der Schicht | Begriff |
| :---: | :--- | :--- |
| **7** | Anwendung (Application) | DHCP |
| **3** | Vermittlung (Network) | Verbindungslokale IPv6-Adresse |
| **2** | Sicherung (Data Link) | Physische Adresse (MAC) |
| **1** | Bitübertragung (Physical) | Buchse mit LED |

#### Quelle: Prüfung Frühjahr 2022, Teil 1, Aufgabe 3c
> **Aufgabe:** Ergänzen Sie die Tabelle zur Fehleranalyse basierend auf dem OSI-Modell.

**Lösung:**
| OSI-Schicht Nr. | OSI-Schicht Name | Protokolle | Adressen | Möglicher Fehler |
| :---: | :--- | :--- | :--- | :--- |
| **7** | Anwendungsschicht | HTTP, DNS | - | DNS-Server nicht erreichbar |
| **4** | Transportschicht | TCP/UDP | Ports | Verlust eines Segments |
| **3** | Vermittlungsschicht | IP, ICMP | IP-Adresse | Falsches Gateway |
| **2** | Sicherungsschicht | Ethernet, ARP | MAC-Adresse | Falsche VLAN-Zugehörigkeit |
| **1** | Bitübertragungsschicht | - | - | Kabel getrennt |
