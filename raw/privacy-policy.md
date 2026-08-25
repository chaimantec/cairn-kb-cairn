---
title: Cairn Privacy Policy (verbatim)
source: https://cairnstudy.com/privacy.html
last_updated_by_cairn: 2026-08-25
copied: 2026-08-26
---

> Verbatim copy of the published policy. The page at cairnstudy.com is
> authoritative; if the two disagree, that one wins.

# Privacy Policy

**Last updated:** August 25, 2026

Cairn is a Chrome extension that helps people finish university lecture courses on YouTube. This policy explains what data Cairn collects, where it's stored, and what we do (and don't do) with it.

The plain version: Cairn collects the minimum needed to make the extension work. There is no advertising, no analytics, and no third-party tracking.

---

## Who runs Cairn

Cairn is an independent side project. It is not affiliated with YouTube, Google, Stanford, MIT, or any other organization.

For privacy or other questions: hello@cairnstudy.com

---

## Without an account (guest mode)

Cairn works without signing in. In this mode:

- Your course list, watch progress, and personal notes are stored only in your browser, using Chrome's built-in extension storage. They are not sent to Cairn's servers.
- The extension reads YouTube pages you are already viewing in order to detect which video is playing and track your progress against courses you have added. It does not read pages outside YouTube.

Some operations require contacting Cairn's servers even in guest mode:

- **Adding a course:** when you paste a YouTube playlist URL, Cairn's server fetches the playlist's public metadata (title, video count, lecture titles, durations) so it can be tracked.
- **Browsing the public course catalog:** the catalog is shared across all users, so loading it is a server request.
- **Loading lecture-level public data:** ratings and public comments on a lecture are loaded from the server when you view that lecture.

For these requests, our hosting provider (Cloudflare) handles standard server logging for security and abuse prevention. See Cloudflare's privacy policy for details on what they log. Cairn itself does not associate these requests with any identity, since you don't have one. No cookies are set, no fingerprinting is performed, no tracking IDs are assigned by Cairn.

You can clear all guest data at any time by uninstalling the extension or clearing extension data in Chrome's settings.

---

## With an account (signed in)

If you sign in to access community features (posting public comments, rating lectures or courses, liking comments, contributing to the catalog), Cairn creates an account on its servers. The account is created using Google sign-in.

### What Cairn requests from Google

Cairn requests only the `openid` scope from Google. This means Cairn receives:

- A unique opaque identifier for your Google account (called a `sub`), which Cairn uses to recognize you on subsequent sign-ins.

That's it. Cairn does **not** request or receive:

- Your email address
- Your name
- Your profile picture
- Any access to your YouTube account, watch history, subscriptions, comments, or any other Google service
- Any access to other Google APIs

### What Cairn stores about your account

When you first sign in, Cairn creates a record with:

- An internal account ID (a random UUID, not visible to other users)
- The Google `sub` identifier, used to recognize you on future sign-ins
- An auto-generated nickname (e.g., "Forest Walker"), which you can change in settings
- The timestamp of account creation and most recent sign-in

Cairn does not store your email address, name, or profile picture. Cairn cannot send you email, because Cairn does not know your email address.

### What Cairn syncs across your devices

When you are signed in, the following data is stored on Cairn's servers and synced to any browser where you sign in:

- Your enrolled courses
- Your watch progress on lectures within those courses
- Your personal comments (notes you marked as Personal)
- Your public comments (notes you marked as Public)
- Your lecture and course ratings
- Your nickname

This data is associated with your account and is visible only to you, except for the public-by-design data described next.

### What is shared publicly when you opt in

The following data is publicly visible to other Cairn users when you choose to share it:

- **Public comments.** When you post a comment with the Public toggle, it becomes visible to other users on the same lecture, attributed to your nickname.
- **Likes on public comments.** When you like a public comment, it adds to that comment's like count. Your individual like is associated with your account internally (to prevent double-liking) but is not publicly attributed to you.
- **Catalog contributions.** When you add a new course to the catalog, the catalog entry is attributed to your nickname.
- **Lecture and course ratings.** Your ratings (usefulness and difficulty) contribute to public aggregate scores. Your individual rating is not displayed to others alongside your nickname.

You can switch a comment from Public back to Personal at any time, which removes it from public view.

### AI study chat

The AI chat is optional and off until you enable it by saving your own API keys. It requires an account.

