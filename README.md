# Gamaliel for Raycast

Ask biblical questions from [Raycast](https://www.raycast.com) and read answers from the [Gamaliel API](https://developer.gamaliel.ai/llms.txt). Scripture references render as markdown links and open the passage in your browser on [Gamaliel](https://gamaliel.ai).

Repository: [gamaliel-ai/gamaliel-raycast](https://github.com/gamaliel-ai/gamaliel-raycast)

## Install locally

1. Install [Raycast](https://www.raycast.com) and [Node.js 22.22.2+](https://nodejs.org).
2. Clone this repo and install dependencies:

```bash
git clone https://github.com/gamaliel-ai/gamaliel-raycast.git
cd gamaliel-raycast
npm install
npm run dev
```

3. Open Raycast and run **Ask Gamaliel**.

`npm run dev` registers the extension in development mode with hot reload. Stop the process with `Ctrl+C`; the command stays installed until you remove the extension from Raycast preferences.

## Use

- Run **Ask Gamaliel**, type a question, and press Return.
- The answer is shown as markdown. Click a scripture link to open that passage on [gamaliel.ai](https://gamaliel.ai).
- Use **Ask Another Question** to follow up (up to 20 user messages), or **New Conversation** to start over.

## Preferences

Open **Raycast Settings → Extensions → Gamaliel** to set:

| Preference | Default | Notes |
| --- | --- | --- |
| Theology | General Christian | Perspective passed as `theology`. |
| Profile | Universal Explorer | Experience level passed as `profile`. |
| Bible Translation | English NIV | Translation passed as `bible_id`. The Ask Gamaliel search bar also has a language-grouped picker. |
| Max Words | 300 | Answer length cap. |

## API

Answers come from `POST https://api.gamaliel.ai/v1/chat/completions`, an OpenAI-compatible chat endpoint. Gamaliel converts scripture references to markdown links such as `[Matthew 5:1–16](/read/MAT/5?verse=1-16)`. This extension rewrites those paths to `https://gamaliel.ai/read/...` so Raycast can open them in a browser.

See the [Gamaliel public API notes](https://developer.gamaliel.ai/llms.txt) for models, theologies, profiles, and rate limits.

## Develop

```bash
npm run dev      # hot reload in Raycast
npm run lint     # eslint
npm run build    # production build
```
