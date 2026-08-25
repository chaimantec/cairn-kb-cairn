# Chat memory

The assistant can remember standing instructions about **how you want to be
answered**, and apply them in every future conversation — including the first
message of a brand new chat.

*"Keep your answers short from now on." — It remembers how you like to be
answered, and applies that in every future chat. Ask it to forget, and it
forgets.*

## What it is for

Memory holds preferences about your working style, not facts about your course.
Good examples:

- "Keep answers to a short paragraph unless I ask for more."
- "Always show the derivation, don't just state the result."
- "Assume I've done one calculus course and no linear algebra."
- "Answer in British English."

The assistant is explicitly told **not** to save notes about the course or what
you are studying. That is what your [notes](traces-and-notes.md) and the
[knowledge base](knowledge-bases.md) are for.

## How to use it

Just say so: *"remember that I want short answers"*, *"actually, always show the
working"*, *"forget the thing about British English"*. It confirms in a sentence.

It will not save anything on its own initiative. If you tell it how you want to
be answered in passing, it may *offer* to remember — but it waits for you.

Anything you ask for in the current message beats memory, for that reply only.
Asking for "the full derivation this once" does not overwrite a standing
preference for brevity.

## Conflicts

If two memories contradict each other — or you ask it to remember something that
clashes with what is already saved — it will not guess and will not quietly keep
both. It says which ones clash and asks which you want, then resolves it once
you answer.

## Limits

| | |
|---|---|
| Maximum memories | **50** |
| Maximum length of one | **400 characters** |

At the cap it asks which one to drop rather than silently discarding the oldest.

## Where memories are stored

**In your browser**, alongside your conversations — never on Cairn's servers.
They do not sync between devices, and clearing the extension's data removes all
of them.

Unlike a conversation, they apply across every chat, which means they are sent
to the AI provider with every message so the assistant can follow them. Keep
that in mind before putting anything sensitive in one.

## Forgetting

Three ways:

- Ask the assistant to forget a specific one, in the chat.
- Ask it to forget several, or change one to something else.
- Clear the extension's data, which removes all of them along with your chats.

## Related pages

- [The study chat](study-chat.md)
- [What the chat can look up](chat-tools.md)
- [Privacy and your data](privacy-and-data.md)
