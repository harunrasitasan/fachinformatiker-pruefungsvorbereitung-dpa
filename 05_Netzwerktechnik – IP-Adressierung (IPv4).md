# Netzwerktechnik – IP-Adressierung (IPv4)

## Theorie-Überblick

### Der Aufbau: 32 Bit in 4 Oktetten

Eine IPv4-Adresse besteht aus **32 Bit**. Um sie für Menschen lesbar zu machen, werden diese 32 Bit in vier Blöcke zu je 8 Bit aufgeteilt. Jeden dieser Blöcke nennt man ein **Oktett**. Diese Oktette werden als Dezimalzahlen (0-255) geschrieben und durch Punkte getrennt.

* **Binär:** `11000000.10101000.00000001.00000001`
* **Dezimal:** `192.168.1.1`

### Die Subnetzmaske: Netzanteil und Hostanteil

Ein Computer muss wissen, welcher Teil der IP-Adresse das **Netzwerk (Netzanteil)** und welcher Teil das **Gerät (Hostanteil)** kennzeichnet. Genau das verrät ihm die **Subnetzmaske**.

* **IP-Adresse:** `192.168.1.1`
* **Subnetzmaske:** `255.255.255.0`

Die `255` in der Maske bedeutet: "Dieser Teil gehört zur Netzwerkadresse". Die `0` bedeutet: "Dieser Teil ist die eindeutige Gerätenummer".

### CIDR-Notation und die Berechnung der Subnetzmaske

Alternativ wird die Subnetzmaske oft in der **CIDR-Notation** angegeben, z. B. `/24`. Die Zahl gibt an, wie viele Bits von links gezählt zum Netzanteil gehören.

* Die CIDR-Notation `/24` bedeutet, dass die ersten **24 Bits** der Maske eine `1` sind.
* **Binär:** `11111111.11111111.11111111.00000000`
* **Dezimal:** Wenn wir jedes Oktett umrechnen, ergibt das `255.255.255.0`.

**Beispiel `/26`:**
* **CIDR:** `/26` (Die ersten 26 Bits sind `1`)
* **Binär:** `11111111.11111111.11111111.11000000`
* **Dezimal:** `255.255.255.192` (da `128 + 64 = 192`)

### Private Adressbereiche & NAT

Es gibt spezielle Adressbereiche, die nur in lokalen Netzwerken (LANs) verwendet werden dürfen und im Internet nicht direkt erreichbar sind.

* **Klasse A:** `10.0.0.0` bis `10.255.255.255` (`/8`)
* **Klasse B:** `172.16.0.0` bis `172.31.255.255` (`/12`)
* **Klasse C:** `192.168.0.0` bis `192.168.255.255` (`/16`)

Dein PC hat eine solche private Adresse. Dein Router zuhause übersetzt diese private Adresse in seine eine, öffentliche IP-Adresse, um mit dem Internet zu kommunizieren. Diesen Vorgang nennt man **NAT (Network Address Translation)**.

### APIPA: Die Notfall-Adresse

Wenn ein PC auf DHCP (automatische Adressvergabe) eingestellt ist, aber keinen DHCP-Server findet, gibt er sich selbst eine Adresse aus dem Bereich `169.254.x.x`. Das nennt man **APIPA** (Automatic Private IP Addressing).

---

## Typische Prüfungsfragen und Lösungswege

#### Frage 1: Subnetting
**Quelle:** *IHK-Abschlussprüfung Frühjahr 2025, Teil 1, Aufgabe 1d*
> **Aufgabe:** Ein Netzwerk hat die Adresse `192.168.100.0 /26`. Wie viele nutzbare Host-Adressen stehen zur Verfügung und wie lautet die Broadcast-Adresse?

**Schritt-für-Schritt-Lösung:**
1.  **Host-Bits finden:** `32 Bit (gesamt) - 26 Bit (Netz) = 6 Bits` für die Hosts.
2.  **Gesamte Adressen berechnen:** `2^6 = 64` Adressen.
3.  **Adressbereich definieren:** Das Netz startet bei `.0`. Der Bereich umfasst 64 Adressen: von `192.168.100.0` bis `192.168.100.63`.
4.  **Nutzbare Adressen bestimmen:** Die erste Adresse (`.0`, Netzadresse) und die letzte (`.63`, Broadcast-Adresse) sind reserviert.
5.  **Antwort:** Es gibt `64 - 2 = 62` nutzbare Host-Adressen. Die Broadcast-Adresse ist `192.168.100.63`.

#### Frage 2: APIPA erklären
**Quelle:** *IHK-Abschlussprüfung Herbst 2024, Teil 1, Aufgabe 1da*
> **Aufgabe:** Ihr Kollege sieht auf einem PC die IP-Adresse `169.254.80.15`. Erklären Sie, was diese Adresse bedeutet und was die wahrscheinliche Ursache ist.

**Antwort:**
Es handelt sich um eine **APIPA-Adresse**. Das Betriebssystem vergibt diese automatisch, wenn der PC für DHCP konfiguriert ist, aber **keinen DHCP-Server im Netzwerk erreichen konnte** (z.B. Kabel nicht angeschlossen, Server ausgefallen).

#### Frage 3: Binär in Dezimal umrechnen
> **Aufgabe:** Wandeln Sie das Oktett `11000000` in eine Dezimalzahl um.

**Antwort:**
Jede Stelle im Oktett hat eine Wertigkeit (eine Zweierpotenz):
`128 | 64 | 32 | 16 | 8 | 4 | 2 | 1`
`  1 |  1 |  0 |  0 | 0 | 0 | 0 | 0`
Man addiert die Wertigkeiten, an denen eine `1` steht: `128 + 64 = 192`.
