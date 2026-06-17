# ADR-0003: Basic-Auth ohne Passwörter statt Okta für den Prototypen

**Status**: Akzeptiert

## Kontext

Für den Prototypen ist eine Nutzeridentifikation notwendig, um Buchungen dem richtigen INNOQ-Mitarbeiter zuzuordnen und die Buchungsübersicht zu ermöglichen. Die langfristig geplante Okta-Integration (OpenID Connect) würde jedoch eine externe Abhängigkeit einführen und den Entwicklungsaufwand für den Prototypen deutlich erhöhen.

## Entscheidung

Wir verzichten für den Prototypen auf eine Okta-Integration. Stattdessen wird **HTTP Basic Authentication ohne Passwörter** eingesetzt: Der Nutzername dient als eindeutiger Identifier; ein Passwort wird nicht geprüft. Die Okta-Integration wird nachgeliefert, wenn das System in den Produktivbetrieb geht.

## Betrachtete Alternativen

| Option | Externe Abhängigkeit | Testbarkeit | Aufwand |
|--------|---------------------|-------------|---------|
| **Basic-Auth ohne Passwort** | **Keine** | **Hoch** | **Gering** |
| Okta (OpenID Connect / OAuth 2.0) | Okta-Tenant notwendig | Mittel | Hoch |
| JWT-basierte Authentifizierung | Keine | Mittel | Mittel |
| Keine Authentifizierung (anonym) | Keine | Gering | Keine |

## Begründung

- **Keine Drittabhängigkeiten**: Okta erfordert einen konfigurierten Tenant und Network-Zugang — beides ist für den Prototyp-Betrieb in der Trainingsumgebung nicht gegeben.
- **Einfaches Nutzerwechseln**: Verschiedene INNOQ-Mitarbeiter-Szenarien lassen sich ohne Account-Setup schnell durchspielen.
- **Fokus auf fachliche Validierung**: Die Authentifizierungsinfrastruktur soll die Validierung der Buchungslogik nicht blockieren.

## Konsequenzen

- Kein Passwortschutz — das System ist nur für die interne Prototyp-Phase geeignet, nicht für den Produktivbetrieb.
- Alle Nutzer haben identische Zugriffsrechte; rollenbasierte Zugriffskontrolle (z. B. Admin-Funktionen) wird erst mit der Okta-Integration umgesetzt.
- **Technische Schuld**: Die Okta-Integration muss vor dem Produktivbetrieb nachgeliefert werden (siehe [Technische Schulden](../technische-schulden.md)).
