# Images in chat

The [study chat](study-chat.md) reads images, and it can also show you one.
There are two ways to get an image *in* — the lecture frame, or a file of your
own — and one way images come *out*: the course's own slides, when its
[knowledge base](knowledge-bases.md) was built with them.

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

## Slide images from the knowledge base

A knowledge base can carry the course's slides **as pictures**, not only as
text. Where it does, the assistant can show you one in its answer instead of
describing it. Just ask:

- *"Show me that slide."*
- *"Is there a picture of the figure they're pointing at?"*
- *"Show me the architecture diagram from lecture 5."*

They are whole slides, usually rendered from the course's own deck at about 1400
pixels wide — readable down to the tick labels on a chart and the citation in
the footer — and stored in the repository next to the text of the slide they
came from. Some knowledge bases use figures the course itself published instead
of rendering the deck. Either way the assistant shows the picture and still says
which slide it is, so you can go and read the rest of that slide.

### When this is the thing you actually want

**Sometimes the recording cannot show you the slide.** Lecture decks routinely
reproduce a figure from a paper or a textbook, and permission to use that figure
in a lecture hall is not permission to publish it on YouTube. Where the rights
could not be cleared, the upload blanks the slide, blurs the figure, or holds on
the lecturer while they talk through something you cannot see. The audio explains
a figure that is not on your screen.

A knowledge base is built from the deck rather than from the video, so when it
has slide images the figure is usually still there. Ask for it, and you get the
slide the room saw.

The same move works when the slide *is* on screen but unusable — a dense table
filmed from the back of the hall, a chart that falls apart at low bitrate, a
whiteboard the camera never quite frames. The rendered slide is sharper than any
frame of the video, because it never went through a camera.

### What to expect

- **Not every course has them.** Slide images are an opt-in part of a build —
  they are the one part that copies course material into the repository rather
  than linking to it, so whoever builds a knowledge base decides deliberately.
  Stanford's CS336 knowledge base carries 373 of them across 14 lectures, and
  others carry none. If a course has none, the assistant will say so rather
  than inventing a link.
- **Not every slide has one, even in a course that has them.** Title cards,
  section dividers and pure-text bullets are deliberately not rendered, and
  neither are tables the knowledge base already reproduces cell by cell. The
  assistant is told never to guess an image's address from the pattern of
  another one, so it will tell you a slide has no picture rather than hand you
  a broken link.
- **For numbers, trust what it quotes over what it shows.** The text of a slide
  is transcribed from the deck at high resolution, so a figure read out of the
  written record is more reliable than one squinted off the picture. The right
  answer usually quotes the table and shows the slide.
- **Only knowledge-base images can be displayed.** The chat renders images from
  the GitHub host that knowledge bases live on and silently drops every other
  source, so it cannot paste in an arbitrary picture it found on the web — it
  will give you the link instead. That restriction is deliberate: a remote image
  in an answer is a URL the model chose, and a knowledge base is a fixed set of
  files somebody published on purpose.

## Limits

These caps are on images **you send**. A slide the assistant shows you is a link
in its answer, so it does not use one up.

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
an image to a model without vision will not work. This applies to images you
send; a model with no vision can still *show* you a slide from the knowledge
base, since that is a link rather than something it has to look at.

## Related pages

- [The study chat](study-chat.md)
- [Asking good questions](asking-good-questions.md)
- [Knowledge bases](knowledge-bases.md)
- [Limits and caps](limits-and-caps.md)
