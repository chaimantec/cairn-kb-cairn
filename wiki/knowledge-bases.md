# Knowledge bases

A knowledge base is a **public GitHub repository built from one course's own
materials** — every lecture transcript, the full text of the slide decks and
handouts from the course website, and topic pages compiled from them and linked
together. When a course has one, the [study chat](study-chat.md) reads it before
answering.

The problem it solves is stated plainly on Cairn's site: *"A general chatbot is
vague about a specific course."* A model asked about lecture 12 of a particular
class is working from whatever it absorbed about the subject in general. A
knowledge base gives it the actual lecture.

## What it changes

With one attached, the assistant:

- **reads before answering** — it opens `INDEX.md`, follows links to the page
  that matters, and reads it, rather than guessing from titles;
- **treats it as more reliable than its own memory** for anything about that
  course;
- **cites the file it used**, as an openable GitHub link, so you can check it;
- **can quote the transcript** at a specific moment, and point you at a specific
  slide or handout PDF;
- **says so when the knowledge base does not cover your question**, and answers
  from general knowledge instead — rather than blurring the two.

## What is in one

Roughly, for each course:

- **Lecture transcripts**, timestamped paragraph by paragraph, so a moment can be
  quoted and cited.
- **Slide decks transcribed slide by slide** — the text, the equations as
  written, tables of numbers, and figures described in prose.
- **Wiki pages**: one per lecture, plus topic pages for concepts that span
  several lectures, all interlinked.
- **An index** naming every page with a one-line description of what it holds.
- **A source inventory** recording where each document came from.

The full layout is in [knowledge base repo layout](kb-repo-layout.md).

## The worked example

Stanford's CS224N — Natural Language Processing with Deep Learning — has a
public one:
[`chaimantec/cairn-kb-cs224n`](https://github.com/chaimantec/cairn-kb-cs224n).
All 23 lectures, with timestamped transcripts, the full text of every slide
deck, and 86 interlinked topic pages. It is worth opening once just to see the
shape of the thing.

## You do not need Cairn to read one

*"A knowledge base is ordinary markdown in a public Git repository, with an
`AGENTS.md` at the root explaining how it is laid out. So you can browse it on
GitHub, clone it, or point Claude Code, Codex, or any other agent at it and work
through the course there instead."*

Two consequences follow, and both are deliberate:

- A knowledge base is **useful on its own**, independent of the extension. Clone
  it and study from it.
- The assistant's sources are **auditable**. You can read exactly what it is
  working from, and correct it — a knowledge base is a repository, so it takes
  pull requests.

Repositories must be **public**: the chat fetches them unauthenticated. A private
repo simply reads as a missing knowledge base.

## Which courses have one

Not many yet. *"They are built course by course, and whoever added a course to
the catalog can attach a knowledge base to it. Courses that have one link to it
from the catalog."* Look for the knowledge-base link on a course card or in the
[catalog](catalog.md).

If a course you care about does not have one, either build it — see
[building a knowledge base](building-a-knowledge-base.md) — or ask whoever
created the catalog entry.

## Related knowledge bases

A knowledge base can list sibling courses in a `SEE_ALSO.md` file, saying what
each is good for. When a question turns on background this course assumes rather
than teaches, the assistant can read that other course's knowledge base too, and
will say which course the answer came from. You can also just paste a repo URL
and ask it to read that one.

## Related pages

- [Attaching a knowledge base](attach-a-knowledge-base.md) — the two-minute version
- [Building a knowledge base](building-a-knowledge-base.md) — the long version
- [Knowledge base repo layout](kb-repo-layout.md)
- [What the chat can look up](chat-tools.md)
