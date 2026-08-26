# Cairn — knowledge base

This is the knowledge base for **Cairn itself**: the Chrome extension that helps
people finish university lecture courses on YouTube. Everything here describes
the shipped product — what it does, how to use it, what it costs, and what
happens to a user's data.

Cairn tracks watch progress automatically against courses you add from YouTube
playlists, shows short timestamped notes — *traces* — that other learners left
at the moments they left them, and syncs across devices when you sign in. Since
1.3.0 it also has an optional AI study chat that knows which lecture is playing
and where you are paused in it, and can read a course's compiled knowledge base
before answering. It is made by **chaimantec** — a free, independent side
project, not affiliated with YouTube, Stanford, or MIT — and it takes its shape
from *Death Stranding*: what you get from other learners is what they left
behind at a hard moment, not a conversation with them.

- Store listing: [Cairn — YouTube Course Tracker](https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim)
- Site: [cairnstudy.com](https://cairnstudy.com/) · Contact: hello@cairnstudy.com

**Scope.** This knowledge base covers Cairn as a user meets it. It does not
document how Cairn is built — there are no pages on server architecture, API
endpoints, or the database — and it does not describe unshipped features. See
[`AGENTS.md`](AGENTS.md).

## Start here

- [What Cairn is](wiki/what-is-cairn.md) — what it does, who makes it, where the
  name and the design come from, who it is for, and the things it deliberately
  is not.
- [FAQ](wiki/faq.md) — the short answer to most questions, with links onward.
- [Glossary](wiki/glossary.md) — trace, catalog, knowledge base, BYOK, nearby
  window, thinking level.

## Using the extension

- [Install and setup](wiki/install-and-setup.md) — installing, opening the
  sidebar, the five tabs, the keyboard shortcut, and what each Chrome permission
  is for.
- [Adding courses](wiki/adding-courses.md) — importing a playlist, enrolling
  from the catalog, editing a course, and what happens with private playlists.
- [Progress tracking](wiki/progress-tracking.md) — how automatic tracking works,
  the 90% completion rule, resuming, ads, and why a video might not be tracked.
- [Accounts and sync](wiki/accounts-and-sync.md) — guest versus signed in, what
  Google sign-in gives Cairn, nicknames, 30-day sessions, and deleting an account.
- [The catalog](wiki/catalog.md) — the shared course list, who can add and edit
  what, and how contributions are attributed.
- [The Live tab](wiki/live-tab.md) — the tab tied to what is playing now: the
  note list, the timeline bar, and the chat.
- [Traces and notes](wiki/traces-and-notes.md) — writing a note, pinning it to a
  moment, private versus public, likes, reporting, and what makes a good trace.
- [Ratings](wiki/ratings.md) — the usefulness and difficulty axes, and what the
  aggregates are good for.
- [The stats dashboard](wiki/stats-dashboard.md) — streak, watch time, weekly
  comparison, and the twelve-week heatmap.

## The AI study chat

- [The study chat](wiki/study-chat.md) — what it is, how to turn it on, what it
  knows without being told, and how it writes.
- [Bring your own key](wiki/bring-your-own-key.md) — Gemini for a free start,
  DeepSeek for a cheap one, OpenRouter for the run of the catalog, Tavily for
  web search; where a key is stored, what drives the bill, why rate limits
  arrive sooner than expected, and every provider error explained.
- [Models and thinking levels](wiki/models-and-thinking.md) — the model picker,
  defaults, which model to pick and what it costs (a dated recommendation, not a
  standing one), arbitrary OpenRouter model ids, and when more thinking is worth
  paying for.
- [What the chat can look up](wiki/chat-tools.md) — the knowledge-base, web and
  memory tools, what the transcript chips mean, and how citations work.
- [Chat memory](wiki/chat-memory.md) — standing instructions about how you like
  to be answered, the 50-entry cap, conflicts, and forgetting.
- [Images in chat](wiki/images-in-chat.md) — snapshotting the lecture frame,
  attaching your own images, formats and caps.
- [Managing chats](wiki/managing-chats.md) — multiple chats, renaming, pinning,
  the two different searches, bulk cleanup, and why chats do not sync.
- [Asking good questions](wiki/asking-good-questions.md) — the question patterns
  that actually exploit lecture context and the knowledge base, and what the
  assistant is weak at.

## Knowledge bases

- [Knowledge bases](wiki/knowledge-bases.md) — what one is, what it changes
  about the chat's answers, and why you can read one without Cairn.
- [Attaching a knowledge base](wiki/attach-a-knowledge-base.md) — the two-minute
  version: paste a repo URL into a course you created.
- [Building a knowledge base](wiki/building-a-knowledge-base.md) — what a build
  involves, what it costs, and how it is resumed and updated.
- [Knowledge base repo layout](wiki/kb-repo-layout.md) — the file-by-file
  contract, and the conventions inside the wiki.
- [Annotating lectures](wiki/annotating-lectures.md) — the `cairn-annotate`
  skill, which drafts timed markers and posts them as personal notes.

## Reference

- [Privacy and your data](wiki/privacy-and-data.md) — where each kind of data
  lives, what becomes public, what reaches an AI provider, and how to delete
  things.
- [Limits and caps](wiki/limits-and-caps.md) — every enforced number in one
  table, and how Cairn's own limits differ from your provider's.
- [Troubleshooting](wiki/troubleshooting.md) — progress not tracking, imports
  failing, the chat locked or erroring, missing chats, sync lag.

## Sources

- [`sources.md`](sources.md) — every source this was compiled from, with dates.
- [`raw/privacy-policy.md`](raw/privacy-policy.md) — the published privacy
  policy, verbatim.
- [`raw/landing-copy.md`](raw/landing-copy.md) — cairnstudy.com's own words,
  section by section.
- [`raw/changelog.md`](raw/changelog.md) — release notes through 1.3.0.
