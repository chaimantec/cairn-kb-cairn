# Knowledge base repo layout

A [knowledge base](knowledge-bases.md) is an ordinary public Git repository of
markdown. The layout is a contract: the chat's reading tools expect `INDEX.md`
at the root and navigate by following relative links from there.

```
INDEX.md              entry point — course summary + annotated table of contents
AGENTS.md             how this wiki is organized, for whoever maintains it
SEE_ALSO.md           related courses' knowledge bases, by repo URL (optional)
TODO.md               build tracker — the resumable state of the build
kb.json               machine-readable self-description: coverage, method, caveats
wiki/                 durable pages: one per lecture, plus cross-lecture topics
raw/transcripts/      lecture transcripts with [MM:SS] paragraph marks
raw/slides/           full text of every slide, numbered
raw/pdfs/             slides and handouts, when committed at all
sources.md            inventory: canonical source URL → local file, fetch date
```

## The files that matter most

**`INDEX.md`** is the front door and the single most important file — the
assistant reads it first in every conversation. It carries a couple of sentences
on what the course covers, then an annotated table of contents naming every page
with a one-line description of what a reader will find there. Those one-liners
are what let the assistant pick the right page without reading all of them. **A
page that is not in the index is effectively invisible.**

**`AGENTS.md`** explains the organizing scheme to whoever maintains the
repository next — human or agent. Its presence is part of what makes a knowledge
base readable outside Cairn: point any coding agent at the repo and it can work
out the layout from this file.

**`kb.json`** is the machine-readable half of `INDEX.md`. It states coverage —
how many lectures of how many are actually done — and how the course materials
were transcribed, which is what tells a reader whether a citation can be
trusted. A knowledge base covering 4 of 20 lectures is useful for those four and
misleading if cited as the course, so it says so in both places.

**`SEE_ALSO.md`**, when present, lists related courses' knowledge bases by repo
URL with a line on what each is good for. It is the only way the assistant
learns that a sibling knowledge base exists; it is told not to guess repository
names.

## Conventions inside the wiki

- **Relative links** between pages, so the repo survives being renamed or
  forked.
- **Every claim traceable** — to a transcript timestamp, or to a numbered slide.
- **Prose in full sentences**, because the assistant quotes these pages to
  learners and fragments quote badly.
- **Mathematics in LaTeX**, `$…$` inline and `$$…$$` displayed, never inside a
  code fence. It renders both in Cairn's chat and on github.com.
- **Nothing invented.** Where the source material is unclear, the page says so
  rather than filling the gap from outside knowledge — a knowledge base that
  silently mixes in outside material is worse than one with a stated gap,
  because the chat presents it as authoritative course content.
- **Transcripts stay verbatim.** Reconstructing notation belongs in `wiki/`, not
  in `raw/transcripts/`.

## Practical requirements

- The repository must be **public**.
- Binary files are never read as text: when the assistant reaches a PDF it
  returns the link instead of the contents, so the learner gets the actual deck.
- Long files are read in pages, so large transcripts are fine.

## Related pages

- [Knowledge bases](knowledge-bases.md)
- [Building a knowledge base](building-a-knowledge-base.md)
- [Attaching a knowledge base](attach-a-knowledge-base.md)
