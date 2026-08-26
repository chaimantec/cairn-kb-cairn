# Troubleshooting

## Progress is not being tracked

Work down this list:

1. **Is the video part of a course you have added?** Cairn only tracks lectures
   in your library. A video that is not in an imported playlist is ignored
   completely. See [adding courses](adding-courses.md).
2. **Is an ad playing?** Tracking pauses during ads by design.
3. **Was the tab open before you installed or updated Cairn?** Reload it — the
   content script is injected when the page loads.
4. **Is this lecture actually in the playlist?** A video posted after the
   playlist was imported will not be there until the course is refreshed.
5. **Give it ten seconds.** Progress is written on a ten-second poll, not
   instantly.

## The Live tab says "Nothing playing"

It needs a *tracked* lecture playing in a YouTube tab. The same checklist as
above applies. If several YouTube tabs are open, the one actually playing your
lecture is the one Cairn reads.

## A playlist will not import

Cairn's server reads public playlist metadata. A **private playlist** cannot be
imported. Check the URL is a playlist link (`.../playlist?list=PL...`) rather
than a single video link that happens to sit in a playlist.

If the playlist already exists in the catalog, Cairn enrols you in the existing
entry instead of creating a duplicate — that is the intended behaviour. Use
**Create my own** only if it is genuinely a different course.

## I have been signed out

Sessions last 30 days. A banner appears at the top of the sidebar offering to
sign in again; Cairn keeps working locally until you do. Nothing is lost.

## The Chat tab is locked

Two possible reasons, in order:

1. **You are not signed in.** The chat requires an account.
2. **No API key is saved.** Add a DeepSeek or OpenRouter key in **Settings → AI
   chat**. See [bring your own key](bring-your-own-key.md).

## The chat gives an error

| Message | What to do |
|---|---|
| *"…rejected the API key. Check it in Settings."* | Re-paste the key; check for stray whitespace and that it has not been revoked. |
| *"…reports insufficient credit for this request."* | Top up with your provider. Cairn cannot see your balance. |
| *"…is rate-limiting this key…"* | Your provider's limit. Wait a moment, or use a different model. See [rate limits](bring-your-own-key.md#rate-limits). |
| *"…is having trouble right now."* | Provider outage. Try again shortly. |
| *"This conversation is too long for the selected model."* | Start a new chat. See [managing chats](managing-chats.md). |
| *"Too many requests. Slow down a moment."* | Cairn's own rate limit. Pause briefly. |

## The chat is costing more than I expected

Three usual causes. **Long conversations** — the earlier messages are re-sent
with every new one, so a chat you have kept going all evening costs more per
turn than a fresh one; start a new chat per question. **Images** are re-sent the
same way. And **the model you are on** — prices across the catalog differ by
more than an order of magnitude.

Check the model picker first. Each provider has a default that you get if you
never opened the picker, and none of them is chosen for being the cheapest —
the spread across the catalog is more than an order of magnitude, so this is
usually the largest single thing you can change. `deepseek-v4-flash` on a
DeepSeek key is the cheap end. See [what it costs](bring-your-own-key.md) and
[models and thinking levels](models-and-thinking.md).

Cairn cannot see your spend — the usage readout is an estimate, and it is wrong
for any model it has no price data for. Your provider's dashboard is the
authority.

## The chat keeps saying it is being rate-limited

Your provider is refusing requests for a moment, not Cairn. The reason it
arrives sooner than expected is that **one question is usually several requests**
— the assistant reads a knowledge-base file, perhaps searches, then writes the
answer, and each step is its own call. A burst of quick follow-ups is the worst
pattern for a per-minute allowance.

Wait a moment and ask again; nothing is lost. Then ask fewer and larger
questions, and check which tier your key is on, since free and entry tiers are
where this shows up.

On **OpenRouter** the message usually reflects the vendor serving your chosen
model rather than your OpenRouter balance, so topping up will not clear it;
switching to a model from another vendor generally will.

More in [rate limits](bring-your-own-key.md#rate-limits).

## The chat does not know anything about my course

Check whether the course has a [knowledge base](knowledge-bases.md) — a link on
the course card or in the catalog. Without one, the assistant is answering from
general knowledge, which is exactly the vague-chatbot behaviour knowledge bases
exist to fix.

If the course *does* have one and answers are still generic, look at the tool
chips in the transcript: a working setup shows a `kb_read` of `INDEX.md` early
in the conversation. If none appear, the repository may be **private**, the URL
may be wrong, or the repo may have no `INDEX.md` at its root. See
[attaching a knowledge base](attach-a-knowledge-base.md).

## The chat cannot search the web

Web search needs a **Tavily** key, which is separate from your chat provider
key. Without it, `web_search` and `web_fetch` simply do not exist for the
assistant. See [bring your own key](bring-your-own-key.md).

## Images are not working

Check that the selected model can read images — the picker marks the ones that
can. Also check the format: JPEG, PNG, WebP and GIF are accepted, SVG is not.
Four images per message is the cap. See [images in chat](images-in-chat.md).

## My chats vanished

Chats live in your browser only. Clearing the extension's data, uninstalling, or
using a different browser or profile means they are gone — they do not sync and
cannot be recovered. This is by design; see
[privacy and your data](privacy-and-data.md).

Signing out does **not** delete them. Signing in with a different account
prompts you to keep or clear them.

## My progress on another computer is behind

Progress syncs only when signed in, and pushes in batches every half minute or
so. Make sure you are signed in on both machines with the same account, and give
it a moment. The merge always keeps the *furthest* position, so syncing can
never rewind you.

## Something else

Email **hello@cairnstudy.com**.

## Related pages

- [Limits and caps](limits-and-caps.md)
- [FAQ](faq.md)
