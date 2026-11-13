---
name: blog
description: Put a post on the person's Propaganda blog, answer the blog's questions about a post, or edit a post there. Use when they say "blog about this", "write about this", "put this on the blog", "post this to <collection>", "check Propaganda" or ask to change a post on their blog; offer once when a conversation has produced something worth publishing.
---

# Blog about this

Propaganda is the person's company blog and its agents. The Propaganda connector sends material there: Propaganda drafts the post from it in the blog's voice, and a reviewer sees it before anything is published. Nothing you send goes live on its own.

## When to act

- **Explicit.** "Blog about this", "blog about it", "write about this", "put this on the blog", "post this to <collection>": do it.
- **Implicit.** The conversation has produced a finding, a method, a result or an argument that reads like a post, and nobody asked for one: offer once, in one line ("Want this on the blog, in Research?"). Yes means act; no holds for the rest of the conversation.
- Never for private material, a draft the person is still deciding on, or anything they said stays internal.

## Send a post

0. If the Propaganda tools (`list_collections`, `assign_post`) aren't available, the connector isn't connected yet. Say so in one line ("Connect Propaganda first: Settings, Connectors, Propaganda, Connect") and stop. Never write the post yourself instead.
1. Call `list_collections` the first time in a conversation. Pick the collection whose description and rules fit; when none plainly does, use the one the person named or ask once with the names.
2. Prepare one Markdown document: the post as it would be written if you can (the blog's voice, from the collection's rules; the person's facts and words, their argument in their order), else the notes, transcript or findings as they are, with a title. Images and PDFs the post needs go as `assets`: a public URL, or the bytes in base64 with their kind (`image` or `pdf`).
   - When they say to keep it as is ("keep it", "don't rewrite it", "post it as written", "use my text"), send their text unchanged with `keep: true` and a `subtitle`: it goes on the blog word for word, to review, and isn't redrafted. Tables go as Markdown tables; place an image with `![alt](its asset name)`.
   - Put what the post stands on in `material`: sources (a link and the passage used), data (Markdown tables), notes (what you know that the post doesn't say). The blog's reviewer reads it.
   - Give `return_to` a label the person would recognise this conversation by.
3. Call `assign_post`.
4. Tell the person in one line where it went: the collection and the link the tool returned. Then stop: drafting and review take it from there.

## Questions back

While Propaganda drafts a post you sent, it may need something only this conversation knows. A tool result then says questions are waiting. Call `open_questions` and answer each with `answer_question`, from this conversation and the material, in a few sentences. If you don't know, say so in the answer. When the person says "check Propaganda", call `open_questions`.

## Edit a post

Only when the person asks for a change to a post on their blog: call `get_post`, edit the Markdown, and send the whole post back with `add_version`, the version `get_post` gave, and a one-line message saying what changed. It becomes the post's next version at once and the previous text stays in its history. Readers see it only after the person republishes the post in Propaganda. If the tool says the post changed since you read it, read it again and redo the edit.
