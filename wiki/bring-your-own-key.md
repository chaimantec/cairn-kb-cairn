# Bring your own key

The [study chat](study-chat.md) runs on **your** API key, from a provider you
have an account with. There is no Cairn subscription, no bundled credits, and no
markup:

*"The chat is off until you add your own API key … so you pay the model provider
directly at cost — Cairn takes no cut and resells nothing."*

(The landing page names DeepSeek and OpenRouter at the elision; it was written
before Gemini was added, and the list below is the current one.)

## The providers

| Provider | For | Required? |
|---|---|---|
| **Gemini** | Chat models, from Google | One of the three chat providers is required |
| **DeepSeek** | Chat models | One of the three chat providers is required |
| **OpenRouter** | Chat models — a gateway to models from many vendors | One of the three chat providers is required |
| **Tavily** | Web search and page reading | Optional. Without it, the chat has no web access. |

Save at least one chat key or the composer stays disabled. Tavily is purely
additive: with it, `web_search` and `web_fetch` appear; without it, they do not.

**If you have never used an AI API before, start with Gemini.** A key is free to
create at [Google AI Studio](https://aistudio.google.com/apikey) with an ordinary
Google account — no card, no billing setup — so you can have the chat working in
a couple of minutes and decide later whether it is worth paying for. The
trade-off is a tight rate limit, which you will meet sooner than you expect:
see [rate limits](#rate-limits-and-why-gemini-meets-them-first) below.

**If you want the cheapest thing that does not get in your way, use DeepSeek.** A
DeepSeek key running `deepseek-v4-flash` is the recommendation for sustained
study use **as of 2026-08-26** — dated, not permanent, since providers reprice
and replace models faster than this page is revised. It costs little, and half
that off-peak, and its limits are generous enough that you will not think about
them.

**OpenRouter is what you add when you want the choice** — one key reaching many
vendors' catalogs, plus any model id OpenRouter publishes, so you can pick on
whatever grounds matter to you that day: price, speed, whether it reads
[images](images-in-chat.md), or simply a model you would rather use. Saving more
than one and switching per question is a perfectly good setup. See
[models and thinking levels](models-and-thinking.md).

Getting a key means signing up with that provider and creating one in their
dashboard. Cairn does not resell or provision keys, and cannot help with billing
on them.

## Saving a key

**Settings → AI chat**. Paste the key and save. Saved providers show a **Saved**
state and a masked field reading `••••••••  enter a new key to replace`;
pasting a new key over it replaces the old one. **Remove** deletes it.

## Where your key lives

Encrypted on Cairn's servers, associated with your account — **never in your
browser and never on your device**. Once saved, a key is never sent back to the
browser; Settings only learns *that* a key exists, not what it is. Cairn uses it
server-side to make the request on your behalf.

The published privacy policy is direct about the limits of that protection: the
encryption defends against a database-only leak, not against a full compromise
of Cairn's servers, and answering a message requires the key in plaintext in
memory for the duration of that one request. It is never written to disk.

Removing a key in Settings deletes it from Cairn's database. Deleting your
account deletes your keys.

## What it costs

Whatever your provider charges for the model you pick, and nothing else. Two
things drive the bill more than anything:

- **The model.** Prices across the catalog differ by more than an order of
  magnitude — a frontier model costs many times what a fast, cheap one does.
  See [models and thinking levels](models-and-thinking.md).
- **Conversation length.** Your browser holds the conversation and sends the
  earlier messages along with each new one, so a long chat costs more per turn
  than a short one. Starting a fresh chat for a new question is the single
  cheapest habit to build. Images add to this too, since they are re-sent with
  each turn.

Reading a [knowledge base](knowledge-bases.md) also costs tokens — the assistant
is genuinely reading files — but it is what makes the answers specific.

## Rate limits, and why Gemini meets them first

Every provider caps how fast you may call it. What makes that surface sooner
than you would guess is this: **one question is usually several requests.**

Answering "what did he mean by regularization here?" can mean reading the
knowledge base index, opening a page, searching the web, and only then writing
the reply — and each of those steps is a separate, billed call to your provider.
A question that feels like one thing is often five or six. So a per-minute
allowance that sounds generous gets spent much faster than one question per
minute.

**On Gemini's free tier this is the thing you will notice.** The free allowance
is only a few requests a minute, so one involved question can consume most of a
minute, and two in quick succession can exhaust it. You will see *"Gemini is
rate-limiting this key."*

What actually helps, roughly in order:

- **Wait a minute.** Per-minute allowances refill on their own. Nothing is
  broken and nothing is lost — ask again.
- **Ask fewer, bigger questions.** A rapid series of small follow-ups is the
  worst pattern for a per-minute cap; one well-framed question costs less than
  five thin ones. See [asking good questions](asking-good-questions.md).
- **Switch to a lighter model.** Flash-Lite variants are given more headroom
  than the larger ones.
- **Enable billing on the key.** Paid tiers lift the limits substantially. You
  still pay Google directly; Cairn is not involved.
- **A second key will not help.** Google counts these limits against your
  Google *project*, not against the individual key, so creating another key in
  the same project shares the same allowance.

The free tier also has a **daily** cap, which resets at midnight US Pacific
time. If the chat works in the morning and refuses by evening, that is the one
you have hit rather than the per-minute limit. Google publishes your key's
actual limits on its
[rate limit page](https://aistudio.google.com/rate-limit) — worth a look, since
they differ per model.

**On OpenRouter, a rate-limit message usually is not about your balance.**
OpenRouter is a gateway: it passes your request to whichever vendor serves the
model you chose, and that vendor's limit is what you are meeting. Topping up
your OpenRouter credit will not clear it. Switching to a model from a different
vendor generally will.

**On DeepSeek this rarely comes up** for one person studying, which is part of
why it is the recommendation for sustained use.

## If the provider rejects the request

Cairn translates the common provider failures into plain messages:

| What you see | What it means |
|---|---|
| *"…rejected the API key. Check it in Settings."* | The key is wrong, revoked, or pasted with whitespace. |
| *"…reports insufficient credit for this request."* | Top up with the provider. Cairn cannot see your balance. |
| *"…is rate-limiting this key…"* | The provider's limit, not Cairn's. See [rate limits](#rate-limits-and-why-gemini-meets-them-first) — on Gemini's free tier this is common. |
| *"…is having trouble right now. Try again shortly."* | The provider is down or overloaded. |
| *"This conversation is too long for the selected model…"* | You hit the model's context window. Start a new chat, or ask something narrower so the assistant reads fewer files. |
| *"Too many requests. Slow down a moment."* | Cairn's own rate limit on chat requests. |

See [troubleshooting](troubleshooting.md).

## Related pages

- [The study chat](study-chat.md)
- [Models and thinking levels](models-and-thinking.md)
- [Privacy and your data](privacy-and-data.md)
