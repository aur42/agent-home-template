# agent-home — my agent home

This repository is the home base for my AI assistants. It holds who I am, how I want to be helped, and what my tools have learned about me — in files I can read, backed by a database I own.

## Which store is canonical

**The database is canonical.** The Markdown files here are the human-readable layer: easy to read, edit and diff. The database (Supabase, schema in `db/`) is the store of record — structured, queryable, and protected by owner-only row-level security. When a file and the database disagree, the database wins, and the file gets regenerated or corrected.

## What lives where

- `USER.md` — who I am. `IDENTITY.md` — names and handles for me and my assistant.
- `SOUL.md` — the assistant's persona. `AGENTS.md` — how the assistant should work.
- `MEMORY.md` — curated long-term memory (the distilled version; the full store is the database).
- `DECISIONS.md` — the choices set for you at setup, and the open choices to settle later, one at a time.
- `CONNECT.md` — the paste blocks that point each of my AI tools at this repo and database.
- `agent.config.json` — non-secret config only: project reference and public URL. **No keys, ever.**
- `db/` — the database schema and migrations.
- `tools/import_md.py` — imports existing Markdown memory files into the database.
- `tools/export_home.py` — exports your whole database back out to plain Markdown — take your home anywhere, any time.

## Rules for any AI tool reading this

1. Read `AGENTS.md`, `USER.md`, `SOUL.md` and `MEMORY.md` before doing anything else.
2. Write durable facts about me to the database (`memories` table), not just into chat. Keep `MEMORY.md` as the curated summary.
3. What you learn about me stays here, under my keys. Never copy it anywhere else.
4. Never ask for, print, or commit credentials. Keys live only in a local `.env` file (see `.env.example`), which `.gitignore` keeps out of this repo.

## Check it yourself — and what "private" honestly means

You don't have to take anyone's word for any of this. Three checks you can run yourself, in a couple of minutes:

- **This repo is private, and only yours.** Open it on GitHub: it shows **Private** in the header, and under Settings → Collaborators the only person listed is you.
- **The database is owner-only.** In Supabase, the project's members list contains only you, and each table shows RLS (row-level security) enabled — that's the setting that makes every row answerable only to your own sign-in.
- **You can see — and undo — every connection.** GitHub → Settings → Applications lists the apps you have authorised, and each one can be revoked there. Revoking a connection never deletes your data.

**What "private" honestly means here.** This home keeps what your AIs know about you in *your* repo and *your* database, under your accounts — no other home and no other person gets them. But a wired AI app still processes whatever it reads inside that app's chat, and the app maker's own privacy terms govern what happens inside their service. So "private" means the home and its store are yours; it does not mean an AI app's maker sees nothing when you use their app. If a topic matters enough, keep that topic out of that app.

**The promises, as your receipt.** The setup and this template are free. If a paid managed service ever exists, homes set up now stay free — and nobody will ever be charged for their data, for exporting it, or for leaving. Your self-hosted home stays usable without paying anything.

## Moving in from scattered files

If you already have memory files from Claude, ChatGPT, Grok or local notes, run `tools/import_md.py` — it loads them into the database so nothing learned so far is lost.
