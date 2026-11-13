# Propaganda for Claude

Say "blog about this" and Claude hands what you worked out to your Propaganda blog. The Writer drafts the post in your voice, in the collection that fits, and it waits in your pipeline for review. Nothing Claude sends is published on its own.

## What it does

- **Reads your collections.** Claude sees each collection's public description and the rules you wrote for posts in it, and files the post where it fits. When nothing fits plainly, it asks you.
- **Sends the material.** Your notes, findings or finished draft become the post's brief, with images placed in the post and PDFs attached for your reviewer. Say "keep it as written" and your text becomes the post word for word, still waiting for review.
- **Starts the draft.** The post appears in your Writing column, with your material under the Brief tab. You edit, approve and publish it in Propaganda.
- **Answers questions back.** While a post is being drafted, Propaganda may need a fact only your conversation has. Claude sees that the next time it uses the connector, or when you say "check Propaganda", and answers.
- **Edits a post when you ask.** Claude reads the post, changes it, and saves the result as the post's next version. The previous text stays in the post's history, and readers see the change only after you republish.

## Set it up

You need a Propaganda account and a blog you are a member of.

1. Add the plugin from Claude's directory, or in Claude Code:

   ```
   /plugin marketplace add Ghaith-Ayadi/propaganda-plugin
   /plugin install propaganda@propaganda
   ```

   Or add Propaganda as a custom connector in Claude with this address: `https://app.propaganda.pub/worker/v1/mcp`.
2. Press **Connect**. Propaganda opens in your browser: sign in with Google or with a code sent to your email, pick the blog Claude may use, and press **Allow**.
3. Say "blog about this" in any conversation.

Each connection is listed in Propaganda under Settings, Connections, Claude. Revoke it there and Claude loses access at once. Access also ends by itself if you leave the blog. A connection can send 20 posts an hour.

## Try it

- "Blog about this." (after working through a problem, an analysis or a decision in the conversation)
- "Put these findings on the blog, in Research."
- "Turn this call summary into a post for our Guides collection, and use the chart I attached."
- "Post this as written, don't rewrite it."
- "What collections does my blog have?"
- "In the post you just sent, change the second heading to a question."
- "Check Propaganda."

## Tools

The plugin adds one skill (`blog`, the instructions above in Claude's words) and one remote MCP server, `https://app.propaganda.pub/worker/v1/mcp`. It runs no code on your computer, has no hooks, and talks to no other address.

| Tool | What it does | Changes anything |
| --- | --- | --- |
| `list_collections` | The blog's visible collections, with their descriptions and post rules | No |
| `assign_post` | Adds a draft post with your material as its brief and starts the draft | Adds a post for review. Never publishes or deletes one |
| `open_questions` | Questions Propaganda has about posts this connection sent | No |
| `answer_question` | Sends Claude's answer to one of those questions | Records the answer. Changes no post |
| `get_post` | Reads one post of the blog: title, subtitle, Markdown and its version | No |
| `add_version` | Saves an edited post as its next version, only when you asked for the change | Replaces the post's working text. The previous text stays in its history, and nothing reaches readers until you republish |

## What goes where

Everything goes to Propaganda at `app.propaganda.pub`, over HTTPS, signed in with OAuth as you, for the one blog you allowed:

- What a tool call contains: the title, the Markdown, the material, the answer or the edited post.
- Images and PDFs, as bytes or as a public link. When you send a link, Propaganda's server downloads the file from it; the plugin downloads nothing itself.
- Nothing else: not your conversation, not your files, not your Claude memory.

## Privacy Policy

Propaganda receives what Claude sends through these tools (a title, the material, images, PDFs, answers and edits) and stores it with your blog, where the members of that blog can see it. We do not receive your Claude conversations, only what a tool call contains. Model calls that write the draft are logged so we can find and fix mistakes, and only our team can see that log. We don't sell your data, show ads, or train our own models on your content. Data is kept while your account exists, and backups for 30 days after that.

The full policy, covering collection, use, storage, sharing, retention and how to reach us, is at [propaganda.pub/privacy](https://propaganda.pub/privacy).

## Support

Write to [hello@propaganda.pub](mailto:hello@propaganda.pub).

## License

MIT: see [LICENSE](LICENSE).
