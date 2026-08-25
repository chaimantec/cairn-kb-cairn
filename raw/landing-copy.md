---
title: cairnstudy.com — the site's own words (verbatim)
source: https://cairnstudy.com/
copied: 2026-08-26
---

> Verbatim copy of the marketing copy on Cairn's landing page, section by
> section. This is how Cairn describes itself in public. Layout, styling and
> images are dropped; the wording is unchanged.

## Hero

**Finally finish YouTube courses.**

Cairn is a Chrome extension for people working through real university lecture
series — Stanford CS, MIT OCW, and the rest. It tracks your progress across
devices, and surfaces *traces* left by other learners who came before.

Meta description: "A Chrome extension that helps self-directed learners finish
university lecture courses on YouTube. Auto-tracks progress, surfaces traces
from other learners."

## How it works — "Three things, done quietly."

**01 / Track — Track your progress automatically.** Cairn watches what you watch
on YouTube and tracks it against your enrolled courses. There is no "mark
complete" button to click. Sign in and your progress follows you to the next
computer, picking up where you left off — at the second you left off.

**02 / Traces — Find traces from other learners.** When you reach a hard moment
in a lecture, see notes left by people who were there before you. Each trace is
anchored to the second it was posted. It is not a conversation — it is a marker
on a trail. You can leave one of your own and keep walking.

**03 / Sync — Pick up on any computer.** Sign in with Google and your courses,
progress, and notes follow you across devices. Watch a lecture on your laptop,
finish it on your work computer. No account needed if you'd rather keep things
local — Cairn works fully offline as a guest.

## What's different — "Traces, not chat."

Cairn is built around the idea that other people walked this trail before you,
and what they left behind can help. Most YouTube tools are built for the solo
note-taker.

A trace is a short, timestamped note pinned to a moment in a lecture. You see
traces only at the seconds they were posted, and only when they are useful — at
the kinds of moments where someone reached out a hand. There are no follower
counts, no DMs, no replies threading off into the woods. People appear under
anonymous nicknames they choose.

The course catalog grows from the people walking the trail. Anyone can add more.

The one conversation Cairn does have is the optional study chat, and it is
private to you — you are talking to an assistant about the lecture, not to other
learners. Between people, Cairn stays asynchronous on purpose.

| | |
|---|---|
| **Identity** | Anonymous nicknames. No real names, no avatars. |
| **Surface** | Traces appear in context, never as a feed. |
| **Catalog** | Community-curated. Anyone can add a course. |
| **Pressure** | No follows, no replies, no DMs. |

## Study chat — "Ask without leaving the lecture."

Cairn has an optional AI study chat in the sidebar. It already knows which
course you are in, which lecture is playing, and the second you are paused at —
so you can point at something with "this" and it knows what you mean.

- *"Wait — what did he just say?"* — It has your exact timestamp, and pulls that
  moment out of the lecture transcript.
- *"Where do the slides derive this? I want to see the steps."* — It cites the
  actual slide deck or handout from the course materials, linked, so you can
  open the PDF and read it yourself.
- *"Explain this like I've only done one calculus course."* — Answers are
  written out properly, with real mathematical notation rendered rather than
  mangled into ASCII.
- *"Didn't lecture 3 already cover this?"* — It can read across the whole
  course, not just the lecture you are on.
- *"Keep your answers short from now on."* — It remembers how you like to be
  answered, and applies that in every future chat. Ask it to forget, and it
  forgets.

### "It did the reading first."

A general chatbot is vague about a specific course. So courses on Cairn can
carry a knowledge base: a public GitHub repository built from that course's own
materials — every lecture transcript, the slide decks and handouts from the
course website, and topic pages compiled from them and linked together.

When a course has one, the chat reads it before answering and treats it as more
reliable than its own memory, citing the file it used so you can go and read the
source yourself.

### "Look at one."

The knowledge base for Stanford's CS224N — Natural Language Processing with Deep
Learning — is public: `chaimantec/cairn-kb-cs224n`. All 23 lectures, with
timestamped transcripts, the full text of every slide deck, and 86 interlinked
topic pages.

### "You don't have to use Cairn to read it."

A knowledge base is ordinary markdown in a public Git repository, with an
`AGENTS.md` at the root explaining how it is laid out. So you can browse it on
GitHub, clone it, or point Claude Code, Codex, or any other agent at it and work
through the course there instead. Nothing in it is locked to the extension —
which also means you can check what the assistant is working from, and correct
it.

Not every course has one yet. They are built course by course, and whoever added
a course to the catalog can attach a knowledge base to it. Courses that have one
link to it from the catalog.

### Bring your own key

The chat is off until you add your own API key from DeepSeek or OpenRouter, so
you pay the model provider directly at cost — Cairn takes no cut and resells
nothing. Your key is stored encrypted and never sent back to your browser, and
your conversations are kept in your browser rather than on Cairn's servers. The
privacy policy explains exactly where each message goes.

## Honest about what this is — "A side project."

Cairn is a free side project. It exists because the person who made it kept
abandoning Stanford CS and MIT OCW courses around lecture four, and wanted a
tracker tool that is accessible. If that's you too — welcome.

## Footer

**Cairn — Stone markers for self-directed learners.**

- Site: cairnstudy.com
- Email: hello@cairnstudy.com
- Chrome Web Store: https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim

© 2026 Cairn. An independent project. Not affiliated with YouTube, Stanford, or
MIT.