**Your API keys.** Cairn stores the provider API keys you enter (DeepSeek, OpenRouter, Tavily) on its servers, encrypted at rest, associated with your account. Once saved, a key is never sent back to your browser and is never written to your device's storage — Cairn uses it server-side to make the request on your behalf. You can remove a key at any time in Settings; removing it deletes it from Cairn's database. Deleting your account deletes your keys.

**Your conversations are stored only in your browser,** in extension local storage. They do not sync between browsers and are not recoverable if you clear the extension's data. They are deliberately not tied to your account: they survive signing out, and if you sign in with a different account on the same device, Cairn asks whether to keep or clear them.

**What the assistant remembers.** If you ask the assistant to remember something about how you like it to answer ("keep answers to a short paragraph"), it saves a brief note. These notes are stored **in your browser** alongside your conversations, never on Cairn's servers, and are capped at 50. Unlike a conversation, they apply across all your chats, and they are sent to the AI provider with every message so the assistant can follow them. You can ask the assistant to change or forget any of them at any time, and clearing the extension's data removes them all.

**Where your messages go.** The AI chat does not run on the same infrastructure as the rest of Cairn. The conversation itself is handled by **Cairn's own chat server** — a virtual private server that Cairn rents and administers directly, in the same Asia Pacific region as the rest of Cairn's infrastructure. Everything the assistant does happens there: reading your message, deciding when to look something up, calling the AI provider with your key, and streaming the answer back.

A message reaches that server through Cairn's ordinary API, which runs on Cloudflare and is the address your browser talks to. Its role in a chat is limited and mechanical: it checks that you are signed in, applies a rate limit, decrypts your stored provider key, and hands the request straight on. It passes your message through as an opaque stream — it does not read, parse, or store it, and no part of the conversation is processed there. Your browser never contacts the chat server directly; Cairn's API is the only client permitted to reach it, and it authenticates with a shared secret.

Neither server retains anything. Your message and the conversation it belongs to exist in server memory only for as long as the answer takes, and are never written to Cairn's database, to disk, or to logs. The chat server keeps no access log of its own, so once an answer has been delivered a chat leaves no record on it at all.

Because your conversation history lives in your browser, your browser sends the earlier messages of the conversation along with each new one so the assistant has context.

What is sent to the AI provider: what you type, the earlier messages in that conversation, your saved memory notes, and the current course title, lecture title, and your position in the video. If web search is enabled, your search queries — and the addresses of any pages the assistant decides to open in order to answer — go to Tavily, which runs the search and retrieves the page. If the course has a knowledge base, Cairn's chat server fetches its public files from GitHub. These providers handle that data under their own privacy policies, listed under "Third parties" below.

**Why it works this way.** Routing through Cairn at all is what lets your API key stay off your device entirely. The chat then runs on a separate server for a plainer reason: a full conversation takes more sustained computation than Cairn's Cloudflare tier allows, and answers were being cut off partway through. The trade in both cases is that your messages transit Cairn's servers rather than going straight to the provider. Cairn does not read, store, or train on them.

### What Cairn never asks for

- Real name
- Email
- Phone number
- Address
- Profile photo
- Payment information
- Date of birth
- Access to your YouTube account or any other Google service

---

## Data we do not collect

Cairn does **not** collect, store, or transmit:

