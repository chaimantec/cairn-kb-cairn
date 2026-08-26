# FAQ

**What is Cairn?**
A Chrome extension that tracks your progress through university lecture courses
on YouTube, shows you timestamped notes other learners left, and offers an
optional AI study chat that has read the course. See
[what Cairn is](what-is-cairn.md).

**Where does the name come from?**
A cairn is a stack of stones left on a trail to mark the way for whoever comes
next. The design is inspired by *Death Stranding*, where other players are never
present and what helps you is the things they left behind — which is exactly
what a trace is. See [what Cairn is](what-is-cairn.md).

**Who makes Cairn?**
**chaimantec**, working solo. It is a free, independent side project, not a
company product.

**Is it free?**
Yes. It is a free side project. The only thing you might pay for is the
[AI chat](study-chat.md), and you pay the model provider directly, not Cairn.

**Do I need an account?**
No. Tracking, notes, courses and stats all work as a guest, stored in your
browser. An account adds cross-device sync and unlocks public traces, ratings,
catalog contributions and the chat. See [accounts and sync](accounts-and-sync.md).

**What does Google sign-in give Cairn access to?**
An opaque account identifier, and nothing else. Not your email, name, picture,
or any part of your YouTube account. See [privacy and your data](privacy-and-data.md).

**Does it work on Firefox or Safari? On my phone?**
No. Chrome and Chromium-based desktop browsers only.

**Do I have to mark lectures complete?**
No, that is the point. A lecture is complete once you have watched 90% of it.
You can still toggle it yourself. See [progress tracking](progress-tracking.md).

**Does Cairn track everything I watch on YouTube?**
No. Only videos that are lectures in courses you have added. Everything else is
ignored, and no other site is read at all.

**What is a "trace"?**
A short note pinned to a second in a lecture, left by another learner and shown
to you as that moment arrives. See [traces and notes](traces-and-notes.md).

**Can I reply to a trace?**
No, deliberately. There are no replies, follows or DMs. You can like one, and
leave your own.

**Are my notes public?**
Not unless you make them so. Notes start private; a padlock/globe toggle
publishes one under your nickname, and you can switch it back.

**Why does the AI chat need my own API key?**
So there is no subscription and no markup — you pay the provider at cost. It
supports DeepSeek and OpenRouter, plus Tavily for optional web search. See
[bring your own key](bring-your-own-key.md).

**Which model should I use?**
`deepseek-v4-flash` with a DeepSeek key, going to DeepSeek directly — that is
the current recommendation, and the DeepSeek default. It is cheap, and it caches
the repeated part of a conversation at about a thirtieth of the normal price,
which is most of what you would otherwise be paying for — and its off-peak rate,
covering most evenings and all weekend, is half of that again. Add OpenRouter
when you want the choice — one key reaching many vendors' catalogs, and any
model id they publish. See [models and thinking levels](models-and-thinking.md).

**Do I need to do anything to get prompt caching?**
No. It is handled for you on every provider Cairn supports, including Claude
models, which are the one family that has to be asked explicitly. There is no
setting. A long conversation is cheaper per turn than its token count suggests.

**Why is a Claude model more expensive, then?**
Its list price. `anthropic/claude-sonnet-5` is roughly $2 per million input
tokens and $10 per million output, against `deepseek-v4-flash`'s $0.44 and $1.32
at peak — halving off-peak. It is also the OpenRouter default in 1.3.0, so if
you saved an OpenRouter key and never opened the model picker, that is what you
are being billed for. See [models and thinking levels](models-and-thinking.md).

**Where is my key stored?**
Encrypted on Cairn's servers, never in your browser and never sent back to it.

**Are my chats stored on Cairn's servers?**
No. They live in your browser only, are not tied to your account, and do not
sync between devices.

**Why does the assistant know what I'm looking at?**
Every message carries the course, the lecture, and your playback position — so
"what did he just say?" resolves against the right moment.

**What is a knowledge base?**
A public GitHub repository built from a course's own materials — transcripts,
slide text, topic pages — that the chat reads before answering, and cites. See
[knowledge bases](knowledge-bases.md).

**Does every course have one?**
No, not yet. They are built one course at a time. Courses that have one show a
link in the catalog.

**Can I read a knowledge base without Cairn?**
Yes. It is ordinary markdown in a public Git repository. Browse it on GitHub,
clone it, or point any coding agent at it.

**Can I add a knowledge base to a course?**
If you created the catalog entry, yes — paste the repo URL into the course's
edit dialog. See [attaching a knowledge base](attach-a-knowledge-base.md).

**Who can edit a course in the catalog?**
Anyone signed in can add one; edits change the shared entry for everyone
enrolled. Personal data — progress, notes, ratings — is never in the catalog.

**How do I delete everything?**
**Settings → Delete account** removes your account and everything synced.
Uninstalling or clearing the extension's data removes what is local, including
your chats. See [privacy and your data](privacy-and-data.md).

**Is Cairn affiliated with Stanford, MIT, or YouTube?**
No. It is an independent project, made by chaimantec.

**Who do I contact?**
hello@cairnstudy.com
