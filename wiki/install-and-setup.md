# Install and setup

## Installing

Cairn is distributed through the Chrome Web Store:
[chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim](https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim).
Add it to Chrome, then pin it to the toolbar so the icon is reachable — Chrome
hides new extensions behind the puzzle-piece menu by default.

It is a Chrome extension and runs in Chrome and Chromium-based browsers that
support Manifest V3 side panels. There is no Firefox or Safari build, and no
mobile version.

## Opening the sidebar

Click the Cairn icon in the toolbar. The sidebar opens in Chrome's side panel,
to the right of the page, and stays open as you navigate. The same click closes
it again.

If you would rather use the keyboard, Chrome owns that binding rather than
Cairn: go to **Settings → Keyboard shortcut** in the sidebar and follow the
link to `chrome://extensions/shortcuts`, where you can assign any combination
you like to toggling the sidebar. Cairn ships no default binding, so nothing is
assigned until you set one.

## The five tabs

Across the top of the sidebar:

| Tab | What it holds |
|---|---|
| **Courses** | Your library — the courses you have added, with progress. Opening one shows its lecture list. See [adding courses](adding-courses.md). |
| **Live** | What is playing right now: notes and traces at this moment, and the study chat. See [the Live tab](live-tab.md). |
| **Stats** | Streak, watch time, and a twelve-week activity heatmap. See [the stats dashboard](stats-dashboard.md). |
| **Catalog** | The shared, community-built course catalog. See [the catalog](catalog.md). |
| **Settings** | Account, nickname, AI provider keys, theme, account deletion. |

## First run, in order

1. **Open a lecture playlist on YouTube** — or find the course in the
   [Catalog](catalog.md) tab, where someone may already have added it.
2. **Add the course.** In **Courses**, use **Add Course** and paste the playlist
   URL. Cairn fetches the playlist's public metadata and builds the lecture
   list. See [adding courses](adding-courses.md).
3. **Play a lecture.** Progress starts recording within about ten seconds. There
   is nothing to press.
4. **Optionally sign in.** Everything above works as a guest, stored only in
   your browser. Signing in adds cross-device sync and lets you post public
   traces, rate lectures, and use the chat. See [accounts and sync](accounts-and-sync.md).
5. **Optionally turn on the chat.** It stays locked until you save your own
   DeepSeek or OpenRouter API key in **Settings**. See
   [bring your own key](bring-your-own-key.md).

## Appearance

**Settings → Appearance** carries a single light/dark toggle. It applies to the
sidebar only and is remembered on that device.

## What Cairn asks Chrome for, and why

The permissions on the store listing are worth knowing, because they are the
question most people have before installing:

| Permission | Why |
|---|---|
| Read and change data on `youtube.com` | The content script reads the player's current time and duration, and detects when you navigate to another video. This is how automatic tracking works. |
| `accounts.google.com` | The sign-in flow only. Cairn requests the `openid` scope and nothing else — no access to your YouTube account, history, or subscriptions. |
| Storage, unlimited storage | Your courses, progress, notes, chats and settings live in the browser. |
| Tabs | To find the YouTube tab that is actually playing your lecture — used for the live position and for [attaching a snapshot](images-in-chat.md) of the frame you are looking at. |
| Side panel, identity | The sidebar itself, and Google sign-in. |

Cairn reads YouTube pages and no others. See [privacy and your data](privacy-and-data.md).

## Related pages

- [Adding courses](adding-courses.md)
- [Progress tracking](progress-tracking.md)
- [Troubleshooting](troubleshooting.md) — if the sidebar is blank or progress is not moving
