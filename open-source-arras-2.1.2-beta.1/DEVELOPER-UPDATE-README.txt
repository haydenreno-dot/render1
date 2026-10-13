Arras Open developer-token popup update
========================================

Changes in this package:
- Ctrl+Shift+Alt+P opens the developer token dialog.
- The dialog POSTs the token to /api/verifyDeveloper; the server compares it against the DEVELOPER environment variable.
- The token is not put in the URL and is not saved to localStorage. A successful verification marker lasts only for the current browser session.
- Existing Siege configurations are included in the original source (siege_classic, siege_blitz, siege_citadel, siege_fortress). The actual running game mode is selected by the server configuration/deployment, not by this shortcut.

Render setup:
- Keep Build Command: npm install
- Keep Start Command: npm start
- In Render Environment, set DEVELOPER to a new secret token. Do not paste the token into public code or chats.
- Push the changed files to GitHub and redeploy Render.

IMPORTANT LIMITATION:
This update adds the working token dialog and server-side token verification endpoint. It does NOT yet implement tank spawning/multibox control or wire a verified permission into the WebSocket gameplay protocol, so pressing backslash will not spawn extra tanks yet. Do not treat the session marker alone as authorization for privileged server actions. Siege files/configs exist already, but this package does not automatically change which mode Render starts.
