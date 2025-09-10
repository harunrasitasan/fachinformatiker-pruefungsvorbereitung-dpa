# Netzwerktechnik – IP-Adressierung (IPv6)

## Theorie-Überblick

### Der Aufbau: 128 Bit in 8 Blöcken

Eine IPv6-Adresse ist **128 Bit** lang. Sie wird in **acht Blöcken** zu je 16 Bit aufgeteilt und in **hexadezimaler Schreibweise** (Zahlen 0-9, Buchstaben A-F) dargestellt. Die Blöcke werden durch Doppelpunkte getrennt.

**Beispiel:** `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

### Die Struktur einer globalen IPv6-Adresse (/64)

Eine typische globale IPv6-Adresse ist logisch aufgeteilt. Die Präfixlänge `/64` sagt uns, dass die ersten 64 Bit das Netzwerk und die letzten 64 Bit das Gerät beschreiben.

* **Global Routing Prefix (Standortpräfix - 48 Bit):** Die ersten 3 Blöcke. Identifiziert dein Netzwerk weltweit eindeutig (wie PLZ + Stadt).
* **Subnet ID (Teilnetz-ID - 16 Bit):** Der 4. Block. Unterteilt dein Netzwerk in kleinere Subnetze (wie die Straße).
* **Interface Identifier (Geräte-ID - 64 Bit):** Die letzten 4 Blöcke. Identifiziert ein Gerät im Subnetz eindeutig (wie die Hausnummer).

### Die Kürzungsregeln (Prüfungs-Tipp)

1.  **Führende Nullen weglassen:** Führende Nullen innerhalb eines Blockes dürfen entfernt werden (`0db8` wird zu `db8`).
2.  **Null-Blöcke zusammenfassen:** Eine zusammenhängende Kette von Null-Blöcken darf **genau einmal** durch zwei Doppelpunkte (`::`) ersetzt werden.

**Beispiel:**
* **Original:** `2001:0db8:0000:0000:1a2b:0000:0000:0001`
* **Gekürzt:** `2001:db8::1a2b:0:0:1`

### Wie entsteht der Interface Identifier?

Es gibt zwei wichtige Methoden, wie ein Gerät die letzten 64 Bit seiner Adresse generiert:

1.  **EUI-64 (der alte Standard):** Der Interface Identifier wird direkt aus der 48-Bit-**MAC-Adresse** der Netzwerkkarte abgeleitet. Dies ist zwar eindeutig, aber ein Datenschutzproblem, da das Gerät so über Netzwerke hinweg wiedererkennbar ist. Dieses Verfahren wird oft noch für die Link-Local-Adresse verwendet.
2.  **Privacy Extensions (der neue Standard):** Das Betriebssystem erzeugt in regelmäßigen Abständen einen **zufälligen Interface Identifier**. Dies ist die Standardmethode für die Kommunikation im Internet, um die Privatsphäre des Nutzers zu schützen.

### Spezielle Adresstypen

* **Link-Local-Adresse (`fe80::/10`):** Ähnlich wie APIPA bei IPv4. Jedes Gerät vergibt sich diese Adresse automatisch selbst. Sie ist **nicht im Internet routbar** und dient nur zur Kommunikation im direkten, lokalen Netzwerk.
* **Globale Unicast-Adresse (beginnt meist mit `2...`):** Die "normale", weltweit eindeutige und im Internet routbare IP-Adresse.

---

## Typische Prüfungsfragen und Lösungswege

#### Frage 1: IPv6 kürzen
> **Aufgabe:** Kürzen Sie die folgende IPv6-Adresse so weit wie möglich: `fe80:0000:0000:0000:00ab:c000:0000:0001`.

**Antwort:** `fe80::ab:c000:0:1` *(Die längste Kette aus drei Null-Blöcken wird durch `::` ersetzt, weitere Nullen werden weggelassen.)*

#### Frage 2: IPv6-Bestandteile benennen
**Quelle:** *IHK-Abschlussprüfung Herbst 2022, Teil 1, Aufgabe 3b*
> **Aufgabe:** Gegeben ist die Adresse `2001:da8:5f2d:28::/64`. Geben Sie das Standortpräfix und die Teilnetz-ID in ungekürzter Form an.

**Lösungsweg:**
1.  Die Adresse hat 4 sichtbare Blöcke, die `::` ersetzen also `8 - 4 = 4` Null-Blöcke.
2.  **Standortpräfix (erste 3 Blöcke):** `2001:0da8:5f2d`
3.  **Teilnetz-ID (4. Block):** `0028`
