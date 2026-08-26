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
in the picker. Two things earn it that place.

**It is cheap.** Fast and cheap enough that the cost of a study session stops
being something you weigh before asking a question, and most study questions are
retrieval — finding the moment in the lecture, quoting a definition back,
checking whether lecture 3 covered something, reading the
[knowledge base](knowledge-bases.md) — which does not need a frontier model.

**Its caching behaviour is excellent, and caching is most of the bill.** Cairn
sends the earlier messages along with each new one, so by the third question the
majority of what you are paying for is text the provider has already seen.
DeepSeek caches that repeated prefix automatically, with nothing to configure,
and charges about a tenth of the normal input price to read it back. A long
conversation therefore costs far less than its length suggests.

### Caching is not the same on every provider

This is the part that decides the bill, and it varies by provider rather than by
gateway. Roughly:

| Provider | Caching | Cost of a cached read |
|---|---|---|
| DeepSeek | Automatic | ~0.1× the input price |
| OpenAI, Google Gemini, xAI Grok | Automatic | ~0.1–0.5× |
| **Anthropic (Claude)** | **Only when the request asks for it** | ~0.1× if asked, **full price if not** |

So going through OpenRouter is not itself the problem — OpenRouter follows
whatever the underlying provider does. The problem is specific: **Anthropic's
models do not cache unless the request explicitly asks them to**, and every
other major provider caches on its own. Pick a Claude model on a chat that
re-sends its history each turn and does not opt in, and you pay full price for
the whole conversation on every single message.

**Worth knowing about the shipped default:** the OpenRouter default in 1.3.0 is
`anthropic/claude-sonnet-5`, which is both the most expensive option in the
picker and the one whose caching is conditional. If you have saved an OpenRouter
key and never touched the model picker, that is what you are being billed for.
Choosing almost anything else is cheaper.

Prefer a direct DeepSeek key for everyday use, and reach for OpenRouter when you
specifically want a model DeepSeek does not publish. See
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
  This is what an OpenRouter key is for. Switching to it for a few hard questions
  rather than leaving it selected for a whole session is what keeps it
  affordable — doubly so for a Claude model, for the caching reason above.

You can change model mid-conversation; the change applies to the next message.

## Related pages

- [Bring your own key](bring-your-own-key.md)
- [Limits and caps](limits-and-caps.md)
- [Asking good questions](asking-good-questions.md)
