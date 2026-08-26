# KB build — Cairn (the extension itself)

Not a course KB: there are no lectures, transcripts, or slide decks. The sources
are Cairn's public surfaces — the landing page at cairnstudy.com, the published
privacy policy, the Chrome Web Store listing, and the shipped extension UI at
version 1.3.0.

**Scope decision (2026-08-26):** user-facing only. What Cairn does, how to use
it, what it costs, where data goes. No internal architecture, no API route
surface, no database schema, no unshipped roadmap.

## Raw sources
- [x] raw/privacy-policy.md — verbatim published policy
- [x] raw/changelog.md — verbatim release notes
- [x] raw/landing-copy.md — the public site's own words
- [x] sources.md — where each came from, and the date

## Wiki — the product
- [x] wiki/what-is-cairn.md
- [x] wiki/install-and-setup.md
- [x] wiki/adding-courses.md
- [x] wiki/progress-tracking.md
- [x] wiki/accounts-and-sync.md
- [x] wiki/catalog.md
- [x] wiki/live-tab.md
- [x] wiki/traces-and-notes.md
- [x] wiki/ratings.md
- [x] wiki/stats-dashboard.md

## Wiki — the study chat
- [x] wiki/study-chat.md
- [x] wiki/bring-your-own-key.md
- [x] wiki/models-and-thinking.md
- [x] wiki/chat-tools.md
- [x] wiki/chat-memory.md
- [x] wiki/images-in-chat.md
- [x] wiki/managing-chats.md
- [x] wiki/asking-good-questions.md

## Wiki — knowledge bases
- [x] wiki/knowledge-bases.md
- [x] wiki/attach-a-knowledge-base.md
- [x] wiki/building-a-knowledge-base.md
- [x] wiki/kb-repo-layout.md
- [x] wiki/annotating-lectures.md

## Wiki — reference
- [x] wiki/privacy-and-data.md
- [x] wiki/limits-and-caps.md
- [x] wiki/troubleshooting.md
- [x] wiki/faq.md
- [x] wiki/glossary.md

## Publish
- [x] AGENTS.md rewritten for a non-course KB
- [x] INDEX.md — annotated table of contents
- [x] kb.json
- [x] Link sweep (no unresolvable relative links)
- [x] Commit and push to chaimantec/cairn-kb-cairn

## Update — 2026-08-26 (maker-supplied facts)

Four facts stated directly by Cairn's maker, recorded in `sources.md` as a
source in their own right since none of them appears on a public page.

- [x] Authorship (chaimantec) — `wiki/what-is-cairn.md` "Who makes it",
      `wiki/faq.md`, `wiki/glossary.md`, `INDEX.md`
- [x] *Death Stranding* as the design inspiration — `wiki/what-is-cairn.md`,
      `wiki/faq.md`, `wiki/glossary.md`, `INDEX.md`
- [x] `deepseek-v4-flash` direct from DeepSeek is the current recommendation —
      `wiki/models-and-thinking.md`, `wiki/bring-your-own-key.md`, `wiki/faq.md`
- [x] Why caching decides the bill, corrected against the providers' own docs:
      caching follows the provider, not the gateway — DeepSeek, OpenAI, Gemini
      and Grok cache automatically, Anthropic's models cache only when the
      request asks. `wiki/models-and-thinking.md`, `wiki/bring-your-own-key.md`,
      `wiki/troubleshooting.md`, `wiki/faq.md`
- [x] Note that the shipped 1.3.0 OpenRouter default, `anthropic/claude-sonnet-5`,
      is both the priciest option in the picker and the one whose caching is
      conditional
- [x] `sources.md` — maker as a source, and which claims rest on it
- [x] `kb.json` — provenance source and caveat
- [x] Link sweep and commit

### Open — depends on the extension, not the KB

- [ ] If the OpenRouter default changes from `anthropic/claude-sonnet-5`, update
      `wiki/models-and-thinking.md` (defaults table and the recommendation
      section), `wiki/faq.md` and `wiki/troubleshooting.md`, all of which now
      name it. Recommendation put to the maker on 2026-08-26 was
      `google/gemini-3.7-flash` — automatic caching, vision, 1M context, and
      about a fifth of the price. Not documented here until it ships: this KB
      describes what ships.
