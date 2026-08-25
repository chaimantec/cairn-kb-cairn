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

- **A fast, cheap model at low thinking** for the bulk of it — locating things
  in the lecture, definitions, "did lecture 3 cover this", reading the
  [knowledge base](knowledge-bases.md) and quoting it back. Most study questions
  are retrieval, and retrieval does not need a frontier model.
- **A strong model at higher thinking** for the moment you are actually stuck on
  the mathematics, or when you want a derivation worked through step by step.

You can change model mid-conversation; the change applies to the next message.

## Related pages

- [Bring your own key](bring-your-own-key.md)
- [Limits and caps](limits-and-caps.md)
- [Asking good questions](asking-good-questions.md)
