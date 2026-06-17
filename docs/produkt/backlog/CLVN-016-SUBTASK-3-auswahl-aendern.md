---
Ticket-ID: CLVN-016-SUBTASK-3
Type: Subtask
Parent: CLVN-016
Status: TODO
---
# Auswahl ändern

## Beschreibung

Bevor ein INNOQ-Mitarbeiter seine Raumauswahl verbindlich bestätigt, soll er die Möglichkeit haben, die Auswahl zu ändern. So kann er einen anderen verfügbaren Raum wählen oder zur Übersicht zurückkehren, ohne den Buchungsvorgang neu beginnen zu müssen.

Reine Frontend-Umsetzung auf Basis der gemockten Daten aus `frontend/src/lib/mock-data.ts`.

## Akzeptanzkriterien

- [ ] Die getroffene Raumauswahl kann vor der Bestätigung geändert werden
- [ ] Es kann ein anderer verfügbarer Raum ausgewählt werden
- [ ] Der zuvor gewählte Zeitraum bleibt beim Ändern der Raumauswahl erhalten
- [ ] Die Zusammenfassung aktualisiert sich entsprechend der geänderten Auswahl

## Betroffene Persona

[INNOQ-Mitarbeiter](/docs/produkt/personas/innoq-mitarbeiter.md)

## Zugehörige Story

[CLVN-016 - Raumauswahl bestätigen](/docs/produkt/backlog/CLVN-016-STORY-raumauswahl-bestaetigen.md)
