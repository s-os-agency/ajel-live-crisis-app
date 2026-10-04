# AJEL (عاجل) — plain-language README

## What this is
AJEL (Arabic for "urgent") is a web dashboard that shows what is happening right now in the Middle East. It collects news and humanitarian reports from several sources, and can summarise them with AI. This is version 2.

## Who it's for
Analysts and leaders who need a quick, current picture of crises in the region.

## What it does today
- **Login**: only signed-in users get in.
- **Live news** from:
  - GDELT (a global news monitor)
  - ReliefWeb (UN humanitarian updates)
  - NewsAPI (optional)
- **AI summary**: an executive summary and insights, written by OpenAI if a key is set. Without a key, it uses simpler built-in rules.
- **Watchlists**: save topics or places to keep an eye on.
- **Bookmarks** with your own notes.
- **Snapshots**: a copy of the picture is saved automatically every few minutes, so you can look back.
- Data is kept in a local database file (`data/ajel.sqlite`).

## How to run it
You need Node.js.
```bash
npm install
cp .env.example .env.local
npm run dev
```
A default admin login is set in the example settings file. **Change the email, password and session secret in `.env.local` before using it.**

Settings used:
- Required: `AJEL_ADMIN_EMAIL`, `AJEL_ADMIN_PASSWORD`, `AJEL_SESSION_SECRET`
- Optional: `OPENAI_API_KEY`, `OPENAI_MODEL`, `NEWS_API_KEY`, `RELIEFWEB_APPNAME`

## Current status and known gaps
- Where it's hosted: not yet confirmed.
- Only one admin account, set in the settings file.

## Where things live
| Page / address | What it is |
|---|---|
| `/login` | Sign in |
| `/dashboard` | Main situation room |
| `/api/live` | Live briefing data |
| `/api/watchlists`, `/api/bookmarks`, `/api/snapshots` | Saved items |
| `data/ajel.sqlite` | Database file |
