# Sources

Everything in this knowledge base was compiled from Cairn's own public surfaces
and from the shipped extension itself, first on **2026-08-26**. There is no
course website to crawl and no lecture transcripts, because this KB is about the
tool rather than about a course.

| Source | Kind | Local copy | Fetched |
|---|---|---|---|
| [cairnstudy.com](https://cairnstudy.com/) | Landing page copy | [`raw/landing-copy.md`](raw/landing-copy.md) | 2026-08-26 |
| [cairnstudy.com/privacy.html](https://cairnstudy.com/privacy.html) | Privacy policy, last updated 2026-08-25 | [`raw/privacy-policy.md`](raw/privacy-policy.md) | 2026-08-26 |
| [Chrome Web Store listing](https://chromewebstore.google.com/detail/cairn/ipoiephjmljacojnhacbkbfbelicifim) | Store description, permissions, version | — | 2026-08-26 |
| Extension release notes | The changelog, verbatim | [`raw/changelog.md`](raw/changelog.md) | 2026-08-26 |
| Cairn, installed | The shipped UI — labels, defaults, limits, error messages | — | 2026-08-26 |
| [`chaimantec/cairn-kb-cs224n`](https://github.com/chaimantec/cairn-kb-cs224n) | A published knowledge base, used as the worked example | — | 2026-08-26 |
| chaimantec, Cairn's maker | Authorship, the *Death Stranding* inspiration, and the current provider recommendation — stated directly, not published anywhere else | — | 2026-08-26 |
| [DeepSeek pricing](https://api-docs.deepseek.com/quick_start/pricing) | `deepseek-v4-flash` peak/off-peak rates and the peak hours | — | 2026-08-26 |
| [Gemini API rate limits](https://ai.google.dev/gemini-api/docs/rate-limits) | That limits are counted per minute and per day, are applied per Google project rather than per key, and that the daily one resets at midnight US Pacific | — | 2026-08-26 |
| [Google AI Studio rate limit page](https://aistudio.google.com/rate-limit) | Where a user finds the limits actually applied to their own key — Google no longer publishes the per-model figures in its docs | — | 2026-08-26 |
| [Gemini API terms](https://ai.google.dev/gemini-api/terms) | That the free tier permits Google to use prompts and responses to improve its products, and the paid tier does not | — | 2026-08-26 |
| [OpenRouter rate limits](https://openrouter.ai/docs/api-reference/limits) | That paid models carry no gateway-level request cap, so a rate limit reflects the upstream vendor rather than the user's balance | — | 2026-08-26 |

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
`deepseek-v4-flash` used with a direct DeepSeek key is the recommended model.
The first two are durable. The third is dated: it and the prices quoted with it
were checked on 2026-08-26 against the providers' own published pricing, and
providers change both independently of Cairn's releases. Re-check it rather than
quoting it as current.
