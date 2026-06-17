---
Ticket-ID: CLVN-016-SUBTASK-1
Type: Subtask
Parent: CLVN-016
Status: TODO
---
# Verfügbaren Raum auswählen und hervorheben

## Beschreibung

Aus der Liste der verfügbaren Konferenzräume soll ein INNOQ-Mitarbeiter einen Raum durch Klick bzw. Tap auswählen können. Die getroffene Auswahl wird visuell deutlich hervorgehoben, sodass jederzeit erkennbar ist, welcher Raum aktuell ausgewählt ist.

Reine Frontend-Umsetzung auf Basis der gemockten Daten aus `frontend/src/lib/mock-data.ts`; es findet keine Persistierung statt.

## Akzeptanzkriterien

- [ ] Ein als verfügbar markierter Konferenzraum kann per Klick/Tap ausgewählt werden
- [ ] Nicht verfügbare Räume können nicht ausgewählt werden
- [ ] Der ausgewählte Raum wird visuell deutlich hervorgehoben (selektierter Zustand)
- [ ] Zu jedem Zeitpunkt ist höchstens ein Raum ausgewählt

## Betroffene Persona

[INNOQ-Mitarbeiter](/docs/produkt/personas/innoq-mitarbeiter.md)

## Zugehörige Story

[CLVN-016 - Raumauswahl bestätigen](/docs/produkt/backlog/CLVN-016-STORY-raumauswahl-bestaetigen.md)
