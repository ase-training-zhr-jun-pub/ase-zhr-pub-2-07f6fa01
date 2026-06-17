# Technische Schulden Calvin

Diese Seite dokumentiert bekannte technische Schulden, die bewusst im Rahmen von Architekturentscheidungen für den Prototypen eingegangen wurden. Jede Schuld ist mit der zugehörigen ADR verlinkt und enthält einen klaren Migrationspfad für den Produktivbetrieb.

---

## TS-1: Ressourcedaten als Mock-Daten in der SPA

**Ursprung**: [ADR-0002](adrs/ADR-0002-ressourcedaten-als-mock-daten-in-der-spa.md)

**Beschreibung**: Standorte, Konferenzräume und Ausstattungen sind als statische Mock-Daten in der SPA hinterlegt. Es existiert kein dedizierter Ressource-Service.

**Auswirkung im Prototyp**:
- Neue Ressourcen erfordern ein Frontend-Redeployment.
- Ressourcedaten können nicht zur Laufzeit geändert werden.

**Migrationspfad für Produktivbetrieb**:
1. Ressource-Service als eigenständigen Service implementieren (REST API, analog zum Booking Service).
2. Mock-Daten in die Datenbank des Ressource-Service migrieren.
3. SPA auf API-Calls gegen den Ressource-Service umstellen.
4. Da der Booking Service nur IDs kennt, sind dort keine Änderungen notwendig.

**Priorität**: Vor Go-Live Pflicht

---

## TS-2: Fehlende Authentifizierung (Basic-Auth ohne Passwörter)

**Ursprung**: [ADR-0003](adrs/ADR-0003-basic-auth-ohne-passwort-fuer-prototyp.md)

**Beschreibung**: Das System verwendet HTTP Basic Authentication ohne Passwortprüfung. Der Nutzername dient lediglich als Identifier. Es gibt keine echte Zugriffskontrolle.

**Auswirkung im Prototyp**:
- Kein Passwortschutz — jede Person mit Netzwerkzugang kann sich als beliebiger Nutzer ausgeben.
- Keine rollenbasierte Zugriffskontrolle.

**Migrationspfad für Produktivbetrieb**:
1. Okta-Tenant für INNOQ konfigurieren und OpenID Connect / OAuth 2.0 Flows einrichten.
2. Booking Service um Token-Validierung (JWT) erweitern.
3. SPA auf Okta-Login-Flow umstellen.
4. Basic-Auth vollständig entfernen.
5. Rollenbasierte Zugriffsrechte (z. B. Admin-Funktionen) definieren und implementieren.

**Priorität**: Vor Go-Live Pflicht

---

## Übersicht

| ID | Beschreibung | ADR | Priorität |
|----|-------------|-----|-----------|
| TS-1 | Mock-Daten statt Ressource-Service | ADR-0002 | Vor Go-Live Pflicht |
| TS-2 | Basic-Auth ohne Passwörter statt Okta | ADR-0003 | Vor Go-Live Pflicht |
