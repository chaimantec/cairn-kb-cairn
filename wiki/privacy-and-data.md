# Privacy and your data

This page summarizes where your data goes, in the terms a user cares about. The
authoritative document is the published policy at
[cairnstudy.com/privacy.html](https://cairnstudy.com/privacy.html), kept
verbatim in this repository at
[`raw/privacy-policy.md`](../raw/privacy-policy.md). Where the two differ, the
published policy wins.

Cairn's own summary: *"Cairn collects the minimum needed to make the extension
work. There is no advertising, no analytics, and no third-party tracking."*

## The short version

| Your data | Where it lives |
|---|---|
| Courses, progress, notes — **as a guest** | Your browser only |
| Courses, progress, notes, ratings, nickname — **signed in** | Your browser, and Cairn's servers, synced |
| Chat conversations | **Your browser only**, always |
| What the assistant remembers about you | **Your browser only**, always |
| Your AI provider API key | **Cairn's servers only**, encrypted — never on your device |

That last row inverts what you might expect, and it is deliberate: keeping the
key server-side is what stops it from ever sitting in your browser's storage.

## What Cairn knows about you

If you never sign in: nothing that identifies you. No account, no cookies, no
fingerprinting, no tracking IDs.

If you sign in with Google, Cairn requests the **`openid` scope only**. It
receives an opaque identifier for your Google account and nothing else — not
your email address, not your name, not your picture, and no access to your
YouTube account, watch history, subscriptions or comments. Cairn stores that
identifier, an internal account ID, an auto-generated
[nickname](accounts-and-sync.md), and sign-in timestamps.

Cairn cannot email you, because it does not know your email address.

## What it does not collect

No telemetry, no analytics, no usage metrics, no crash reports. No Google
Analytics, Mixpanel, Segment or anything comparable. No advertising networks or
marketing pixels.

It does not collect your YouTube watch history: it only knows about videos in
courses you have added. Your activity on YouTube outside those, and on every
site other than YouTube, is never read — the extension reads YouTube pages and
no others.

## What becomes public, and only when you choose

- **Public traces**, attributed to your nickname. You can switch one back to
  private at any time, which removes it from public view.
- **Catalog contributions**, attributed to your nickname.
- **Ratings**, which move a public average. Your individual rating is not shown
  next to your name.
- **Likes**, which raise a count. Your individual like is not publicly
  attributed.

## The AI chat, specifically

The chat is off until you enable it, and it requires an account.

**Your conversations stay in your browser.** They are not stored on Cairn's
servers, do not sync, are not tied to your account, and are not recoverable if
you clear the extension's data. Cairn does not read them, store them, or train
on them.

**Your messages do pass through Cairn's servers** on the way to the model
provider — that is what allows your API key to stay off your device entirely.
Nothing is retained: a message exists in server memory only for as long as the
answer takes, and is never written to a database, to disk, or to logs.

**What reaches the AI provider** with each message: what you type, the earlier
messages of that conversation, your saved [memories](chat-memory.md), and the
current course title, lecture title and your position in the video. If you have
enabled web search, your queries and the addresses of pages the assistant opens
go to Tavily. If the course has a [knowledge base](knowledge-bases.md), its
public files are fetched from GitHub.

Those providers handle that data under their own privacy policies. The relevant
ones are Google (Gemini), DeepSeek, OpenRouter — which forwards to whichever
underlying model you select — Tavily, and GitHub.

**One thing worth knowing before you pick a free Gemini key:** Google's terms
for the free tier of the Gemini API allow it to use your prompts and responses
to improve its products. The paid tier does not. That is Google's policy rather
than Cairn's, and it applies to whichever key you save — so if your questions
are sensitive, that is a reason to use a paid key or another provider.

**Your API key** is encrypted at rest on Cairn's servers and never sent back to
your browser. The policy is candid about the limits: this defends against a
database-only leak, not a full server compromise, and the key must exist
decrypted in memory for the duration of a request.

## Where it is hosted

Cairn's servers are in the **Asia Pacific region**. Using Cairn means consenting
to your data being processed there, wherever you are.

## Deleting things

| To delete | Do this |
|---|---|
| Your account and everything synced | **Settings → Delete account** |
| Chats and assistant memories | Clear the extension's data, or uninstall |
| One memory | Ask the assistant to forget it |
| An AI provider key | **Settings → AI chat → Remove** |
| A public trace, from public view | Switch it back to Personal |

Deletion is immediate and irreversible. Catalog entries you created survive
account deletion, reassigned to an anonymous proxy with no link to you, because
other people are enrolled in them.

## Honesty about the threat model

The policy says it plainly, and it is worth repeating: *"This is a small
project, not a security-hardened enterprise product… Do not rely on Cairn to
protect highly sensitive information — your study notes are not the same threat
model as your bank."*

## Rights and contact

EU, UK and California users wanting access, correction, deletion or portability
should email **hello@cairnstudy.com**; the policy commits to a response within
30 days. Cairn is not directed at children under 13.

## Related pages

- [Accounts and sync](accounts-and-sync.md)
- [Bring your own key](bring-your-own-key.md)
- [Chat memory](chat-memory.md)
