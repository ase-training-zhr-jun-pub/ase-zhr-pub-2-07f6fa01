# ADR-0002: Ressourcedaten als Mock-Daten in der SPA

**Status**: Akzeptiert

## Kontext

Für den Prototypen müssen Standorte, Konferenzräume und Ausstattungen verwaltet werden. Ursprünglich war ein separater Ressource-Service geplant, der diese Daten über eine REST API bereitstellt. Ein solcher Service würde jedoch den Entwicklungsaufwand erhöhen und eine weitere Systemkomponente einführen, die für die Validierung der Buchungslogik im Prototypen nicht notwendig ist.

## Entscheidung

Standort-, Konferenzraum- und Ausstattungsdaten werden als statische Mock-Daten in der SPA hinterlegt. Der Booking Service arbeitet ausschließlich mit den IDs aus diesen Mock-Daten und kennt keine Ressourcedetails.

## Betrachtete Alternativen

| Option | Aufwand | Abhängigkeiten | Prototyp-Eignung |
|--------|---------|----------------|-----------------|
| **Mock-Daten in der SPA** | **Gering** | **Keine** | **Hoch** |
| Separater Ressource-Service (REST) | Hoch | Neuer Service | Gering |
| Ressourcedaten im Booking Service | Mittel | Kein separater Service | Mittel |

## Begründung

- **Schnelleres Prototyping**: Kein separater Service notwendig; Ressourcedaten sind sofort verfügbar.
- **Geringere Komplexität**: Die Systemarchitektur bleibt zweiteilig (SPA + Booking Service) ohne zusätzliche Komponenten.
- **Schlanker Booking Service**: Der Booking Service verarbeitet nur IDs und muss keine Ressourcedetails vorhalten oder synchronisieren.
- **Migrationspfad**: Ein späterer Wechsel zu einem echten Ressource-Service erfordert keine Änderung am Booking Service, da dieser nur mit IDs arbeitet.

## Konsequenzen

- Neue Standorte oder Konferenzräume erfordern ein Frontend-Redeployment.
- Anzeigenamen für Standorte, Räume und Ausstattungen kommen ausschließlich aus der SPA; der Booking Service gibt nur IDs zurück.
- **Technische Schuld**: Ressourcedaten müssen vor dem Produktivbetrieb in einen echten Ressource-Service ausgelagert werden (siehe [Technische Schulden](../technische-schulden.md)).
