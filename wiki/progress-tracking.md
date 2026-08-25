# Progress tracking

Cairn's central claim is that you never mark anything complete. The extension
watches the YouTube player directly and records what you actually watched.

## How it works

A small script runs on YouTube pages. When the video playing matches a lecture
in one of your courses, it reads the player's current time and duration and
writes your position down. It polls roughly **every ten seconds**, and updates
the sidebar's live position about **every two seconds** while the video is
actually playing, which is what lets the [Live tab](live-tab.md) show traces
arriving in time with the lecture.

Three details make it behave the way you would want:

- **Ads do not count.** While YouTube is showing an ad, tracking pauses. Ad time
  is not added to your watch time and does not advance your position.
- **It follows YouTube's navigation.** YouTube changes videos without reloading
  the page. Cairn listens for that and re-detects the lecture, so clicking
  through a playlist keeps tracking without a refresh.
- **It only watches your courses.** A video that is not a lecture in a course you
  have added is ignored entirely. Cairn does not build a record of your YouTube
  viewing at large.

## When a lecture counts as complete

A lecture is marked complete once you have reached **90%** of its duration. The
last tenth is credits, questions, and the lecturer packing up, so requiring
100% would leave a course permanently at 19 of 20.

You can also toggle a lecture complete or incomplete yourself, at any time,
regardless of what the tracker thinks. That is useful for a lecture you watched
elsewhere, or one you have decided to skip.

## Resuming

Every lecture stores the position you left it at, to the second. The resume
control on the lecture row opens YouTube at that timestamp. Signed in, the
position is the furthest you have reached on **any** device — so a lecture
half-watched on a laptop resumes correctly on a desktop.

## Course-level progress

The course page shows a progress bar and a completion percentage over the whole
lecture list, and the library card repeats it. Watch time feeds the
[stats dashboard](stats-dashboard.md) — the streak, the weekly totals and the
twelve-week heatmap all come from the same records.

## Guest versus signed in

As a guest, progress is written to your browser's extension storage and stays
there. It is real and complete, but it is local to that browser: clear the
extension's data or move to another machine and it is gone.

Signed in, progress is also pushed to Cairn's servers — batched, roughly every
thirty seconds — and merged across your devices. The merge keeps the furthest
position rather than the most recent write, so watching on two machines never
rewinds you. See [accounts and sync](accounts-and-sync.md).

## When tracking does not happen

- The video is not part of a course you have added. Add the course first.
- The playlist was imported but this particular video is not in it — a lecture
  posted later, or a video the playlist omits.
- The tab was opened before the extension was installed or updated. Reload it.
- An ad is playing.

See [troubleshooting](troubleshooting.md) if progress is not moving when it
should be.