- Your YouTube watch history (Cairn only knows about videos in courses you've enrolled in)
- Your activity on YouTube outside of tracked courses
- Your activity on websites other than YouTube (the extension only reads YouTube pages)
- Telemetry, analytics, or usage metrics of any kind
- Crash reports
- Any information about your device beyond what is required for HTTPS requests

Cairn does not use Google Analytics, Mixpanel, Segment, or any other analytics service. Cairn does not embed any third-party trackers, advertising networks, or marketing pixels.

---

## Cookies and similar technologies

Cairn does not use cookies in the extension UI.

When you sign in, Cairn issues a session token stored in Chrome's extension local storage (not as a browser cookie). This token is sent with API requests to identify your session. It expires after 30 days.

Cairn's landing page (`cairnstudy.com`) is a static HTML page served by Cloudflare Pages. It does not set any cookies and contains no JavaScript trackers.

---

## Third parties

Cairn uses the following third-party services to operate. Each has its own privacy policy:

- **Cloudflare** hosts the API, database, and landing page. The AI chat does not run on Cloudflare; Cloudflare only relays chat messages, unread, to Cairn's own chat server. Cloudflare handles standard server logging for security and abuse prevention. See Cloudflare's privacy policy at https://www.cloudflare.com/privacypolicy/ for details on what they log.
- **Google (Sign-In)** is used for authentication. Google's handling of sign-in flows is governed by Google's privacy policy at https://policies.google.com/privacy. As described above, Cairn requests only the `openid` scope.
- **YouTube.** Cairn reads YouTube pages in your browser to detect playback progress. Cairn does not interact with YouTube's API. Your interactions with YouTube itself (watching videos, viewing comments, etc.) are governed by YouTube's privacy policy.
- **Cairn's chat server host.** The AI chat runs on a virtual private server that Cairn rents from a commercial hosting company and administers itself, in the Asia Pacific region. This is the machine that talks to the AI providers on your behalf. The hosting company is not a processor of your data in the usual sense — it is not sent anything and nothing from your chats is written to that machine — but it does operate the underlying hardware, as is true of any rented server.

The following are used **only if you turn on the AI study chat** and save a key for them. Cairn's chat server contacts them on your behalf, using your key, and does not retain the request or the response.

- **DeepSeek** — https://platform.deepseek.com/downloads/DeepSeek%20Privacy%20Policy.html
- **OpenRouter** — https://openrouter.ai/privacy. Note that OpenRouter forwards your messages to whichever underlying model provider you select, under that provider's terms.
- **Tavily** (web search, optional) — https://tavily.com/privacy
- **GitHub** — when a course has a knowledge base, its public files are fetched from GitHub. See https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement

Cairn does not share your account data with any third party for marketing, advertising, or analytics purposes.

---

## How to delete your data

You can delete your data at any time:

- **Delete your account.** In the extension settings, choose "Delete account." This permanently removes your account record, all synced personal data (progress, personal comments, enrollments), all your public comments, all your ratings, all your likes, and your saved AI provider keys. Catalog entries you contributed remain in the catalog (so other users who rely on them are not affected) but are reassigned to an anonymous proxy account, with no link to your former identity.
- **Delete local data only.** Uninstall the extension or clear its data in Chrome's settings. This is also what deletes your AI chat conversations and anything the assistant has been asked to remember, since both are stored only in the browser.
- **Make the assistant forget something.** Ask it to forget a specific memory in the chat, or clear the extension's data to remove all of them.
- **Remove an AI provider key.** In settings, under AI chat, choose "Remove" for that provider. The key is deleted from Cairn's database.
- **Make specific public comments private.** Switch them to Personal in the comment menu. They are removed from public view.

Deletion is immediate and irreversible.

---

## Data security

Cairn uses HTTPS for all API requests. Account session tokens are stored in Chrome's extension local storage, accessible only to the Cairn extension. Server-side data is stored in Cloudflare D1 (a managed database service) and Cloudflare KV (managed key-value storage), with access restricted to the Cairn API.

AI provider keys are encrypted (AES-GCM) before being written to the database, and are never transmitted back to your browser. Be aware of the limits of that protection. The decryption key is held by the same API that reads the database, so this defends against a database-only leak, not against a full compromise of Cairn's servers. And answering a chat message requires the key in plaintext, so for the duration of that one request it exists decrypted in the memory of both Cairn's API and Cairn's chat server. It is not written to disk in either place.

Cairn's chat server accepts connections only over HTTPS and only from Cairn's API, which authenticates with a shared secret. The agent process is bound to that machine's loopback interface rather than a public one, runs in a container as an unprivileged user, and every request path except the chat endpoints is refused at the edge before it reaches the process.

This is a small project, not a security-hardened enterprise product. We follow reasonable practices but cannot guarantee against all forms of compromise. Do not rely on Cairn to protect highly sensitive information — your study notes are not the same threat model as your bank.

---

## Children

Cairn is not directed at children under 13. Cairn does not knowingly collect data from children under 13.

Cairn does not request a date of birth and has no way to actively verify a user's age. If you are a parent or guardian who believes a child under 13 has signed in to Cairn, contact hello@cairnstudy.com. We will guide you through deleting the account.

---

## International users

Cairn's API, database, and AI chat server are all hosted in the Asia Pacific region. By using Cairn, you consent to your data being processed in this region, regardless of where you are located.

If you are in the EU, UK, or California and wish to exercise data-protection rights (access, correction, deletion, portability), email hello@cairnstudy.com. We will respond within 30 days.

---

## Changes to this policy

If this policy changes in a way that materially affects how your data is used, we will update the "Last updated" date at the top of this page. For significant changes affecting signed-in users, we will also display a notice in the extension on next sign-in.

This is a small project; updates are likely to be infrequent.

---

## Contact

hello@cairnstudy.com
