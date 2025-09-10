# Netzwerktechnik – Netzwerkdiagnose

## Theorie: Systematische Fehlersuche

Wenn ein Netzwerkproblem auftritt, ist ein systematisches Vorgehen entscheidend. Die bewährteste Methode ist die **"Bottom-Up-Fehlersuche"**, bei der man sich am OSI-Modell orientiert und bei der untersten Schicht (Schicht 1) beginnt.

### Die Bottom-Up-Fehlersuche in der Praxis

Stell dir vor, ein Benutzer meldet: "Das Internet geht nicht!". Hier ist dein Plan:

#### Schritt 1: Überprüfung der Schicht 1 (Bitübertragung)
**Frage:** Gibt es eine physische Verbindung?
* **Visuelle Prüfung:** Leuchten die LEDs an der Netzwerkkarte und am Switch? Ist das Netzwerkkabel auf beiden Seiten fest eingesteckt?
* **System-Anzeige:** Zeigt das Netzwerksymbol "Nicht verbunden"?

---
#### Schritt 2: Überprüfung der Schichten 2 & 3 (Lokales Netz)
**Frage:** Funktioniert die Kommunikation im lokalen Netzwerk?

1.  **Eigene Konfiguration prüfen mit `ipconfig /all`**
    * **Zweck:** Zeigt die eigene IP-Konfiguration an.
    * **Analyse:** Habe ich eine korrekte IP-Adresse oder eine APIPA-Notfalladresse (`169.254.x.x`)? Stimmen Subnetzmaske und Standardgateway?

2.  **Eigenen Netzwerkadapter testen mit `ping 127.0.0.1`**
    * **Zweck:** Der "Loopback-Ping" testet, ob der TCP/IP-Stack auf deinem Computer korrekt funktioniert. Schlägt dieser fehl, liegt ein Treiber- oder Betriebssystemproblem vor.

3.  **Lokale Erreichbarkeit testen mit `ping [Standardgateway]`**
    * **Zweck:** Testet, ob du den Router (dein Tor ins Internet) erreichen kannst.
    * **Analyse:** Wenn dieser Ping erfolgreich ist, funktioniert die Verbindung vom PC zum Router (Schicht 1-3).

4.  **Adressauflösung prüfen mit `arp -a`**
    * **Zweck:** Zeigt die Zuordnung von IP- zu MAC-Adressen (ARP-Cache).
    * **Analyse:** Wenn der Ping zum Gateway erfolgreich war, muss hier ein Eintrag für die IP des Gateways mit der zugehörigen MAC-Adresse stehen.

---
#### Schritt 3: Überprüfung der Schichten 3 & 7 (Internet)
**Frage:** Komme ich über den Router hinaus ins Internet?

1.  **Internet-Konnektivität testen mit `ping 8.8.8.8`**
    * **Zweck:** Testet die Erreichbarkeit eines öffentlichen Servers per IP-Adresse.
    * **Analyse:** Wenn dieser Ping funktioniert, der Ping zum Gateway aber nicht, liegt das Problem wahrscheinlich am Router. Wenn der Ping zum Gateway klappt, dieser aber nicht, liegt das Problem oft beim Internetanbieter.

2.  **DNS-Funktionalität testen mit `ping google.de`**
    * **Zweck:** Testet, ob die Namensauflösung (DNS) funktioniert.
    * **Analyse:** Wenn `ping 8.8.8.8` funktioniert, aber `ping google.de` nicht, dann liegt das Problem beim DNS-Server.

3.  **Den Weg verfolgen mit `tracert google.de`**
    * **Zweck:** Verfolgt den Weg, den Datenpakete zu einem Ziel nehmen, und zeigt alle Router-Stationen ("Hops") an.
    * **Analyse-Tipp:** Achte auf die Ausgabe!
        * **Normale Antwort (`12 ms...`):** Alles in Ordnung.
        * **Zeitüberschreitung (`* * *`):** Nicht immer ein Fehler! Kann eine Firewall sein. Wenn spätere Hops antworten, geht die Verbindung weiter.
        * **Zielhost nicht erreichbar:** Hier ist die Verbindung wirklich unterbrochen.

---

## Prüfungsaufgaben (Original)

#### Quelle: IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 1dc
> **Aufgabe:** Sie sollen die richtige RJ-45-Buchse für das Präsentationsnetzwerk (`192.168.20.0/24`) an einer unbeschrifteten Doppeldose ermitteln. Beschreiben Sie Ihre Vorgehensweise.

**Lösung:**
1.  Präsentationsrechner mit einem Patchkabel mit der **linken Buchse** verbinden.
2.  Kommandozeile öffnen und den Befehl **`ipconfig`** ausführen.
3.  Die angezeigte IP-Adresse überprüfen:
    * Liegt die Adresse im Bereich `192.168.20.x`? Dann ist es die richtige Buchse.
    * Ist die Adresse aus einem anderen Netz oder eine APIPA-Adresse? Dann ist es die falsche Buchse.
4.  Falls falsch, das Kabel in die **rechte Buchse** stecken und die Schritte 2-3 wiederholen.
5.  Die Buchse entsprechend dem Ergebnis beschriften.

#### Quelle: IHK-Abschlussprüfung Frühjahr 2024, Teil 1, Aufgabe 2e
> **Aufgabe:** Erläutern Sie die grundlegende Aufgabe des Address Resolution Protocol (ARP) anhand des `arp -a` Outputs.
> **Angabe im Output:** `Internetadresse 192.168.0.1` ist `Physische Adresse d4-3f-cb-8c-37-8b` zugeordnet.

**Lösung:**
Das **ARP (Address Resolution Protocol)** übersetzt eine **IP-Adresse (logische Adresse, Schicht 3)** in eine **MAC-Adresse (physische Adresse, Schicht 2)**. Wenn ein PC Daten an ein anderes Gerät im selben lokalen Netzwerk senden möchte, kennt er zwar dessen IP-Adresse, benötigt aber die MAC-Adresse für die Zustellung. Per ARP-Request fragt der PC ins Netzwerk, wer die gesuchte IP-Adresse hat, und das Zielgerät antwortet mit seiner MAC-Adresse.
