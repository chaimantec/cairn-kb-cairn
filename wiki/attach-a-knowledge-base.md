# Attaching a knowledge base to a course

If a [knowledge base](knowledge-bases.md) already exists for a course, pointing
Cairn at it takes about a minute.

## How

1. Open the course from the **Courses** tab.
2. Edit it.
3. Put the repository URL in **Knowledge base URL**, in the form
   `https://github.com/owner/repo`.
4. Save.

That is all. The [study chat](study-chat.md) picks it up on the next
conversation, and the knowledge-base tools appear in its toolset.

## Who can do it

**The person who created the catalog entry.** The catalog entry is shared, so
the knowledge base URL is shared too — attaching one changes what every enrolled
learner's chat reads.

If you are not the creator and a course should have one, ask whoever added it.
The assistant itself will tell learners this when a course has no knowledge base
configured: the course creator can add one in the course's edit dialog.

## Requirements for the repo

- **Public.** The chat fetches over unauthenticated GitHub URLs. A private repo
  produces the same result as no knowledge base at all.
- **`INDEX.md` at the root.** That is the entry point the assistant reads first,
  and it is where it learns what else exists.
- **Relative links between pages.** That is how it navigates.

The full contract is in [knowledge base repo layout](kb-repo-layout.md). A
repository that does not follow it will be read, but badly.

## Checking that it worked

Play a lecture from that course, open **Live → Chat**, and ask something only
the course materials would answer — "what does the index say this course
covers?" is a fair first test. The tool chips in the transcript should show a
`kb_read` of `INDEX.md`. If they do not, see [troubleshooting](troubleshooting.md).

## Pointing at someone else's knowledge base

You can attach any public repo that follows the layout, including one you did
not build. It does not have to live under your account.

## Related pages

- [Knowledge bases](knowledge-bases.md)
- [Building a knowledge base](building-a-knowledge-base.md)
- [The catalog](catalog.md)
