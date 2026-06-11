# Postproxy

One API for social media workflows.

Postproxy lets you publish, schedule, track, and manage engagement across social platforms without building every platform integration yourself.

Use it to add social publishing, comments, DMs, reviews, analytics, and automation workflows to your product, agent, or internal tool.

## Links

* Website: https://postproxy.dev
* Documentation: https://postproxy.dev/getting-started/overview/
* API base URL: https://api.postproxy.dev
* App: https://app.postproxy.dev

## What you can build with Postproxy

* Publish posts across multiple social platforms
* Schedule posts and manage publishing queues
* Send text, images, videos, stories, reels, pins, and platform-specific formats
* Get clear per-platform publishing results
* Handle retries, validation, and platform-specific errors
* Read and reply to comments
* Read and send direct messages
* Manage reviews where supported
* Pull post and profile insights
* Import historical posts
* Use webhooks for publishing and engagement events
* Scope access by profile groups for brands, clients, or projects

## Supported platforms

Postproxy supports major social platforms, including:

* Facebook
* Instagram
* TikTok
* LinkedIn
* YouTube
* X / Twitter
* Threads
* Pinterest
* Bluesky
* Telegram
* Google Business

Reddit support is coming soon.

Platform rules change because platforms apparently enjoy making developers suffer. Postproxy handles that layer so your product can keep a cleaner API surface.

## API

Postproxy uses a single API surface for social publishing and engagement.

Typical flow:

1. Create an API key
2. Connect social profiles
3. Send one request to publish, schedule, or manage engagement
4. Get per-platform results back

### Example request

```bash
curl -X POST "https://api.postproxy.dev/api/posts" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "post": {
      "body": "Hello from Postproxy"
    },
    "profiles": ["linkedin", "twitter", "threads"],
    "media": ["https://example.com/image.jpg"]
  }'
```

## Core concepts

### Profile

A connected social media account that you can post content to. Each profile represents an authenticated connection to a specific platform.

### Post

A piece of content published through one or more profiles. It can include text, images, videos, or platform-specific parameters.

### Profile Group

A collection of profiles grouped for organization and access control. Use profile groups to separate brands, clients, projects, regions, or customer workspaces.

API keys can be scoped to specific profile groups.

### Comment

A comment on one of your published posts. Comments can be synced from the platform or created through the API.

You can list, reply to, hide, and like comments where supported.

### Chat & Message

A chat is a 1:1 direct-message conversation between one of your profiles and a participant.

A message is an inbound or outbound item inside that chat.

Direct messages are supported on Facebook Messenger, Instagram, Telegram, and Bluesky.

## Media handling

When you create a post with media, provide URLs to your images or videos.

Postproxy downloads and processes the media, then uploads it to each platform according to its requirements.

Each platform has its own constraints for file size, format, dimensions, duration, and content type. Postproxy handles the platform-specific upload flow and returns explicit results.

## Rate limits and retries

Social networks have rate limits, quotas, transient failures, and platform-specific edge cases.

Postproxy handles rate limits and retries where possible. Your application does not need to implement separate retry logic for every social platform.

## Integrations

Postproxy works with automation tools, AI agents, and workflow builders.

* Make: https://www.make.com/en/integrations/posptroxy
* Zapier: https://zapier.com/apps/postproxy/integrations
* n8n: https://n8n.io/integrations/postproxy/
* Needle: https://needle.app/resources/connectors/postproxy
* MCP server: https://github.com/postproxy/postproxy-mcp

Use Postproxy in Make scenarios, Zaps, n8n workflows, agent tools, backend jobs, and any system that can send an HTTP request.

## MCP

Postproxy MCP gives AI agents direct access to social media publishing and engagement actions.

Use it from Claude Code, Cursor, terminals, and other MCP clients.

Repository:

https://github.com/postproxy/postproxy-mcp

## Documentation

Start here:

* Overview: https://postproxy.dev/getting-started/overview/
* Posts API: https://postproxy.dev/reference/posts/
* Profiles API: https://postproxy.dev/reference/profiles/
* Profile Groups API: https://postproxy.dev/reference/profile-groups/
* Comments API: https://postproxy.dev/reference/comments/
* Direct Messages API: https://postproxy.dev/reference/direct-messages/
* Webhooks: https://postproxy.dev/reference/webhooks/
* Platforms: https://postproxy.dev/reference/platforms/
* SDKs: https://postproxy.dev/getting-started/sdks/

## Why Postproxy exists

Social media APIs are inconsistent, fragile, and full of tiny platform rules that only show up when something breaks.

Postproxy gives you one API layer for the full social workflow: publishing, engagement, analytics, automation, and operational visibility. Your product sends the intent and Postproxy deals with the platform-specific mess.
