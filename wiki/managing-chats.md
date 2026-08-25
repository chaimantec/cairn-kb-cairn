# Managing chats

Chats are per lecture, and you can have as many as you like. The chat header
carries a history control that opens the manager.

## The basics

- **New chat** starts a fresh conversation on the current lecture. Because your
  browser sends the whole conversation with each message, starting a new chat is
  also the cheapest thing you can do — see
  [bring your own key](bring-your-own-key.md).
- **Switch** between saved chats from the list.
- **Rename** a chat to something you will recognise later.
- **Pin** the ones worth keeping. Pinning protects a chat from the bulk cleanups
  below.
- **Delete** one, with a confirmation.
- **Stop** a reply mid-stream if it is heading the wrong way.

## Finding things

Two different searches, which is worth knowing because it is easy to reach for
the wrong one:

- **Find in chat** searches *within the open conversation*, with next and
  previous matches — Enter and Shift+Enter — and Escape to close.
- **Search chats**, in the manager, searches *across your saved chats*, with an
  option to search message text rather than just titles. This is how you find
  the conversation where you worked out the thing about eigenvalues three weeks
  ago.

## Bulk cleanup

The manager offers three sweeps, each behind a confirmation:

- Delete all except pinned
- Delete chats older than 30 days
- Delete chats older than 90 days

They cannot be undone.

## Sending

**Enter** sends; **Shift+Enter** makes a new line.

## Where chats live, and what that implies

In your browser's extension storage, not on Cairn's servers, and **not tied to
your account**. Practically:

- They **do not sync**. A chat had on your laptop is not on your desktop.
- They **survive signing out**, because they are not considered account data.
- Signing in with a *different* account while chats exist prompts you to keep or
  clear them.
- They are **not recoverable** if you clear the extension's data or uninstall.
  Copy anything you want to keep.

Deleting your Cairn account does not delete your chats, for the same reason —
they were never on the server. See [privacy and your data](privacy-and-data.md).

## When a conversation gets too long

Two ceilings can end a conversation: Cairn's own cap of **200 messages**, and
the selected model's context window, which usually arrives first and produces
*"This conversation is too long for the selected model. Start a new chat."*
Either way the fix is the same, and it is cheaper anyway. See
[limits and caps](limits-and-caps.md).

## Related pages

- [The study chat](study-chat.md)
- [Limits and caps](limits-and-caps.md)
