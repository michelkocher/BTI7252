# Schnittstelle Sensoren 

Gegenüber den Sensoren wird eine MQTT-Schnittstelle vorgeschlagen.
Die Topic-Struktur kann analog der Datenstruktur aufgebaut werden. 


# mögliche Datenstruktur
Für die Datenspeicherung wird folgende Struktur vorgeschlagen. 
Diese muss je nach eingesetztem Tech-Stack noch angepasst werden. 

```
{
    "things": {
        "<thing_uuid>": {
            "location": "<String>",
            "registration_date": "<Date>",
            "last_update": "<Date>",
            "entities": {
                "<entity_uuid>": {
                    "feature_type": "<String>",
                    "name": "<String>",
                    "value": "<Var>",
                    "value_type": "<Var>", 
                    "value_unit": "<String>",
                    "last_update": "<Date>"
                }
            }
        }
    }
}
```

Weiter sollen die Daten für die Aufbereitung/Abfrage durch Applikationen noch nach Zeitstempel/Wert abgelegt werden.

```
{
    "data": {
        "thing_uuid.entity_uuid": {
            "<unix_timestamp>": "value"
        }
    }
}
```

Für eine weitere Abfrage können die Sensoren noch nach Feature-Type abgelegt werden
```
{ "feature_type": {
    "TemperatureSensor": [
        "<thing_uuid>",
        "<thing_uuid>",
        "<thing_uuid>"
    ]
}
}
```

# Feature Type
Jede Entity soll ein Feature-Type beinhalten. In dieser Klasse können die Metadaten (Möglichkeiten des Sensors, Mögliche Messwerte usw.) abgebildet werden. Die Feature-Type Klasse soll zwischen den Applikationen und Sensoren abgemacht werden. 


# Offene Punkte 
* Video-Stream einer Webcam -> allenfalls nur Standbild, kein Livestream? 
* Feature-Type Klassen für Sensoren u. Applikationen möglich? 
* Können über die Value-Fields der Things alle möglichen Sensoren gesteuert werden? 