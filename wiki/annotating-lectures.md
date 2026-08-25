# Annotating lectures with an agent

The `cairn-annotate` skill drafts **timed study markers** across a lecture and
posts them back into Cairn as your own personal notes, at the timestamps they
refer to. They appear in the [Live tab](live-tab.md) feed exactly like notes you
wrote yourself, prefixed with a 🚩 so they are easy to find and replace on a
re-run.

It is the second of Cairn's two agent skills; the other builds
[knowledge bases](building-a-knowledge-base.md).

## What it is for

Pre-marking a lecture before you watch it, so the hard turns are flagged as you
reach them — or marking up a lecture you have finished, as a revision aid. The
markers are timestamped, so they surface in the feed as the lecture plays rather
than sitting in a wall of text.

## How it works

It fetches the lecture's transcript, picks out the moments worth marking, and
writes each marker back through Cairn's API against the right second. When the
course has a [knowledge base](knowledge-bases.md) attached, the markers are
drafted from that instead of from raw YouTube captions, which produces
noticeably better ones — the knowledge base has the corrected terminology and
the slides.

## What it will and will not touch

- Markers are posted as **personal notes**, never public. They are yours, and
  they sync to your devices like any other note.
- It only annotates lectures in courses **you created** in the catalog. It
  refuses other people's courses.
- The 🚩 prefix exists so a re-run can find and replace its own previous
  markers rather than piling duplicates on top.

You can edit any marker afterwards, delete it, or make it public if you decide
it is worth leaving as a [trace](traces-and-notes.md) for other learners.

## Requirements

An agent that can run the skill, and a session token from the extension so it
can read and write your notes. The drafting is done by whichever model is
running the skill — there is no separate API key, and it is unrelated to the
[key you save for the study chat](bring-your-own-key.md).

## Related pages

- [Traces and notes](traces-and-notes.md)
- [Building a knowledge base](building-a-knowledge-base.md)
