# Bring your own key

The [study chat](study-chat.md) runs on **your** API key, from a provider you
have an account with. There is no Cairn subscription, no bundled credits, and no
markup:

*"The chat is off until you add your own API key from DeepSeek or OpenRouter, so
you pay the model provider directly at cost — Cairn takes no cut and resells
nothing."*

## The three providers

| Provider | For | Required? |
|---|---|---|
| **DeepSeek** | Chat models | One of the two chat providers is required |
| **OpenRouter** | Chat models — a gateway to models from many vendors | One of the two chat providers is required |
| **Tavily** | Web search and page reading | Optional. Without it, the chat has no web access. |

Save at least one chat key or the composer stays disabled. Tavily is purely
additive: with it, `web_search` and `web_fetch` appear; without it, they do not.

**If you are only going to set up one, make it DeepSeek.** A DeepSeek key
running `deepseek-v4-flash` is the recommendation for ordinary study use **as of
2026-08-26** — dated, not permanent, since providers reprice and replace models
faster than this page is revised. It is cheap, cheaper still off-peak, and its
limits are generous enough that you will not think about them.

**OpenRouter is what you add when you want the choice** — one key reaching many
vendors' catalogs, plus any model id OpenRouter publishes, so you can pick on
whatever grounds matter to you that day: price, speed, whether it reads
[images](images-in-chat.md), or simply a model you would rather use. Saving both
and switching per question is a perfectly good setup. See
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

## Rate limits

Every provider caps how fast you may call it. Cairn cannot raise those caps,
cannot see what they are, and does not share them between users — they are
yours, on your key.

What makes them arrive sooner than you would guess is this: **one question is
usually several requests.**

Answering "what did he mean by regularization here?" can mean reading the
[knowledge base](knowledge-bases.md) index, opening a page, searching the web,
and only then writing the reply — and each of those steps is a separate, billed
call to your provider. A question that feels like one thing is often five or
six. So an allowance quoted per minute goes much faster than "a few questions a
minute" would suggest, and a burst of quick follow-ups is the worst pattern for
it.

You will see *"…is rate-limiting this key."* Nothing is broken and nothing is
lost. What helps, roughly in order:

- **Wait a moment and ask again.** Per-minute allowances refill on their own.
- **Ask fewer, bigger questions.** One well-framed question costs fewer requests
  than five thin follow-ups. See
  [asking good questions](asking-good-questions.md).
- **Check which tier you are on.** A provider's free or entry tier is where this
  shows up; paid tiers lift the limits substantially.
- **On OpenRouter, try a model from a different vendor.** A rate-limit message
  there usually reflects the vendor serving the model you chose rather than your
  OpenRouter balance, so topping up will not clear it — but switching vendor
  generally will.

**On DeepSeek this rarely comes up** for one person studying, which is part of
why it is the recommendation.

## If the provider rejects the request

Cairn translates the common provider failures into plain messages:

| What you see | What it means |
|---|---|
| *"…rejected the API key. Check it in Settings."* | The key is wrong, revoked, or pasted with whitespace. |
| *"…reports insufficient credit for this request."* | Top up with the provider. Cairn cannot see your balance. |
| *"…is rate-limiting this key…"* | The provider's limit, not Cairn's. See [rate limits](#rate-limits) — one question is several requests, so this arrives sooner than expected. |
| *"…is having trouble right now. Try again shortly."* | The provider is down or overloaded. |
| *"This conversation is too long for the selected model…"* | You hit the model's context window. Start a new chat, or ask something narrower so the assistant reads fewer files. |
| *"Too many requests. Slow down a moment."* | Cairn's own rate limit on chat requests. |

See [troubleshooting](troubleshooting.md).

## Related pages

- [The study chat](study-chat.md)
- [Models and thinking levels](models-and-thinking.md)
- [Privacy and your data](privacy-and-data.md)
