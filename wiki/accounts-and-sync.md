# Accounts, sign-in and sync

Cairn works without an account. Signing in adds cross-device sync and unlocks
the parts that involve other people or a server-side key.

## What works as a guest

Adding courses, automatic [progress tracking](progress-tracking.md), personal
notes, the [stats dashboard](stats-dashboard.md), browsing and enrolling from the
[catalog](catalog.md), and reading public traces others have left. All of it is
stored in your browser.

## What needs an account

| Feature | Why |
|---|---|
| Sync across devices | There has to be somewhere to sync to. |
| Posting **public** traces | They are attributed to a nickname, which needs an identity. |
| Liking a public trace | So a like counts once. |
| Rating lectures and courses | Same reason. |
| Creating or editing a catalog entry | Contributions are attributed. |
| Reporting a trace | Moderation needs an account behind the report. |
| The [AI study chat](study-chat.md) | Your provider key is stored against your account. |

## Signing in

Sign-in is Google, from **Settings → Account**. Cairn requests the `openid`
scope and nothing more. In practice that means Cairn receives an opaque
identifier for your Google account and nothing else — no email address, no name,
no profile picture, and no access to your YouTube account, watch history,
subscriptions or comments.

Because Cairn does not learn your email address, it cannot send you email. It
also cannot recover an account for you.

## Nicknames

New accounts are given an automatically generated nickname from an
adjective-and-noun list — the site's example is *"Forest Walker"*. That nickname
is the only thing other people see next to your public traces and catalog
contributions. You can change it in **Settings → Account**.

There are no real names and no avatars anywhere in Cairn, by design.

## What syncs

Signed in, these are stored on Cairn's servers and follow you to any browser you
sign in on:

- Your enrolled courses
- Watch progress on their lectures
- Your notes, both personal and public
- Your lecture and course ratings
- Your nickname

Progress merges rather than overwrites: the furthest position wins, and a
lecture that has been completed stays completed. Notes queue locally and flush
when the connection allows, so writing a note offline is safe.

**Chats do not sync.** Your [study chat](study-chat.md) conversations and
anything the assistant has been asked to [remember](chat-memory.md) live only in
the browser you had them in. That is deliberate — see
[privacy and your data](privacy-and-data.md).

## Sessions expire

A signed-in session lasts **30 days**. When it lapses, a banner appears at the
top of the sidebar offering to sign in again, and Cairn keeps working locally in
the meantime rather than failing. Version 1.2.0 exists largely to make that
expiry graceful.

## Signing out, and signing in as someone else

Signing out leaves your local data in place. Your chats survive it, because they
are not considered account data. If you then sign in with a *different* account
while chats exist, Cairn asks whether to keep them or clear them — it does not
decide for you.

## Deleting your account

**Settings → Danger zone → Delete account**, which asks you to type a
confirmation phrase first. Deleting removes your account record, your synced
progress and enrolments, your personal and public notes, your ratings, your
likes, and your saved AI provider keys.

Two things behave differently and are worth knowing before you press it:

- **Catalog entries you created stay in the catalog**, reassigned to an
  anonymous proxy account with no link to you. Other people are enrolled in
  them, so deleting them would break their libraries.
- **Local data is not touched by account deletion.** Chats, and anything stored
  only in the browser, are removed by uninstalling the extension or clearing its
  data in Chrome.

Deletion is immediate and irreversible.

## Related pages

- [Privacy and your data](privacy-and-data.md)
- [Traces and notes](traces-and-notes.md)
- [Troubleshooting](troubleshooting.md)
