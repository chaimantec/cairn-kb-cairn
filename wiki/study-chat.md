# The AI study chat

The study chat is an assistant that sits in the [Live tab](live-tab.md), beside
your notes, while a lecture plays. Its whole reason for existing is context:

*"It already knows which course you are in, which lecture is playing, and the
second you are paused at — so you can point at something with 'this' and it
knows what you mean."*

It arrived in version **1.3.0**, alongside [knowledge bases](knowledge-bases.md).

## Turning it on

Two conditions, both required:

1. **Be signed in.** Guests see the Chat tab locked with a sign-in hint.
2. **Save your own API key** for DeepSeek or OpenRouter in **Settings**. Until
   then the composer is disabled. See [bring your own key](bring-your-own-key.md).

There is no Cairn-provided model and no free tier to run out of. You pay a
provider directly, at their price.

## What it knows without being told

Every message you send carries, automatically:

- the **course** code and title,
- the **lecture** title,
- your **playback position** in that lecture, to the second,
- anything you have asked it to [remember](chat-memory.md).

That is why "wait, what did he just say?" works. The position is attached to the
turn, so the assistant resolves "this", "here" and "what he just said" against
the moment you are actually paused at.

A chat is scoped to one lecture. Move to another lecture and you are in that
lecture's chats; the course and lecture context change with you.

## What it can do

Depending on what is configured, it has tools rather than only its own memory —
each shows as a chip in the transcript when it runs, so you can see what it
looked at:

| Capability | Needs | What it does |
|---|---|---|
| Read the course [knowledge base](knowledge-bases.md) | The course has one attached | Reads the actual transcripts, slide text and topic pages for this course, and cites the file. |
| Search and read the web | A Tavily key saved | Looks things up outside the course and reads specific pages. |
| Remember how you like answers | Nothing | Saves standing instructions that apply to every future chat. |

See [what the chat can look up](chat-tools.md) for the details of each.

## How it writes

It is told to answer clearly and concretely, to prefer worked explanations over
vague summaries, and to keep formatting light. Mathematics is written in LaTeX
and **rendered**, not flattened into ASCII — which matters when the thing you are
asking about is a derivation on a slide.

When the course has a knowledge base, it is instructed to treat that as more
reliable than its own memory, to read the relevant page before answering rather
than guessing from titles, and to cite the file it used. When the knowledge base
does not cover your question, it is told to say so plainly and answer from its
own knowledge or the web, rather than blurring the two.

## Images

You can attach a screenshot, a photo of a problem set, or your own written work —
or grab the current frame of the lecture in one click. It is told to work from
what is actually in the image rather than describing it back to you. See
[images in chat](images-in-chat.md).

## Where the conversation lives

**In your browser, not on Cairn's servers.** Chats are stored in extension local
storage, are not tied to your account, do not sync between devices, and are not
recoverable if you clear the extension's data. They survive signing out. See
[privacy and your data](privacy-and-data.md) and [managing chats](managing-chats.md).

## Related pages

- [Bring your own key](bring-your-own-key.md) — providers, cost, where keys live
- [Models and thinking levels](models-and-thinking.md)
- [Asking good questions](asking-good-questions.md) — what it is actually good at
- [Chat memory](chat-memory.md)
- [Troubleshooting](troubleshooting.md)
