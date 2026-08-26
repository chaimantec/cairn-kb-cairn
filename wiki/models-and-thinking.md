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
| OpenRouter | `openai/gpt-5.6-luna` |

**Any OpenRouter model id works, listed or not.** There is a free-text field —
*"any OpenRouter model id"* — because OpenRouter adds models faster than any
bundled list can keep up. Type the id exactly as OpenRouter publishes it and it
is used. The one side effect is that the usage readout's cost estimate will be
wrong for a model Cairn has no price data for; the request itself is unaffected.

Your choice is remembered as your default for future chats.

## The recommendation, as of 2026-08-26: `deepseek-v4-flash`, direct from DeepSeek

> **Dated on purpose.** Providers reprice and replace models every few months,
> independently of Cairn's releases and faster than this page is revised. If you
> are reading this well after 2026-08-26, check the providers' own pricing pages
> rather than taking it as current. The picker will take whatever you choose.

If you want one answer rather than a decision, use **`deepseek-v4-flash` with a
DeepSeek key, going to DeepSeek directly**. It is the DeepSeek default in the
picker for this reason.

It is cheap enough that the cost of a study session stops being something you
weigh before asking a question, and most study questions are retrieval — finding
the moment in the lecture, quoting a definition back, checking whether lecture 3
covered something, reading the [knowledge base](knowledge-bases.md) — which does
not need a frontier model. DeepSeek also charges **half price off-peak**, and
peak is only 01:00–04:00 and 06:00–10:00 UTC on weekdays, so evening and weekend
study is always at the lower rate.

Per million tokens on 2026-08-26, at the peak rate — see
[DeepSeek's pricing](https://api-docs.deepseek.com/quick_start/pricing) for
current figures:

| | `deepseek-v4-flash` | `anthropic/claude-sonnet-5` (for comparison) |
|---|---|---|
| Input | $0.44 | $2.00 |
| Output | $1.32 | $10.00 |

**A default is a starting point, not a recommendation.** Each provider's default
is a reasonable middle of its own catalog, and none of them is chosen to be the
cheapest thing available. If you saved a key and never opened the picker, it is
worth one look — the spread between models is wide enough that the choice
matters more than almost anything else you can change.

Prefer a direct DeepSeek key for sustained use. OpenRouter is what you add when
you want the choice — one key reaching many vendors' catalogs, plus any model id
they publish, so you are not limited to what one provider happens to offer. What
that choice costs is then down to the model you make with it. See
[what it costs](bring-your-own-key.md).

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
  whole session is what keeps it affordable.

You can change model mid-conversation; the change applies to the next message.

## Related pages

- [Bring your own key](bring-your-own-key.md)
- [Limits and caps](limits-and-caps.md)
- [Asking good questions](asking-good-questions.md)
