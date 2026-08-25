# Traces and notes

A **trace** is a short note pinned to a second in a lecture. It is Cairn's
central idea, and the thing that makes it different from a note-taking app:

*"A trace is a short, timestamped note pinned to a moment in a lecture. You see
traces only at the seconds they were posted, and only when they are useful — at
the kinds of moments where someone reached out a hand. There are no follower
counts, no DMs, no replies threading off into the woods."*

In the interface they are simply called notes, and they are private until you
decide otherwise.

## Writing one

In the [Live tab](live-tab.md), with a tracked lecture playing, type into **Add
a note…** and post it. Two controls sit next to the box:

- **Timestamp.** The note is pinned to your current position by default. The
  timestamp field is editable while the video is paused, so you can correct it
  to the moment you actually mean rather than the moment you finished typing.
- **Visibility.** A padlock means private; a globe means public. Click to
  switch. New notes start private.

Notes support ordinary text and are stored per lecture. You can edit or delete
your own at any time, and flip a note between private and public whenever you
like — including making a public note private again, which removes it from
everyone else's view.

## Private notes versus public traces

**Private** notes are yours. As a guest they never leave your browser. Signed
in, they sync across your devices and remain visible only to you.

**Public** notes are traces: they appear to anyone watching that lecture, at
that moment, attributed to your [nickname](accounts-and-sync.md). Posting one
requires an account.

The asymmetry is deliberate. Most notes are for yourself; publishing is the
exception, for the moment where you worked out something confusing and the next
person will hit the same wall.

## Reading other people's

Traces arrive as their moments arrive — appearing about ten seconds early,
retiring about eighty seconds later. The timeline bar above the list shows where
in the lecture notes cluster, which is a rough map of the hard parts. Filter to
**Public** to read only what others left.

You can **like** a public trace, which raises its like count. Likes need an
account so each counts once, and your individual like is not shown to anyone
else.

There is no way to reply. That is the design, not an omission — *"It is not a
conversation — it is a marker on a trail. You can leave one of your own and keep
walking."*

## Reporting

Public traces carry a report control, under the note's menu. The reasons offered
are **spam or advertising**, **harassment or bullying**, **misinformation**, and
**other**, with a box for describing the problem. Reporting requires an account.

## Writing a good trace

Traces are read by someone mid-lecture, at the moment you left them. That
suggests:

- **Short.** One or two sentences that can be read while the lecturer keeps
  talking.
- **Anchored to the right second.** Pin it to where the confusion starts, not to
  where you finished understanding it.
- **Useful at that moment.** "The jump from line 2 to line 3 is just the chain
  rule" earns its place. "Good lecture" does not.
- **Self-contained.** Nobody can ask you what you meant.

## Generating traces with an agent

The `cairn-annotate` skill drafts timed markers across a whole lecture and posts
them back as your *personal* notes, prefixed with a flag emoji so they are easy
to find and replace. It is a way to pre-mark a lecture before watching it. See
[annotating lectures](annotating-lectures.md).

## Related pages

- [The Live tab](live-tab.md)
- [Accounts and sync](accounts-and-sync.md)
- [Privacy and your data](privacy-and-data.md)
