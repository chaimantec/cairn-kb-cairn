# Asking good questions

The [study chat](study-chat.md) is not a general chatbot in a sidebar. It knows
the lecture and the second you are paused at, and — when the course has one — it
reads that course's actual [knowledge base](knowledge-bases.md) before it
answers. Questions that use those two things get much better answers than
questions that could have been typed into any chatbot.

## Point at things

Pause and ask. Your position is attached to every message, so deictic language
works:

- *"Wait — what did he just say?"*
- *"What is he actually doing here?"*
- *"Why does this step follow from the last one?"*
- *"Can you write out what's on the board right now properly?"*

The assistant resolves *this*, *here* and *what he just said* against your
playback position and pulls that moment out of the transcript.

## Ask across the course, not just this lecture

It can read the whole course, so questions that span lectures are fair game:

- *"Didn't lecture 3 already cover this? What's different here?"*
- *"Where was the bias-variance tradeoff introduced?"*
- *"Which lectures should I have watched before this one?"*
- *"Give me a list of everything in this course that uses the chain rule."*

## Ask for the source

It cites files, and the citations are openable links:

- *"Where do the slides derive this? I want to see the steps."*
- *"Which slide is that on?"*
- *"Is there a handout that covers this?"*
- *"Quote me exactly what he said about regularization."*

Things written down — equations, tables, citations — are usually best answered
from the slides; things said aloud, from the transcript. Asking for one or the
other explicitly tends to get you the more precise answer.

## Calibrate the explanation to you

- *"Explain this like I've only done one calculus course."*
- *"I know the linear algebra, skip that part."*
- *"Give me the intuition first, then the derivation."*
- *"What's the simplest example where this actually matters?"*

If a preference is permanent rather than for this one answer, say *"remember
that"* and it applies to every future chat. See [chat memory](chat-memory.md).

## Use it on your own work

Attach a photo or a snapshot and ask a real question — see
[images in chat](images-in-chat.md):

- *"I get a different answer for part (b). Where did I go wrong?"*
- *"Is this proof step valid?"*
- *"What is the y-axis on this plot measuring?"*

## Before and after a lecture

- *"What should I already know before watching this one?"*
- *"Give me three questions to check I actually followed this lecture."*
- *"Summarize what this lecture established, in five bullets I can put in a note."*
- *"What's the one thing from this lecture I'll need later in the course?"*

That last pattern pairs well with [traces](traces-and-notes.md): work the answer
out in chat, then leave a short note pinned at the moment it applies.

## What it is less good at

- **Anything outside the course, without a Tavily key.** No web access is
  configured by default; see [what the chat can look up](chat-tools.md).
- **A course with no knowledge base.** It will say so and answer from its own
  general knowledge, which is exactly the vague-chatbot experience the knowledge
  base exists to fix. See [attaching a knowledge base](attach-a-knowledge-base.md).
- **Reading your notes, progress or ratings.** It does not have access to them.
  Paste what you want it to see.
- **Doing your problem set for you.** It will help, but the useful mode is
  "check my working" rather than "produce an answer".

## A habit worth having

Start a **new chat per topic** rather than one long chat per lecture. Your
browser re-sends the whole conversation each turn, so a long chat gets slower
and more expensive with every message, and eventually hits the model's context
window. Short, focused chats are cheaper and get better answers. See
[managing chats](managing-chats.md).

## Related pages

- [The study chat](study-chat.md)
- [What the chat can look up](chat-tools.md)
- [Knowledge bases](knowledge-bases.md)
