# How this knowledge base is organized

This repo is the knowledge base for **Cairn itself** — the Chrome extension —
rather than for a course taught in it. It exists so that Cairn's own study
assistant, and any other agent pointed at it, can answer questions about what
Cairn is, how to use it, and what it does with a user's data, from documentation
rather than from guesswork.

It follows the same layout contract as a course knowledge base, so the same
reading tools navigate it: `INDEX.md` at the root, relative markdown links
between pages.

## Layout

| Path | Contents |
|---|---|
| `INDEX.md` | Entry point. What Cairn is, plus an annotated table of contents. |
| `wiki/` | Every durable page, grouped as product, chat, knowledge bases, reference. |
| `raw/` | Verbatim copies of Cairn's public documents — the source material. |
| `sources.md` | Where each source came from, and when. |
| `kb.json` | Machine-readable self-description: coverage, method, caveats. |
| `TODO.md` | Build tracker. Unchecked boxes are outstanding work. |

There is no `raw/transcripts/`, `raw/slides/` or `raw/pdfs/` here: this KB has
no lectures behind it.

## Scope — read this before adding anything

This knowledge base documents Cairn **as a user meets it**. That boundary was
set deliberately when it was built, and it is the main thing a future
maintainer needs to respect.

**In scope:** what the extension does, how to use every feature, what things
cost, what the limits are, what happens to a user's data, how knowledge bases
work and how to build or attach one, and how to get unstuck.

**Out of scope:** how Cairn is built. No server architecture, no API endpoint
reference, no database schema, no source-code layout, no description of features
that have not shipped. Cairn's source is not public and nothing here is quoted
from it.

Where a user question genuinely turns on where data goes — which key is stored
where, what reaches a model provider — the answer comes from the published
privacy policy and is cited to it, at the level of detail the policy itself
uses. That is user-facing fact, not architecture.

## Conventions

- **`INDEX.md` is the front door.** It is read first in every conversation.
  Every page must appear there with a one-line description of what it holds. An
  unindexed page is effectively invisible.
- **Relative links only** — from a page in `wiki/`, a sibling is written bare
  and `raw/` is reached with `../`. Absolute GitHub URLs break when the
  repo is renamed or forked. Absolute links to the outside web — the store
  listing, cairnstudy.com — are fine and expected.
- **Describe what ships.** Every claim should be checkable against the shipped
  extension, the store listing, the landing page, or the privacy policy. Do not
  document intentions, roadmap items, or behaviour that only exists in a branch.
- **Do not track versions.** Chrome auto-updates the extension, so a reader is
  always on the current build and cannot choose otherwise; "which version added
  what" is a fact they can do nothing with. Write current behaviour in the
  present tense and leave version numbers out, rather than pinning claims to a
  release that will be superseded before anyone reads them.
- **Quote Cairn's own words where they are better than a paraphrase**, in
  italics, and keep them accurate. The landing page copy is in
  [`raw/landing-copy.md`](raw/landing-copy.md).
- **Prose in full sentences.** The assistant quotes these pages to users, and
  fragments quote badly. Tables are for enumerable facts — limits, permissions,
  which tool needs what.
- **Do not invent numbers.** Every limit in
  [`wiki/limits-and-caps.md`](wiki/limits-and-caps.md) is one the product
  actually enforces. If a value is unknown, leave it out rather than guessing.

## Keeping it current

The extension changes; this repo does not change with it automatically. When a
release ships:

1. Update [`raw/changelog.md`](raw/changelog.md) with the new version's notes.
2. Fix the pages the release affects — a changed limit, a new setting, a renamed
   tab.
3. Update `INDEX.md` if pages were added or removed. A stale index is the most
   common way a knowledge base rots: the assistant reads it, trusts it, and never
   finds the new page.
4. Update `kb.json` — at minimum `coverage.appVersion` and `updated`.
5. Re-copy [`raw/privacy-policy.md`](raw/privacy-policy.md) if the published
   policy's "Last updated" date has moved, and re-check
   [`wiki/privacy-and-data.md`](wiki/privacy-and-data.md) against it.
