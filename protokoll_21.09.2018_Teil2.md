### Protokoll vom 21.09.2018, Teil2

## Grundsätzliches

- Alle Anwendungen werden über eine einzige App gesteuert. Es handelt sich immer um dieselbe App, beispielsweise unabhängig davon, ob man sich vor Ort im selben Netz wie die Things befindet oder ab man von aussen über das Internet zugreift. Es soll aber dennoch erweiterbar bleiben.
- Solange noch nicht mit echten Daten getestet werden kann, wird das Digitale Abbild aus Testdaten erstellt
- Die Architektur ist entkoppelt, da die Anwendung sonst kaum Testbar ist und eine kleine Änderung grosse Auswirkungen auf die gesamte Applikation mit sich zieht.

### Möglicherweise  Verwendbar

- Modbus-Protokoll: Client-/Server-Architektur
- EEBUS: Initiative eines Elektro-Unternehmens und beschreibt ein digitales Modell z.B. für eine Boiler-Heizung oder Batterie, welches vorsieht, dass der Hardware-Hersteller ausgewechselt werden kann, da von allen dieselbe Software eingesetzt wird. Das Motto : „we speak energy&quot;

## Brainstorming Anwendungen

### Iteration 1

- Security
- Condition Monitoring (Basisdaten)
- Netz
- FogDevice
- Lärm Detektor
- Assetmanagement (Boote)
- Brefing/Debrefing Miete (Raum vorbereiten &amp; Aufräumen)
- Umkleide
- Personenflüsse
- Klima
- Life-Cycle-Management
- Monitoring Abfall, Küchengeräte
- User Interface
- Schnittstellen (incl. zukünftige)

### Iteration 2

- Gebäudesicherheit
  - Einbruch
  - Wasserschaden
  - Fenster offen
  - Bewegung unerlaubt
- Ungebungsdaten &amp; Alarme
  - O2
  - CO2

# 2
, Temperatur, Flüsse(Wasser, Strom)
- Klima
  - Heizen/Kühlen
- Asset Tracking
- Vor- &amp; Nachbearbeitung Miete
- Umkleide
- Nutzerstatistik/Personenfluss

## Systemaufteilung

 ![Basic principle](/pictures/view1.jpg)
1. 1)Sensoren
2. 2)Aktoren
3. 3)Digitales Abbild
4. 4)Applikationen
5. 5)Widget (Bedienelement)
6. 6)GUI (Zusammenfassung Widged)

Durch diese Architektur kann das System problemlos erweitert werden (rot im Bild). Spezialisierte Teams kümmern sich um die verschiedenen Teile (grüne Pfeile).

Grobe Aufteilung Teams:

- Digitales Abbild incl. Sync
- Interface
- GUI
- Generelles und Allgemeines, Value Proposition

Das FogDevice baut das Digitale Abbild der realen Welt und speichert dieses von Zeit zu Zeit in der Cloud (beide blau).

## Zugriffe

Rollenmanagement:

- Person kann verschiedene Rollen haben
- Recht digitales Bild schreiben &amp; Recht zum Nutzen
- Gibt es schon
- Standard Protokoll: oauth2
- Broker: Worniq (?) (hat sich bewährt)

# Beschlüsse

**Systemaufteilung gemäss Bild weiter oben:** Einstimmig angenommen, keine Enthaltungen

# Aufgaben

| **Zuständigkeit** | **Aufgabe** | **Fälligkeit** |
| --- | --- | --- |
| Joris | GitHub erstellen | 05.10.2018 |
| Alle | eebus.org für mindestens 30 Minuten studieren | 05.10.2018 |
| Alle | 2-3 Prioritäten, wo er sich gerne einbringen möchte |   |
|   |   |   |
