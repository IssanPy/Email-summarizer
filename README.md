This repo contains:
- Apps Script (Gmail Add-on) code: apps_script/Code.gs and appsscript.json
- Node.js backend: backend/index.js, package.json
- .env.example

The add-on reads the opened Gmail message, sends it to the backend (with the user's Google OAuth token), the backend verifies the token, calls OpenAI to summarize the email, and returns the summary.



1. Clone or copy this repo.
2. In `backend/` run:
   ```
   npm install
   cp .env.example .env
   # set OPENAI_API_KEY and GOOGLE_CLIENT_ID in .env
   npm start
   ```
3. For Apps Script testing you can expose your local server with ngrok:
   ```
   npm install -g ngrok
   ngrok http 3000
   ```
   Use the https ngrok URL as BACKEND_URL in Apps Script properties.


- Push to GitHub and connect to Vercel or Render for automatic deployment.
- Set environment variables (OPENAI_API_KEY, GOOGLE_CLIENT_ID) in the host's dashboard.


- Create a new Apps Script project, paste `apps_script/Code.gs`, and add `appsscript.json` to the project manifest.
- Set Script Properties: BACKEND_URL to your deployed backend URL.
- Authorize required scopes and test the add-on.

See full instructions in the project canvas or ask for step-by-step guidance.
