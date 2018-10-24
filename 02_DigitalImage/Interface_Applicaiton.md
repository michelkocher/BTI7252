# Schnittstelle Applikation

Die Apps können über eine einheitliche REST-Schnittstelle auf bestehende Daten zugreifen.

Dabei gibt es folgende Abfragen mit dazugehörigen Antworten

|   Endpoint   |     Response   |
|-------------|----------------|
|/Things      | Gibt alle Things zurück (Paging) |
|/Things/{id} | Gibt ein Thing mit der {id} zurück) |
|/Entities      | Gibt alle Entities zurück (Paging) |
|/Entities/{id}     | Gibt eine Entity mit der {id} zurück)  |
|/Entities/{id}/History     | Gibt die historischen Daten zu einer Entity zurück |
|/History                | Gibt die historischen Daten zu einer Entity zurück |
|*/Entities/{id}/Do*      | *Führt eine Aktion auf einer Entity aus* |
|*/Things/{id}/Do*      | *Führt eine Aktion auf einem Thing aus* |

Zudem ist es bei allen Endpoints möglich mittels Query ähnlich wie in SQL das Resultat zu filtern. Bsp: /Things?$select=name, id$filter name eq 'fridge'

Dies entspricht dem OData-Standard (https://www.odata.org). 

## Offene Fragen
Werden Actions auf einem Thing und / oder auf einer Entity ausgeführt? 

Wie werden Livedaten angezeigt? 

Wie werden Event-Basierte Applikation angesprochen?

Wer priorisiert die Befehle? --> Applikation; Hinweis an die Applikationsleute