---
title: Zelda AI
---

# Zelda AI

Zealous Digital Assistant (or _Zelda_ for short) is a GPT-3.5 based virtual assistant helping me with day-to-day tasks.

She has its own memory, she knows who I am, who my wife and daughter are, what we were discussing previously. She can execute simple actions on my behalf (e.g. preparing an invoice for my current client, adding events to my Google Calendar, translating longer texts etc.).

I talk with her using [Telegram](/Knowledge/AI/telegram-make-bot.md) and ask her for actions with Shortcuts.

Zelda is a big project that I am improving gradually whenever I have some spare time. Ultimately I want her to become ~~a sentient ai destroying the world~~ an assistant that I could delegate mundane things to.

## Current stack

The current stack is based on the notes from [AI Devs](https://aidevs.pl) course, where I've developed skills related to [GPT](/Knowledge/AI/GPT.md) and automation things with it.

- Make.com
  - a prototypic _backend_ for handling simple related actions
- NestJS
  - I moved some parts from Make.com to my own backend to reduce costs (Make is rather pricey)
  - I want to move all the whole Make scenario to code at some point
- Pinecone and Airtable
  - databases for handling Zelda's memory
- [...]
