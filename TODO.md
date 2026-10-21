# KB build — Cairn (the extension itself)

Not a course KB: there are no lectures, transcripts, or slide decks. The sources
are Cairn's public surfaces — the landing page at cairnstudy.com, the published
privacy policy, the Chrome Web Store listing, and the shipped extension UI.
This KB does not track version numbers — see `AGENTS.md`.

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
- [x] Why caching decides the bill — DeepSeek reads cached text at ~1/30 of its
      input price. `wiki/models-and-thinking.md`, `wiki/bring-your-own-key.md`,
      `wiki/troubleshooting.md`, `wiki/faq.md`
- [x] `deepseek-v4-flash` peak/off-peak price table, and the peak hours
- [x] **Corrected 2026-08-26:** an earlier revision of these pages claimed Claude
      models through OpenRouter were billed uncached. Wrong. Anthropic does
      require explicit cache markers where other providers do not, but
      `@earendil-works/pi-ai` — the library Cairn uses to reach providers — sets
      them itself for `anthropic/*` ids on OpenRouter (`generate-models.ts:682`
      sets `cacheControlFormat: "anthropic"`; retention defaults to `short`, not
      `none`). Claude is dearer here for the ordinary reason: its list price.
- [x] Note that the shipped 1.3.0 OpenRouter default, `anthropic/claude-sonnet-5`,
      is the priciest option in the picker
- [x] `sources.md` — maker as a source, and which claims rest on it
- [x] `kb.json` — provenance source and caveat
- [x] Link sweep and commit

## Revision 2026-08-26 — rate limits, and the new OpenRouter default

- [x] ~~Add **Gemini** as a third chat provider~~ — **added, then reverted the
      same day.** Gemini was withheld from the extension's UI before release:
      the free tier a learner would sign up for allows only a few requests a
      minute, and one question is several requests, so it rate-limited during
      ordinary study. It is still supported end to end in the extension, just
      not offered, so this is a re-enable rather than a rebuild. See the
      deferred item below.
- [x] OpenRouter default is now `openai/gpt-5.6-luna`. Removed every claim that
      the default is `anthropic/claude-sonnet-5` and the "most expensive option
      in the picker" framing built on it — `wiki/models-and-thinking.md`,
      `wiki/faq.md`, `wiki/troubleshooting.md`. Claude's prices are kept as a
      comparison, since the point about model choice driving the bill stands.
- [x] **Rate limits, the point of this revision.** New section in
      `wiki/bring-your-own-key.md`; a symptom section in
      `wiki/troubleshooting.md`; an FAQ entry; and the requests-vs-questions
      distinction in `wiki/limits-and-caps.md`. The load-bearing fact is that
      **one question is several requests** — a KB read, a search and the answer
      are separate calls — which is why a per-minute allowance goes sooner than
      a user expects.
- [x] The rate-limit material **survives the Gemini revert**, rewritten to be
      provider-general. The load-bearing insight is not Gemini-specific: one
      question is several requests, so any per-minute allowance goes sooner than
      "a few questions a minute" implies. It applies to DeepSeek and OpenRouter
      and will apply to whatever is added next.
- [x] Version references are gone throughout — `INDEX.md`, `sources.md`,
      `kb.json`, `wiki/study-chat.md`, `wiki/what-is-cairn.md`.
      **Deliberate policy, per the maker (2026-08-26): this KB does not track
      versions.** Chrome auto-updates the extension, so a reader is on the
      current build and cannot choose otherwise — "which version added what" is
      a fact they can do nothing with. Describe current behaviour and nothing
      else. (An earlier draft of this entry dropped the pins for a different and
      wrong reason: that these pages had moved past 1.3.0. They had not. Gemini,
      the chat and knowledge bases are all 1.3.0, which had not yet released.)
- [x] `sources.md` and `kb.json` — Google and OpenRouter limit/terms sources.

### Open — depends on the extension, not the KB

