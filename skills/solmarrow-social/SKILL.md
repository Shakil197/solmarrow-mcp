---
name: solmarrow-social
description: Draft, schedule and check social media posts across 19 networks through the SolMarrow MCP server. Use when the user wants to plan, write, schedule or review posts for X, LinkedIn, Facebook, Instagram, Threads, Bluesky, TikTok, YouTube, Pinterest, Telegram, Discord and more.
---

# SolMarrow social posting

Uses the SolMarrow MCP server (`https://mcp.solmarrow.com/mcp`, OAuth sign-in, free plan).

## When to use

- The user asks to write and schedule posts for one or more social networks.
- The user wants to see what is scheduled or how posts performed.

## Workflow

1. Call `list_workspaces`, then `list_accounts` for the chosen workspace. Never guess account ids.
2. Write the copy per network (length and tone differ). Confirm the text with the user.
3. If media is needed, call `upload_media_from_url` (or `create_media_upload` then `finish_media_upload`) and keep the media ids.
4. Call `create_post` as a draft, or schedule at least 5 minutes ahead. Times use ISO 8601 with an offset in the workspace time zone.
5. Call `get_post` or `list_posts` to confirm status per network. Use `get_analytics` for results.

## Rules

- SolMarrow does not publish instantly. Everything appears in the user's calendar first.
- Do not delete posts unless the user asks. `delete_post` removes drafts and scheduled posts only.
- SolMarrow is independent and not endorsed by any social network.
