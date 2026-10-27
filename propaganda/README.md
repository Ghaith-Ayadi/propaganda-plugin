# Propaganda for Claude

Say "blog about this" and Claude hands what you worked out to your Propaganda blog. The Writer drafts the post in your voice, in the collection that fits, and it waits in your pipeline for review. Nothing Claude sends is published on its own.

## What it does

- **Reads your collections.** Claude sees each collection's public description and the rules you wrote for posts in it, and files the post where it fits. When nothing fits plainly, it asks you.
- **Sends the material.** Your notes, findings or finished draft become the post's brief, with images placed in the post and PDFs attached for your reviewer.
- **Starts the Writer.** The draft appears in your Writing column, with your material under the Brief tab. You edit, approve and publish it in Propaganda.

## Set it up

You need a Propaganda account and a blog you are a member of.

1. Install the plugin. In Claude Code:

   ```
   /plugin marketplace add Ghaith-Ayadi/propaganda-plugin
   /plugin install propaganda@propaganda
   ```

   Or add Propaganda as a custom connector in Claude with this address: `https://app.propaganda.pub/worker/v1/mcp`.
2. Press **Connect**. Propaganda opens in your browser: sign in with Google, pick the blog Claude may post to, and press **Allow**.
3. Say "blog about this" in any conversation.

Each connection is listed in Propaganda under Settings, Connections, Claude. Revoke it there and Claude loses access at once. Access also ends by itself if you leave the blog. A connection can send 20 posts an hour.

## Try it

- "Blog about this." (after working through a problem, an analysis or a decision in the conversation)
- "Put these findings on the blog, in Research."
- "Turn this call summary into a post for our Guides collection, and use the chart I attached."
- "What collections does my blog have?"

## Tools

| Tool | What it does | Changes anything |
| --- | --- | --- |
| `list_collections` | The blog's visible collections, with their descriptions and post rules | No |
| `assign_post` | Adds a draft post with your material as its brief and starts the Writer | Adds a draft for review. Never edits, publishes or deletes a post |

## Privacy Policy

Propaganda receives what Claude sends through these tools (a title, the material, images and PDFs) and stores it with your blog, where the members of that blog can see it. We do not receive your Claude conversations, only what a tool call contains. Model calls that write the draft are logged so we can find and fix mistakes, and only our team can see that log. We don't sell your data, show ads, or train our own models on your content. Data is kept while your account exists, and backups for 30 days after that.

The full policy, covering collection, use, storage, sharing, retention and how to reach us, is at [propaganda.pub/privacy](https://propaganda.pub/privacy).

## Support

Write to [hello@propaganda.pub](mailto:hello@propaganda.pub).

## License

MIT: see [LICENSE](LICENSE).
