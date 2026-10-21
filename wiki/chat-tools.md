# What the chat can look up

The [study chat](study-chat.md) is not a plain text box wired to a model. It has
tools, and it decides when to use them. Each one shows as a chip in the
transcript as it runs, so you can see what the assistant actually consulted
before it answered — and tell the difference between a researched answer and one
from the model's own memory.

Which tools exist depends on your setup:

| Tool | Appears when | What it does |
|---|---|---|
| `kb_read` | The course has a [knowledge base](knowledge-bases.md) | Reads one file from it. |
| `kb_list` | Same | Lists what files exist, optionally under a directory. |
| `web_search` | A Tavily key is saved | Searches the web and returns titles, URLs and snippets. |
| `web_fetch` | Same | Reads a specific web page. |
| `memory_add` / `memory_update` / `memory_delete` | Always | Saves, changes or forgets a standing instruction. |
| `note_post` | Always | Saves something from the conversation as a note on the lecture. |

## Reading the knowledge base

When a course has one, this is the assistant's primary source, and it is told to
treat it as more accurate about that specific course than its own memory.

The pattern it follows is: read `INDEX.md` first to see what exists, follow the
relative links from there to the specific page, and read it before answering
rather than guessing from the title. `kb_list` fills the gap when it needs a
file the index does not mention.

Two things fall out of this that are useful to know as a user:

- **Transcripts are quotable.** Lecture transcripts in a knowledge base are
  stored one timestamped paragraph per line, so the assistant can page through
  to a moment and quote what was actually said, rather than paraphrasing from
  memory.
- **Every citation is a real link.** Each read hands back that file's GitHub URL,
  and the assistant is told to cite that URL rather than assembling one — and
  never to link a file it has not actually read. So a citation in an answer is a
  link you can open. Slides and PDFs are cited the same way: the link is
  returned instead of the file contents, so you get the actual deck.
- **Slide images come back as pictures.** When a knowledge base holds rendered
  slides and the assistant reads one, what comes back is an address it can
  display, so the slide appears in the answer rather than as a link to click.
  Reading an address that is not in the repository returns an error instead,
  which is what stops it guessing one. See
  [images in chat](images-in-chat.md).

Long files come back in pages of about 500 lines, with a note saying how much of
the file you received, so the assistant can keep reading if the part it needs is
further down.

### Reading another course's knowledge base

A course often assumes material another course teaches. If this course's
knowledge base has a `SEE_ALSO.md` listing related courses, the assistant can
read those repos too, with the same tools, and will say which course an answer
came from. It is told to take the repo URL from `SEE_ALSO.md` or from you
directly, and never to guess one from the naming pattern — so if you want it to
consult a specific knowledge base, paste the repo URL.

## Searching the web

`web_search` and `web_fetch` exist only if you have saved a Tavily key. They are
for what the course materials do not cover: recent developments, an alternative
explanation, the paper a lecture cites. Sources come back as markdown links.

Without a Tavily key the chat has no web access at all, which is a perfectly
reasonable way to run it — the course materials are usually what you want.

## Remembering how you like answers

The memory tools are always available, since they need no configuration. They
are covered in [chat memory](chat-memory.md). The short version: the assistant
changes memory only when you ask it to, never on its own initiative, and never
to store notes about what you are studying — that is what
[saving a note](#saving-a-note-to-the-lecture) is for.

## Saving a note to the lecture

When an exchange produces something worth keeping, ask the assistant to save it:
*"save that as a note"*, *"pin this to the lecture"*, *"note the bit about the
scaling factor"*. It writes the point up as a [note](traces-and-notes.md) and
posts it to the lecture you are watching, where it sits in the Notes feed
beside the ones you write yourself.

- **Only when you ask.** It never saves a note on its own initiative. If an
  answer looks worth keeping it may offer once, and then waits for a yes.
- **Marked as AI-written.** The note starts with a 🚩 — the same flag the
  [annotation skill](annotating-lectures.md) puts on its markers — so you can
  tell at a glance which notes you did not write.
- **Pinned where you are.** By default it goes at your playback position when
  you sent the message. If the point belongs to a different moment, such as one
  the assistant found in a timestamped transcript, it pins it there instead, and
  it cannot pin one past the end of the lecture.
- **Private unless you say otherwise.** Ask for a public note and it posts one,
  shown to everyone on that lecture under your nickname, like any
  [trace](traces-and-notes.md).
- **Written to be read cold.** It is told to write a few sentences that make
  sense weeks later with the video paused at that moment: the actual idea and
  why it matters, not "as discussed above". Notes show text exactly as written,
  so formulas are spelled out in words rather than in LaTeX.

The chip reads **Saved a note**, and the reply says where it was pinned. Because
the note is pinned at the moment you are watching, it also floats over the chat
straight away, the same way any nearby note does.

From then on it is an ordinary note. Edit it, delete it, or make it public from
the Notes side, and it syncs to your devices like the rest. One thing to know if
you also use the annotation skill: a re-run of that skill on a lecture removes
every 🚩 note on it before posting fresh markers, and that includes notes the
chat saved.

## When there is no knowledge base

The assistant says so and answers from its own knowledge, and from the web if
Tavily is configured. It is also told to mention that the course's creator can
add a knowledge base URL in the course's edit dialog — see
[attaching a knowledge base](attach-a-knowledge-base.md).

## Related pages

- [Knowledge bases](knowledge-bases.md)
- [Traces and notes](traces-and-notes.md)
- [Asking good questions](asking-good-questions.md)
- [Bring your own key](bring-your-own-key.md)
