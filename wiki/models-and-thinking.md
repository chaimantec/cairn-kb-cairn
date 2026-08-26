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
in the picker. It is fast and cheap enough that the cost of a study session stops
being something you weigh before asking, and most study questions are retrieval
— finding the moment in the lecture, quoting a definition back, checking whether
lecture 3 covered something, reading the
[knowledge base](knowledge-bases.md) — which does not need a frontier model.

**Reaching a model through OpenRouter is not the same as reaching it directly.**
Prompt caching does not always work as expected through OpenRouter, and when it
does not, you pay full price for the entire conversation on every turn instead
of a reduced rate for the part that was already cached. Because Cairn re-sends
the earlier messages with each new one, caching is most of what keeps a long
chat cheap, so losing it is a multiplier rather than a rounding error. Prefer a
direct DeepSeek key for everyday use, and reach for OpenRouter when you
specifically want a model DeepSeek does not publish. See
[what it costs](bring-your-own-key.md).

This is a recommendation about today's providers and today's prices, not a
property of the product — both move, and the picker will take whatever you
choose.

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
  This is what an OpenRouter key is for, and switching to it for a few hard
  questions rather than a whole session keeps the caching problem above small.

You can change model mid-conversation; the change applies to the next message.

## Related pages

- [Bring your own key](bring-your-own-key.md)
- [Limits and caps](limits-and-caps.md)
- [Asking good questions](asking-good-questions.md)
