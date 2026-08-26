# Sources

Everything in this knowledge base was compiled from Cairn's own public surfaces
and from the shipped extension itself, at **version 1.3.0**, on **2026-08-26**.
There is no course website to crawl and no lecture transcripts, because this KB
is about the tool rather than about a course.

| Source | Kind | Local copy | Fetched |
|---|---|---|---|
| [cairnstudy.com](https://cairnstudy.com/) | Landing page copy | [`raw/landing-copy.md`](raw/landing-copy.md) | 2026-08-26 |
| [cairnstudy.com/privacy.html](https://cairnstudy.com/privacy.html) | Privacy policy, last updated 2026-08-25 | [`raw/privacy-policy.md`](raw/privacy-policy.md) | 2026-08-26 |
| [Chrome Web Store listing](https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim) | Store description, permissions, version | — | 2026-08-26 |
| Extension release notes | Changelog through 1.3.0 | [`raw/changelog.md`](raw/changelog.md) | 2026-08-26 |
| Cairn 1.3.0, installed | The shipped UI — labels, defaults, limits, error messages | — | 2026-08-26 |
| [`chaimantec/cairn-kb-cs224n`](https://github.com/chaimantec/cairn-kb-cs224n) | A published knowledge base, used as the worked example | — | 2026-08-26 |
| chaimantec, Cairn's maker | Authorship, the *Death Stranding* inspiration, and the current provider recommendation — stated directly, not published anywhere else | — | 2026-08-26 |
| [Anthropic prompt caching docs](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) | That Claude models cache only on explicit `cache_control`, and the read/write multipliers | — | 2026-08-26 |
| [OpenRouter prompt caching docs](https://openrouter.ai/docs/features/prompt-caching) | Which providers cache automatically, and their multipliers | — | 2026-08-26 |

## What is deliberately not here

This knowledge base documents Cairn as a **user** meets it. It does not
document how Cairn is built: there are no pages on the server architecture, the
API endpoints, the database, or the source layout, and no description of
features that have not shipped. Where a question genuinely turns on where data
goes — which key is stored where, what reaches a model provider — the answer is
taken from the published privacy policy and cited to it.

Cairn's source code is not public, so nothing here is quoted from it.

## The maker-supplied facts

Three claims in this knowledge base come from Cairn's maker directly rather than
from a public page, and are marked as such where they appear: that Cairn is made
by chaimantec, that its design is inspired by *Death Stranding*, and that
`deepseek-v4-flash` used with a direct DeepSeek key is the current
recommendation. The first two are durable; the third is a snapshot of provider
prices in August 2026 and should be re-checked before being quoted as current.

The supporting claim about **prompt caching** — that DeepSeek, OpenAI, Gemini
and Grok cache automatically while Anthropic's models cache only when the
request explicitly asks — is provider-documented behaviour, checked against
Anthropic's prompt-caching documentation and OpenRouter's prompt-caching page on
2026-08-26, not something taken on assertion. It is provider behaviour and will
move; re-check it rather than trusting this page's date.
