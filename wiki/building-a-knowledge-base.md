# Building a knowledge base

Knowledge bases are not built inside the extension. They are compiled outside it
by an agent — the **`cairn-kb` skill**, written for Claude Code — which fetches
transcripts, reads the course's slide decks, writes the wiki, pushes the
repository to GitHub, and attaches the URL to the catalog entry.

This page is the user-facing account of what that involves. It is not a manual
for the skill.

## What you need

- The course already in Cairn's [catalog](catalog.md), **created by you**. The
  build's last step writes the knowledge base URL onto the catalog entry, and
  only the entry's creator may do that.
- A GitHub account, and somewhere to put a **public** repository.
- The course website URL, if the class has one. Without it the build is
  transcript-only, which is still useful but misses the slides.
- An agent that can run the skill, and a session token from the extension so it
  can read your course's lecture list.

## What it does, roughly in order

1. **Resolves the course** in the catalog and pulls its lecture list.
2. **Fetches a transcript for every lecture** from YouTube's captions, and
   groups it into timestamped paragraphs.
3. **Copy-edits each transcript.** This step matters more than it sounds.
   Auto-captions mangle exactly the vocabulary a course is about — in the
   CS224N build, *word2vec* arrived as "word Tove", "word DEC" and "watch ve",
   and *PyTorch* as "py talk". A transcript in which the term never appears
   cannot answer a question about it. The verbatim captions are kept alongside
   the edited version, so the edit can be checked.
4. **Reads the slide decks.** Each deck is transcribed slide by slide — text,
   equations as written, tables, and figures described in prose, since prose is
   the only representation of an image the knowledge base will have. Slide
   numbering is derived from the deck rather than assumed, because hidden slides
   make printed numbers drift from page numbers.
5. **Crawls the course website** for handouts and problem sets, recording each
   with its canonical URL. PDFs are normally linked rather than committed: the
   reader is an agent that navigates markdown, and a course's decks routinely
   run to well over 100 MB.
6. **Writes the wiki** — a page per lecture, plus topic pages for concepts that
   span lectures — with mathematics reconstructed into rendered LaTeX rather
   than left as the captions' spoken form.
7. **Publishes** the public repo and sets the knowledge base URL on the catalog
   entry.

## What it costs, and how long it takes

It is a long, expensive job. The measured figure from the CS224N build — 23
lectures, fourteen sessions over about a month — was roughly **$33 per lecture**
in model usage, most of it in reading slide decks and writing prose. Budget
accordingly before starting a 25-lecture course.

The build is **resumable**. A `TODO.md` in the repository is the state: each run
reads it and does only the unchecked work, so an interrupted build picks up
where it stopped rather than starting over.

## Updating one

When a playlist gains lectures, or the course site publishes new slides, the
same skill appends entries for the new work and runs the loop again. The index
needs updating too — a stale index is the most common way a knowledge base
rots, because the assistant reads the index, trusts it, and never finds the new
pages.

## Doing it by hand

Nothing requires the skill. A knowledge base is markdown in a Git repository; if
you want to write one yourself, follow
[the layout contract](kb-repo-layout.md), keep `INDEX.md` accurate, and attach
it as described in
[attaching a knowledge base](attach-a-knowledge-base.md).

## Related pages

- [Knowledge bases](knowledge-bases.md)
- [Knowledge base repo layout](kb-repo-layout.md)
- [Annotating lectures](annotating-lectures.md) — the other Cairn agent skill
