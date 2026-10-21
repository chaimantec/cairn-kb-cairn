# Sources

Everything in this knowledge base was compiled from Cairn's own public surfaces
and from the shipped extension itself, first on **2026-08-26** and revised since;
the fetch date on each row below says when that source was last read. There is no
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
| [`chaimantec/cairn-kb-cs336`](https://github.com/chaimantec/cairn-kb-cs336) | A published knowledge base carrying slide images — the example for what `raw/images/` holds and how many | — | 2026-09-06 |
| chaimantec, Cairn's maker | Authorship, the *Death Stranding* inspiration, and the current provider recommendation — stated directly, not published anywhere else | — | 2026-08-26 |
| chaimantec, Cairn's maker | GLM added as a third chat provider, keyed from Z.ai and defaulting to `glm-5.3-flash`; DeepSeek's catalog moving to `deepseek-v4.1-flash` and `deepseek-v4-pro`; both flash defaults reading images — stated directly, not published anywhere else | — | 2026-09-13 |
| chaimantec, Cairn's maker | The study chat saving notes: that it does so only when asked, the 🚩 marker it shares with `cairn-annotate`, where a note is pinned and who can see it, the two caps, and that an annotation re-run removes chat-saved notes — from the build that ships it, not published anywhere else | — | 2026-10-21 |
| [DeepSeek pricing](https://api-docs.deepseek.com/quick_start/pricing) | Off-peak discount and the peak hours. The per-model rates once quoted here were for `deepseek-v4-flash`, which has been withdrawn; no replacement figures have been read from this page | — | 2026-08-26 |
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

Several claims in this knowledge base come from Cairn's maker directly rather
than from a public page, and are marked as such where they appear: that Cairn is
made by chaimantec, that its design is inspired by *Death Stranding*, that GLM
is now a chat provider alongside DeepSeek and OpenRouter, which model each
provider defaults to, and that a direct DeepSeek key is the recommended setup.

The first two are durable. The rest are dated. The model catalog was last
described on **2026-09-13**, when `deepseek-v4-flash` — recommended here in
August — was withdrawn and replaced by `deepseek-v4.1-flash`, with
`deepseek-v4-pro` above it. That is how quickly this material goes stale.
Re-check it against the picker and the providers' own pricing pages rather than
quoting it as current.

How the study chat saves notes, documented on **2026-10-21**, is also the
maker's account rather than a published one. Its two caps are the ones the chat
enforces. The warning that re-running `cairn-annotate` removes chat-saved notes
describes how the two features interact today, and is the part most likely to
change.

No per-token price has been verified since 2026-08-26, so the pages quote none
for the current DeepSeek models and link to DeepSeek's pricing instead. The one
figure still quoted, for `anthropic/claude-sonnet-5`, is explicitly dated where
it appears.

## Where the published documents lag

[`raw/privacy-policy.md`](raw/privacy-policy.md) and
[`raw/landing-copy.md`](raw/landing-copy.md) are verbatim copies and are left
exactly as published. Both predate GLM: the landing copy still offers a choice
of "DeepSeek or OpenRouter", and the policy's third-party list still names only
DeepSeek, OpenRouter and Tavily. The wiki pages that draw on them say so rather
than silently correcting the quotes. When the published documents are updated,
re-copy them and drop those notes.
