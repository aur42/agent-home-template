# CONNECT.md — Point your AI tools here

_This file is generated per person by the setup page, with your real repo and database URLs filled in. The version in the template repo uses placeholders — replace `YOUR-USERNAME` and `YOUR-PROJECT-REF`, or regenerate it from the setup page._

Honest label: there is no uniform one-click OAuth into every AI tool. The honest version is **one button that generates all the paste blocks below** — you paste each block once, into that tool's custom instructions / project instructions / system prompt.

---

## For every tool — the universal block

```text
My agent home is a private GitHub repo: https://github.com/YOUR-USERNAME/agent-home
My personal database is: https://YOUR-PROJECT-REF.supabase.co (Supabase, owner-only RLS)

How to use it:
1. Open the repo through your own GitHub connection (connect GitHub in your settings and allow only this repo). If you cannot open it, reply exactly: I can't read your agent home yet. Never guess what is in it.
2. At the start of a conversation, read USER.md and MEMORY.md. Read other files only when the task needs them.
3. Call me by the name in USER.md and use what MEMORY.md says about me, so I never repeat myself.
4. When I tell you something worth keeping, offer one short line for MEMORY.md and wait for my yes before writing it.
5. Never write passwords, keys or other people's private details into the repo.
6. If I ask "are you wired in?", reply with the phrase on the "Verification phrase:" line of MEMORY.md, word for word, then my name from USER.md and one fact from MEMORY.md.
```

## Muse

Paste the universal block into Settings → Custom Instructions, and add the repo as a project source if your plan supports it.
_Capability, honestly: custom instructions alone don't give Muse access to a private repo — it can read your home only when the repo/files are attached as a project source or the tool is connected to your database. Without that, it has the block's snapshot, not live files._

## Claude

Create a Project named "Agent Home", paste the universal block as the project instructions, and upload USER.md / MEMORY.md / AGENTS.md as project knowledge.
_Capability, honestly: Claude cannot open your private repo from a link by itself — the uploaded files ARE its copy of your home. Re-upload after big edits to MEMORY.md or USER.md._

## ChatGPT

Paste the universal block into Settings → Personalization → Custom Instructions.
_Capability, honestly: custom instructions don't grant file or database access. ChatGPT works from the pasted block (a snapshot) unless you also give it the files or a connector in the conversation._

## Grok

Paste the universal block at the start of a new conversation, or into its custom instructions where available.
_Capability, honestly: a block pasted into one conversation is a snapshot for that conversation only._

## Instinct

Paste the universal block into its instructions for you.