- [ ] **If Gemini is re-offered in the extension, restore its documentation.**
      It is hidden by a single list in the extension, not removed, so this can
      come back quickly. What to put back, all of it written once and reverted
      in commit history rather than lost: the provider row and free-key on-ramp
      in `wiki/bring-your-own-key.md`; the `gemini-3.7-flash` default row in
      `wiki/models-and-thinking.md`; the provider lists in `wiki/study-chat.md`,
      `wiki/install-and-setup.md`, `wiki/glossary.md`, `wiki/faq.md`,
      `wiki/troubleshooting.md` and `INDEX.md`; that Google counts limits **per
      project, not per key** (the fix people reach for first); and the note in
      `wiki/privacy-and-data.md` that Google's free-tier terms permit training
      on prompts while the paid tier does not. Sources for those claims are in
      the same reverted commit.
- [ ] Worth checking in the extension, not the KB: the `cacheControlFormat`
      rule in pi-ai keys off the *generated model catalog*. A model id typed
      into the free-text "any OpenRouter model id" field that is not in the
      catalog may not get compat computed, and so may not get cache markers.
      Raised 2026-08-26; not documented until confirmed either way.
- [x] Attach an explicit date to the model recommendation everywhere it appears
      (`wiki/models-and-thinking.md`, `wiki/bring-your-own-key.md`,
      `wiki/faq.md`, `INDEX.md`, `kb.json`) and say plainly it is a snapshot, not
      a standing answer — providers reprice faster than this KB is revised
- [x] Record that the first read of a knowledge-base page is billed uncached and
      every later turn re-reads it from cache — `wiki/bring-your-own-key.md`,
      `wiki/faq.md`
- [x] **Scope trim, 2026-08-26:** removed the prompt-caching explanations added
      earlier in the day — per-provider caching behaviour, cache-hit vs
      cache-miss price rows, which library sets cache markers, the first-read
      cache miss. All of it was investigation notes rather than anything a user
      acts on. What survives is the dated recommendation, plain model prices, and
      the warning about the expensive OpenRouter default. Keep this KB to what a
      user meets.

- [x] **Slide images, 2026-09-06:** documented that a knowledge base may carry
      the course's slides as pictures and that a learner can just ask to see one
      — the case that motivates it being a recording that blanks or blurs a
      figure it could not license, where the deck-built knowledge base still has
      it. Written as a general knowledge-base capability, with
      `chaimantec/cairn-kb-cs336` (373 images, 14 lectures) as the illustration
      rather than the subject. Touched `wiki/images-in-chat.md` (the new
      section), `wiki/knowledge-bases.md`, `wiki/kb-repo-layout.md`,
      `wiki/building-a-knowledge-base.md`, `wiki/chat-tools.md`,
      `wiki/study-chat.md`, `wiki/asking-good-questions.md`, `wiki/faq.md`,
      `wiki/glossary.md`, `INDEX.md`, `sources.md` and `kb.json`. Corrected the
      claim in `wiki/building-a-knowledge-base.md` that prose is the only
      representation of a figure a knowledge base will have — true before this
      step existed, false now.

## Revision 2026-09-13 — GLM, and DeepSeek's new catalog

