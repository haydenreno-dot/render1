# Arras Open - Render server

This package is prepared to run the Arras Open Node.js server as a Render Web Service.

## Render settings

The included `render.yaml` uses:
- Build: `npm install`
- Start: `npm start`
- Node: 22
- Health check: `/isOnline`

The server is configured to use Render's `PORT` and `RENDER_EXTERNAL_HOSTNAME` automatically and runs one FFA game server on the same public HTTP/WebSocket endpoint. Render supports inbound WebSocket connections on Web Services.

## Developer token

The requested developer token is set to `arras-open1072` in `server/.env`. If this project is put in a public repository, treat that value as public and change it before using it for anything sensitive.

## Connecting the Netlify frontend

After Render deploys, its service will have an `https://...onrender.com` URL. The game client must request `/getServers.json` from that server (or otherwise be configured to use the Render server URL) and connect to its WebSocket endpoint. Use `wss://` for the public WebSocket connection.
