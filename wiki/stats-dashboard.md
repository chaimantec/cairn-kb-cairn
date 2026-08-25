# The stats dashboard

The **Stats** tab is a small motivation panel built entirely from watch data
Cairn already has. Nothing on it needs an account, though signing in is what
makes it consistent across devices.

## What it shows

**In progress.** The courses you are partway through, so the tab doubles as a
"what was I doing?" view.

**Day streak.** Consecutive days on which you watched at least something. A
flame appears once the streak is above zero. Streaks are the one piece of
pressure Cairn applies, and it is applied to you rather than displayed to anyone
else — there is no leaderboard.

**Total watched.** Cumulative watch time across every course.

**This week versus last week.** Two bars. It is the most honest number on the
page, because it shows a slowdown immediately.

**Activity — last 12 weeks.** A GitHub-style heatmap, one cell per day, shaded
from *Less* to *More* by how much you watched. Twelve weeks is long enough to
show a pattern and short enough that a bad fortnight does not disappear into the
noise.

Before you have watched anything the tab says so: *"No data yet — start watching
a lecture to see stats."*

## Where the numbers come from

All of it derives from the same records that drive
[progress tracking](progress-tracking.md) — the ten-second polls the content
script writes while a lecture plays. Ad time is excluded. Time spent on videos
outside your courses is not counted, because Cairn never records it.

As a guest the figures are local to that browser. Signed in, daily activity
syncs, so a streak survives moving between machines. Version 1.1.0 fixed daily
activity not syncing after sign-in, so a streak built as a guest is carried
forward rather than lost.

## Related pages

- [Progress tracking](progress-tracking.md)
- [Accounts and sync](accounts-and-sync.md)