- [x] **GLM is a third chat provider.** Students save a GLM key from
      **Z.ai** and its models appear in the picker, defaulting to
      `glm-5.3-flash`, which reads images. Added the provider row and an
      on-ramp paragraph in `wiki/bring-your-own-key.md` (now "the four
      providers", and every "one of the two chat providers" reads *three*), the
      default row in `wiki/models-and-thinking.md`, and the provider lists in
      `wiki/study-chat.md`, `wiki/install-and-setup.md`, `wiki/glossary.md`,
      `wiki/faq.md`, `wiki/troubleshooting.md`, `wiki/privacy-and-data.md` and
      `INDEX.md`. This is the same page set the reverted Gemini work touched —
      see the open Gemini item above, which is unaffected.
- [x] **`deepseek-v4-flash` is withdrawn.** Replaced by `deepseek-v4.1-flash`,
      now the DeepSeek default and vision-capable, with `deepseek-v4-pro` above
      it for questions a flash model does not do well. The recommendation moves
      to `deepseek-v4.1-flash` and is re-dated **2026-09-13** everywhere it
      appears. No id that no longer exists survives anywhere in `wiki/`.
- [x] **Dropped the DeepSeek price table** in `wiki/models-and-thinking.md` and
      the price comparison in `wiki/faq.md`. They quoted $0.44/$1.32 for a model
      you can no longer buy, and no replacement figure has been verified. Per
      `AGENTS.md`, a missing number beats a guessed one: both places now link to
      DeepSeek's pricing. The `anthropic/claude-sonnet-5` figures stay as the
      other end of the range, explicitly dated 2026-08-26.
- [x] The off-peak claim survives — half price outside 01:00–04:00 and
      06:00–10:00 UTC on weekdays is a DeepSeek platform policy rather than a
      per-model rate, so the model change does not invalidate it.
- [x] Vision is no longer OpenRouter-only. `wiki/images-in-chat.md` now says
      both direct-provider defaults read images, so a student who never opens
      the picker can still attach a screenshot.
- [x] `sources.md` — the maker as a source again, dated 2026-09-13; a new
      section on where the published documents lag. `kb.json` — the new source,
      three revised caveats, `updated`.

### Open — depends on Cairn's published documents, not the KB

- [ ] **`raw/` predates GLM and is left alone.** The landing copy still reads
      *"your own API key from DeepSeek or OpenRouter"* and the privacy policy's
      third-party list still names only DeepSeek, OpenRouter and Tavily. Both
      are verbatim copies, so editing them to add GLM would make them stop
      matching what is published. `wiki/bring-your-own-key.md` and
      `wiki/privacy-and-data.md` note the gap instead. When cairnstudy.com and
      the policy are updated, re-copy both files and delete those two notes.
- [ ] No per-token price for `deepseek-v4.1-flash`, `deepseek-v4-pro` or
      `glm-5.3-flash` has been read from a provider's pricing page. Worth one
      pass to restore a real cost comparison, which was the most concrete thing
      on `wiki/models-and-thinking.md`.
- [ ] Unverified, so undocumented: whether `deepseek-v4-pro` reads images, and
      what GLM's catalog holds beyond `glm-5.3-flash`.
- [ ] `deepseek-v4-flash-vision-exp` was reported deprecated on 2026-09-13, but
      it appears nowhere in this repo or its git history — it was never
      documented, so there was nothing to remove.

## Revision 2026-10-21 — the chat can save notes

- [x] **The study chat has a note-saving tool.** Asked to — *"save that as a
      note"* — it writes the point up and posts it to the lecture: pinned at the
      playback position unless the point belongs to another moment, private
      unless the student asks for public, and prefixed 🚩, the marker
      `cairn-annotate` already uses. It never saves on its own initiative. The
      main section is in `wiki/chat-tools.md` (a table row and "Saving a note to
      the lecture"); supporting edits in `wiki/study-chat.md` (capability row),
      `wiki/traces-and-notes.md` (the agent section now covers both agents),
      `wiki/chat-memory.md` ("remember this" about content gets a note, not a
      memory), `wiki/live-tab.md`, `wiki/faq.md` and `INDEX.md`.
- [x] Two caps in `wiki/limits-and-caps.md`: 5 notes in one reply, 2,000
      characters a note. The assistant aims well under that — a few sentences —
      but the page lists only what is enforced.
- [x] `wiki/privacy-and-data.md` — a saved note is an ordinary note, so unlike
      the conversation it came from it reaches Cairn's servers.
- [x] `sources.md` and `kb.json` — the maker's account as a dated source.

### Open

- [ ] **The annotation re-run removes chat-saved notes.** `cairn-annotate`
      clears every 🚩 note on a lecture before posting, and chat notes carry the
      same flag. Documented as a warning in `wiki/chat-tools.md` and
      `wiki/annotating-lectures.md` (and as a source caveat). If the skill stops
      doing this, delete both warnings and the caveat.
- [ ] `raw/changelog.md` stops before GLM. Re-copy it verbatim from the
      extension's changelog once the release carrying note-saving ships.
