# Limits and caps

Every number Cairn enforces that you might actually bump into, in one place.

## Progress tracking

| | |
|---|---|
| Completion threshold | **90%** of a lecture's duration |
| Progress poll | every **10 seconds** while playing |
| Live position update | every **2 seconds** while playing |
| Progress push to the server, signed in | batched, roughly every **30 seconds** |

Ad playback is excluded from all of the above. See
[progress tracking](progress-tracking.md).

## Notes and traces

| | |
|---|---|
| A note becomes "nearby" | **10 seconds before** its timestamp |
| …and stops being nearby | **80 seconds after** it |
| Timeline bar resolution | the lecture divided into about **40** buckets |

See [traces and notes](traces-and-notes.md).

## Accounts

| | |
|---|---|
| Session lifetime | **30 days**, then a re-sign-in banner |
| Ratings | one per lecture and one per course, replaceable |

## The study chat

| | |
|---|---|
| Messages in one conversation | **200** |
| Text across one request | **400,000 characters** |
| Images per message | **4** |
| Images across one conversation | **24** |
| Image formats | JPEG, PNG, WebP, GIF — not SVG |
| Images downscaled to | ~**1568 px** longest edge, ~**300 KB** |
| Saved memories | **50** |
| Length of one memory | **400 characters** |

In practice the selected model's own context window is reached before Cairn's
message cap, producing *"This conversation is too long for the selected model.
Start a new chat."* Either way the fix is a new chat, which is cheaper anyway.

Cairn also rate-limits chat requests per account — hitting it gives *"Too many
requests. Slow down a moment."*

Separately, your **provider** enforces its own rate limits and credit balance,
which surface as their own messages — and those are the ones you are far more
likely to meet. Cairn cannot raise them and does not know what they are. The
number that matters is not questions per minute but **requests** per minute: one
question can take five or six calls, because reading a knowledge-base file,
searching the web and writing the answer are separate requests. See
[rate limits](bring-your-own-key.md#rate-limits).

## Knowledge bases

| | |
|---|---|
| Repository visibility | must be **public** |
| One file read | up to **50,000 characters**, paged at **500 lines** at a time |
| Very large files | refused with a note to read something more specific |
| Binary files | never read as text — the link is returned instead |

See [knowledge base repo layout](kb-repo-layout.md).

## Where there is no limit

There is no cap on how many courses you can add, how many lectures you can
track, how many notes you can write, or how many chats you can keep. Extension
storage is unlimited, so the practical ceiling is your disk.

## Related pages

- [Managing chats](managing-chats.md)
- [Troubleshooting](troubleshooting.md)
