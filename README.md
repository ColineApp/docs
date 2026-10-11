---
title: Coline Docs
description: Coline documentation.
---

# Coline Docs

MDX pages and Fumadocs navigation for [docs.coline.app](https://docs.coline.app).

## Structure

```
index.mdx              Introduction
getting-started/       Account, workspace, navigation, desktop app
plans.mdx              Plans and credits
home.mdx … apps.mdx    One page per product area (Messages, Mail, Calendar, Drive, …)
kairo/                 Kairo, Crew, memory, routines, computer, customize
workspace/             Workspaces, permissions and sharing, import
developers.mdx         Overview of the developer surfaces
authentication/        API keys, OAuth, scopes, security
api/                   REST API, endpoint reference, errors, rate limits, MCP, Tab
sdk/                   Building apps with @colineapp/sdk
meta.json              Navigation order
```

## Editing

- Pages are MDX; only `.mdx` files become pages. Navigation is `meta.json`.
- Write plain, factual copy. Don't name AI model providers.
- Link between pages with root paths, such as `/kairo/crew`, not `/docs/...`.
- When a page moves, add a redirect in `apps/docs/next.config.ts` (`MOVED_PAGES`).
- The docs app at `apps/docs` mounts this directory and builds with Fumadocs. Every page is also served as Markdown at `/{slug}.md`, in `/llms.txt` and in `/llms-full.txt`.
- `brand.mdx` is the internal brand system reference. It's not in the navigation.

## License

MIT.
