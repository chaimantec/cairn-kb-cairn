# What Cairn is

Cairn is a Chrome extension for people working through full university lecture
series on YouTube — Stanford CS, MIT OpenCourseWare, and anything else published
as a playlist. It lives in Chrome's side panel next to the video, tracks what you
watch without being told, and shows you the notes other learners left at the
exact moments they left them.

The name is the point. A cairn is a stack of stones left on a trail by whoever
walked it before you, to mark the way at the spot where the way is unclear. The
extension is built around that idea: the useful thing is not a feed or a
discussion, it is a short note pinned to the second in a lecture where someone
got stuck and worked it out.

The site's own summary: *"Cairn is a Chrome extension for people working through
real university lecture series — Stanford CS, MIT OCW, and the rest. It tracks
your progress across devices, and surfaces traces left by other learners who came
before."*

## The three things it does

**It tracks automatically.** There is no "mark complete" button to press. While
a lecture from a course you have added is playing, Cairn reads the player's
position and records it. A lecture counts as finished when you have watched 90%
of it. See [progress tracking](progress-tracking.md).

**It surfaces traces.** A trace is a short note pinned to a timestamp. As the
lecture plays, traces left by other learners appear as their moments arrive and
retire shortly after. You can leave your own, keep it private, or make it
public. See [traces and notes](traces-and-notes.md).

**It syncs.** Sign in with Google and your courses, progress, notes and ratings
follow you to any browser you sign in on. See [accounts and sync](accounts-and-sync.md).

On top of those, version 1.3.0 added an optional [AI study chat](study-chat.md)
that knows which lecture is playing and where you are paused in it, and can read
a course's [knowledge base](knowledge-bases.md) before it answers.

## Who it is for

Self-directed learners who start real lecture courses and want to finish them.
The maker's own description is blunt about the motivation: *"It exists because
the person who made it kept abandoning Stanford CS and MIT OCW courses around
lecture four, and wanted a tracker tool that is accessible."*

It suits you if you are working through a course alone, on your own schedule,
and you want a record of where you are and some sense that other people have
been down the same path. It is less useful if you only watch the occasional
one-off video, since nearly everything in it is organized around a course.

## What Cairn deliberately is not

It is **not a social network.** There are no followers, no direct messages, no
replies, and no threads. You cannot reply to a trace. People appear under
anonymous nicknames they pick, with no real names and no avatars. As the site
puts it: *"It is not a conversation — it is a marker on a trail. You can leave
one of your own and keep walking."*

It is **not a video player or a downloader.** Playback stays on YouTube; Cairn
sits beside it and reads the player's position.

It is **not a courseware platform.** It does not host lectures, problem sets or
solutions. Where a course publishes materials, Cairn links to them, and a
[knowledge base](knowledge-bases.md) compiles from them rather than re-hosting
them.

It is **not an AI product with a subscription.** The chat is off until you add
your own provider key, and you pay that provider directly. See
[bring your own key](bring-your-own-key.md).

It is **not affiliated with YouTube, Google, Stanford, or MIT.** It is an
independent side project, and free.

## Where it lives

- Chrome Web Store: [Cairn — YouTube Course Tracker](https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim)
- Site: [cairnstudy.com](https://cairnstudy.com/)
- Contact: hello@cairnstudy.com
- Current version: **1.3.0** (see [`raw/changelog.md`](../raw/changelog.md))

## Related pages

- [Install and setup](install-and-setup.md) — getting from installed to tracking
- [Adding courses](adding-courses.md) — the playlist import and the catalog
- [Glossary](glossary.md) — trace, catalog, knowledge base, BYOK
- [FAQ](faq.md) — the short answers
