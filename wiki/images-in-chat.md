# Images in chat

The [study chat](study-chat.md) reads images. There are two ways to get one in.

## Snapshot of the lecture

The composer has a control that grabs **the current frame of the lecture you are
watching** — one click, no screenshot tool. It is pulled from the video itself,
so you get the slide at video resolution, cleanly, with no comments panel or
sidebar around it, and it works even if the player is scrolled half off the
screen.

This is the fastest way to ask about something on a slide: pause, snapshot, ask.

If you have several YouTube tabs open, the tab actually playing that lecture is
the one that answers — the wrong video cannot supply the frame.

## Attaching your own

The other control takes a file: a screenshot, a photo of a problem set, a
scanned page, or a photo of your own working. Accepted formats are **JPEG, PNG,
WebP and GIF**. SVG is not accepted, as it is markup rather than an image.

Images are downscaled in your browser before they are sent — to a maximum edge
of about 1568 pixels, and roughly 300 KB — which is enough for a slide or a page
of handwriting and keeps the request small.

## Limits

| | |
|---|---|
| Images per message | **4** |
| Images across a whole conversation | **24** |

At four attachments the composer refuses a fifth. The conversation-wide cap
exists because your browser re-sends the whole conversation on every turn, so
images accumulate cost as a chat grows. See [limits and caps](limits-and-caps.md).

## What it does with them

It is told to **work from what is in the image rather than describing it back to
you**: solve the problem, find the error in your working, explain that specific
figure. So ask a question rather than just attaching:

- "Where does the second line come from?" — with a snapshot of the slide.
- "I get a different answer for (b). What did I do wrong?" — with a photo of
  your working.
- "What is the x-axis on this plot actually measuring?"

**Use a model that can read images.** Not every model can. The picker marks
which ones do — see [models and thinking levels](models-and-thinking.md). Sending
an image to a model without vision will not work.

## Related pages

- [The study chat](study-chat.md)
- [Asking good questions](asking-good-questions.md)
- [Limits and caps](limits-and-caps.md)
