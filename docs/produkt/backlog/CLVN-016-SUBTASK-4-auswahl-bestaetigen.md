---
Ticket-ID: CLVN-016-SUBTASK-4
Type: Subtask
Parent: CLVN-016
Status: TODO
---
# Auswahl bestätigen und fortfahren

## Beschreibung

Hat der INNOQ-Mitarbeiter seinen Konferenzraum ausgewählt und die Zusammenfassung geprüft, soll er die Auswahl über eine Bestätigungsschaltfläche verbindlich bestätigen. Nach der Bestätigung wird er zum nächsten Schritt des Buchungsprozesses (Eingabe weiterer Buchungsdetails) weitergeleitet.

Reine Frontend-Umsetzung auf Basis der gemockten Daten aus `frontend/src/lib/mock-data.ts`.

## Akzeptanzkriterien

- [ ] Eine Bestätigungsschaltfläche ermöglicht das Fortfahren zum nächsten Buchungsschritt
- [ ] Die Bestätigungsschaltfläche ist nur aktiv, wenn ein verfügbarer Raum ausgewählt ist
- [ ] Nach Bestätigung wird der Mitarbeiter zur Eingabe weiterer Buchungsdetails weitergeleitet
- [ ] Die Raum- und Zeitraumauswahl wird in den nächsten Schritt übernommen

## Betroffene Persona

[INNOQ-Mitarbeiter](/docs/produkt/personas/innoq-mitarbeiter.md)

## Zugehörige Story

[CLVN-016 - Raumauswahl bestätigen](/docs/produkt/backlog/CLVN-016-STORY-raumauswahl-bestaetigen.md)
