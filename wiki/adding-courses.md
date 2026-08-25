# Adding courses

A course in Cairn is a YouTube playlist plus a bit of metadata — code, title,
instructor, and an ordered list of lectures. There are two ways to get one into
your library: paste a playlist URL, or enrol in something already in the
[shared catalog](catalog.md).

## By playlist URL

In **Courses**, open **Add Course** and paste the playlist link, in the form
`https://www.youtube.com/playlist?list=PL...`, then **Import Playlist**.

Cairn fetches the playlist's public metadata — its title, the video count, and
each lecture's title and duration — and builds the lecture list from it. That
fetch happens on Cairn's servers rather than in your browser, so it works even
before you sign in.

Two outcomes are possible:

- **The playlist is already in the catalog.** You are enrolled in the existing
  entry immediately, and you inherit whatever the community has curated on it —
  the corrected title, the course website link, ratings, traces, and a
  [knowledge base](knowledge-bases.md) if one is attached.
- **It is new.** A catalog entry is created from the playlist, attributed to
  your nickname, and you are enrolled in it. Creating a catalog entry requires
  being signed in.

When a playlist matches an entry that already exists, Cairn offers **Create my
own** as well. Use it when the existing entry is genuinely a different course —
a different year's recording of the same class, say — rather than one you want
to share.

**Private and unlisted playlists.** A playlist Cairn's server cannot see is a
playlist it cannot import; the metadata fetch reads public data only. Version
1.1.0 fixed the handling here so the failure is reported cleanly rather than
producing a broken course.

## From the catalog

The **Catalog** tab lists every course anyone has added, searchable, with
aggregate ratings and a knowledge-base link where one exists. Enrolling is one
click and needs no account. This is usually the better path for a well-known
course, because someone has probably already tidied the entry.

## Editing a course

Open a course from **Courses** and edit it to set:

- **Course URL** — the class's own website, where slides, notes and problem sets
  live. It shows as a link on the course page, and it is where a
  [knowledge base build](building-a-knowledge-base.md) goes looking for
  materials.
- **Knowledge base URL** — a public GitHub repo holding the course's compiled
  wiki. Setting this is what switches on the chat's ability to read the course.
  See [attaching a knowledge base](attach-a-knowledge-base.md).
- **Description** — what the course is about, shown on the course page. Long
  descriptions collapse behind a "show more".

The catalog entry is shared, so an edit changes what everyone sees. Personal
things are not stored there: your progress, your notes and your enrolment are
yours alone.

## What a course looks like once added

The course page lists every lecture in playlist order, each with its number,
title, duration, a progress bar, and a resume control that deep-links to YouTube
at the second you stopped. The header carries the course's aggregate usefulness
and difficulty [ratings](ratings.md), a link to the playlist, a link to the
course website if one is set, and a knowledge-base link if one is attached.

## Refreshing a course

When a playlist gains lectures — a class still being posted week by week — the
course entry can be refreshed to pick them up. Progress on existing lectures is
untouched. If the course has a knowledge base, that is built separately and
needs its own update run; see [building a knowledge base](building-a-knowledge-base.md).

## Related pages

- [The catalog](catalog.md) — who can add and edit what
- [Progress tracking](progress-tracking.md) — what happens once a lecture plays
- [Troubleshooting](troubleshooting.md) — import failures
