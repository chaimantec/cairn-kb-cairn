# The Live tab

**Live** is the tab you keep open while a lecture is playing. It is the only
part of Cairn that is tied to *this second* of *this video*, and it holds two
things behind a switcher:

- **Notes** — the traces on this lecture, and the box for writing your own.
- **Chat** — the [AI study chat](study-chat.md), scoped to this lecture.

When nothing tracked is playing, the tab says so: *"Start watching a tracked
lecture on YouTube — comments and your notes will appear here in real time."*
It needs a lecture from a course you have added; a video Cairn does not
recognise leaves it empty. See [adding courses](adding-courses.md).

## The Notes side

The note list is filtered three ways — **All**, **Mine**, **Public** — so you
can read only what other people left, or only your own.

Above it sits a **timeline bar**: the whole lecture as a strip, with the density
of notes shown across roughly forty buckets, and your current position marked.
It shows at a glance where in a lecture people stopped to write something, which
is a decent proxy for where a lecture is hard. Clicking a point on the bar seeks
the video there.

Below is the composer: a text box, a timestamp field, and a visibility toggle.
See [traces and notes](traces-and-notes.md) for how notes are written, pinned to
a moment, and made public.

## Notes appearing as the lecture runs

Notes surface around their moment rather than all at once. A note becomes
"nearby" **10 seconds before** its timestamp and stops being nearby **80 seconds
after** it — the window Cairn settled on after an earlier and longer one. The effect is that a note reaches you slightly before the moment it
was written about, and stays visible long enough to read while the lecturer is
still on the topic.

The same window governs the popup that floats a note over the Chat side, so a
trace surfaces and retires at the same moments whichever side you are looking at.

## The Chat side

The Chat sub-tab is the study chat. It knows the course, the lecture, and your
playback position, which is what lets you ask "what did he just say?" and get an
answer about the right moment.

It is locked for guests, and stays locked for signed-in users until an API key
is saved — see [bring your own key](bring-your-own-key.md). Everything about
using it is in [the study chat](study-chat.md).

Cairn remembers which of the two sides you had open and returns you to it.

## Related pages

- [Traces and notes](traces-and-notes.md)
- [The study chat](study-chat.md)
- [Progress tracking](progress-tracking.md) — where the live position comes from
