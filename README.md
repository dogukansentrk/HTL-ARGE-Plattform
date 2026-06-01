# Pflichtenheft
## HTL ARGE Plattform
**Alperen Muratgül, Dogukan Sentürk**

---

## Projektbeschreibung

Ziel des Projekts ist die Entwicklung einer webbasierten Plattform für Schülerinnen und Schüler der HTL. Die Anwendung ermöglicht es Benutzern, sich zu registrieren, einzuloggen und ihre Interessen einzutragen (z.B. Linux, 3D-Modelling, Gaming, Robotik). Das System findet automatisch Mitschüler mit denselben Interessen und ermöglicht so die Bildung von Arbeitsgemeinschaften. Über eine Integration mit der WebUntis API werden Stundenplan-Daten abgerufen, um gemeinsame freie Stunden zu berechnen und Gruppen gezielt planen zu können.

---

## Anforderungen

- Schüler können sich mit Name, Schulmail und Passwort registrieren
- Schüler können sich einloggen und ausloggen
- Nach dem Login wird ein JWT-Token ausgestellt, der bei weiteren Anfragen zur Authentifizierung verwendet wird
- Jeder Schüler kann Interessen aus einer vordefinierten Liste auswählen oder eigene eintragen
- Das System zeigt automatisch Mitschüler mit gleichen Interessen an
- Schüler können Gruppen zu einem bestimmten Thema erstellen und anderen beitreten
- Über die WebUntis API werden Stundenplandaten abgerufen und gemeinsame freie Stunden berechnet
- Schüler können sich per E-Mail oder Discord benachrichtigen lassen, wenn jemand Neues dasselbe Interesse einträgt

---

## Mögliche Erweiterungen

- **Freistunden-Finder:** Berechnung gemeinsamer freier Stunden mehrerer Schüler aus WebUntis-Daten
- **Raumplan-Viewer:** Anzeige freier Räume in Echtzeit zur Planung von Gruppentreffen
- Bewertungssystem für Gruppen und Mitglieder
- Admin-Panel für Lehrer zur Verwaltung von Gruppen und Inhalten
- Telegram-Bot als alternative Benachrichtigungsmethode

---

## Abgrenzung

- Kein direktes Messaging innerhalb der Plattform — Kommunikation über externe Tools (Discord, WhatsApp)
- Keine Verwaltung von Schulnoten oder offiziellen Schuldaten
- Keine native Mobile App in der ersten Version
- Der HTML-Scraper ist nur als Fallback vorgesehen — primär wird die WebUntis REST API genutzt
- Keine SSO-Authentifizierung über das Schulnetzwerk in der Basisversion

---

## Technologie

- Python Backend (FastAPI)
- SQLite Datenbank
- JWT für Authentifizierung
- WebUntis REST API (Session-Token) für Stundenplandaten
- BeautifulSoup + requests (Web Scraping als Fallback)
- React Frontend
- SMTP / SendGrid für E-Mail-Benachrichtigungen
