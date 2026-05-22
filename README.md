# Portfolio Backend

REST API für das [Portfolio-Frontend](https://github.com/alper42/portfolio). Empfängt Kontaktformular-Anfragen und versendet E-Mails via [Resend](https://resend.com).

---

## Tech Stack

| Technologie | Verwendung |
|---|---|
| Node.js + Express | REST API |
| Resend | E-Mail-Versand |
| dotenv | Umgebungsvariablen |
| Docker | Containerisierung |
| Render | Hosting |

---

## API

### `POST /send`

Versendet eine E-Mail aus dem Kontaktformular.

**Request Body:**
```json
{
  "name": "Max Mustermann",
  "email": "max@example.de",
  "message": "Hallo, ich hätte eine Frage..."
}
```

**Response (Erfolg):**
```json
{ "success": true }
```

**Response (Fehler):**
```json
{ "success": false, "error": "Fehlermeldung" }
```

---

## Umgebungsvariablen

`.env` Datei im Projektroot erstellen:

```env
RESEND_API_KEY=dein_resend_api_key
PORT=3001
```

---

## Docker

```bash
# Image bauen
docker build -f Dockerfile.backend -t portfolio-backend .

# Container starten
docker run -p 3001:3001 --env-file .env portfolio-backend
```

---

## Deployment (Render)

1. Repository auf GitHub pushen
2. Auf [render.com](https://render.com) neuen **Web Service** erstellen
3. Repository verbinden
4. Umgebungsvariable `RESEND_API_KEY` in den Render-Einstellungen hinterlegen
5. Render deployed automatisch bei jedem Push auf `main`

---

## Autor

**Alper Caliskan**
- GitHub: [@alper42](https://github.com/alper42)
- Website: [alper42.github.io/portfolio](https://alper42.github.io/portfolio)
