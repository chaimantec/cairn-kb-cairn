# Models and thinking levels

The model picker sits at the top of the [chat](study-chat.md), showing whichever
model is currently selected. Only providers you have saved a key for are
offered.

## Choosing a model

Each provider offers a list of its catalog models. Models capable of reading
images are marked, which matters if you intend to
[attach screenshots](images-in-chat.md).

The defaults, if you do not choose:

| Provider | Default model |
|---|---|
| DeepSeek | `deepseek-v4-flash` |
| OpenRouter | `anthropic/claude-sonnet-5` |

**Any OpenRouter model id works, listed or not.** There is a free-text field —
*"any OpenRouter model id"* — because OpenRouter adds models faster than any
bundled list can keep up. Type the id exactly as OpenRouter publishes it and it
is used. The one side effect is that the usage readout's cost estimate will be
wrong for a model Cairn has no price data for; the request itself is unaffected.

Your choice is remembered as your default for future chats.

## The recommendation: `deepseek-v4-flash`, direct from DeepSeek

If you want one answer rather than a decision, use **`deepseek-v4-flash` with a
DeepSeek key, going to DeepSeek directly**. That is the current recommendation
from Cairn's maker, as of August 2026, and the reason it is the DeepSeek default
in the picker. Three things earn it that place.

**It is cheap.** Fast and cheap enough that the cost of a study session stops
being something you weigh before asking a question, and most study questions are
retrieval — finding the moment in the lecture, quoting a definition back,
checking whether lecture 3 covered something, reading the
[knowledge base](knowledge-bases.md) — which does not need a frontier model.

**Its caching is excellent, and caching is most of the bill.** Cairn sends the
earlier messages along with each new one, so by the third question the majority
of what you are paying for is text the provider has already seen. DeepSeek
caches that repeated prefix automatically, with nothing to configure, and reads
it back at roughly **a thirtieth** of the normal input price — a far steeper
discount than most providers offer. A long conversation therefore costs much
less than its length suggests.

**Its off-peak rate is half price.** DeepSeek bills peak and off-peak, and peak
is only 01:00–04:00 and 06:00–10:00 UTC on weekdays — about a fifth of the week.
Evening and weekend study, which is when most of it happens, is off-peak.

### What `deepseek-v4-flash` actually costs

Per million tokens, as published in August 2026 — check
[DeepSeek's pricing page](https://api-docs.deepseek.com/quick_start/pricing) for
current figures, since these move:

| | Peak | Off-peak |
|---|---|---|
| Input, already cached | $0.014 | $0.007 |
| Input, not yet cached | $0.44 | $0.22 |
| Output | $1.32 | $0.66 |

After the first question or two, most input is the cached kind. That is why a
long conversation on this model stays cheap in a way its token count does not
predict.

### A note on caching and Claude models

Anthropic's models are the one family that does not cache automatically: the
request has to ask, by marking where the reusable prefix ends. Every other major
provider — DeepSeek, OpenAI, Gemini, Grok — caches on its own.

**This is handled for you and is not something you need to think about.** The
library Cairn uses to talk to providers sets those markers itself for Claude
models reached through OpenRouter, so the conversation caches the same way it
would anywhere else. It is worth knowing only if you are comparing Cairn's costs
against some other tool that does not do it.

So a Claude model is not expensive here because of caching. It is expensive
because of its list price: `anthropic/claude-sonnet-5` is around $2 per million
input tokens and $10 per million output, against `deepseek-v4-flash`'s $0.44 and
$1.32 at peak, halving off-peak.

**Worth knowing about the shipped default:** the OpenRouter default in 1.3.0 is
`anthropic/claude-sonnet-5`, the most expensive option in the picker. If you
saved an OpenRouter key and never touched the model picker, that is what you are
being billed for, and almost anything else you choose is cheaper.

Prefer a direct DeepSeek key for everyday use. OpenRouter is what you add when
you want the choice — one key reaching many vendors' catalogs, plus any model id
they publish, so you are not limited to what one provider happens to offer. What
that choice costs is then down to the model you make with it. See
[what it costs](bring-your-own-key.md).

This is a description of today's providers and today's prices, not a property of
the product — both move, and the picker will take whatever you choose.

## Thinking levels

Models that support extended reasoning expose a level control, from least to
most:

`off` · `minimal` · `low` · `medium` · `high` · `xhigh` · `max`

More thinking means better answers on genuinely hard questions — a derivation
you cannot follow, a proof step that seems to skip something — and more tokens,
which means more money and more waiting. For "what did he just say at 24:10?"
it buys you nothing.

If you pick a level a model does not support, the request is not rejected: it is
clamped down to the nearest level that model does support. So leaving it high
while switching between models is safe.

## Which to pick

A reasonable pattern:

- **`deepseek-v4-flash` at low thinking** for the bulk of it — locating things
  in the lecture, definitions, "did lecture 3 cover this", reading the
  [knowledge base](knowledge-bases.md) and quoting it back.
- **A strong model at higher thinking** for the moment you are actually stuck on
  the mathematics, or when you want a derivation worked through step by step.
  Switching to one for a few hard questions rather than leaving it selected for a
  whole session is what keeps it affordable — doubly so for a Claude model, for
  the caching reason above.

You can change model mid-conversation; the change applies to the next message.

## Related pages

- [Bring your own key](bring-your-own-key.md)
- [Limits and caps](limits-and-caps.md)
- [Asking good questions](asking-good-questions.md)
