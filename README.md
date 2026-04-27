---
title: Coline Docs
description: Coline documentation.
---

# Coline Docs

MDX pages and Fumadocs navigation for [docs.coline.app](https://docs.coline.app).

## Structure

```
index.mdx              Landing page
meta.json              Top-level nav order
api/                   Public API & MCP
authentication/        API keys, OAuth, scopes
developers/            Developer onboarding
getting-started/       Quickstart guides
integrations/          Apps & webhooks
kairo/                 Kairo AI assistant
platform/              Platform concepts
sdk/                   SDK guides & examples
```

## Editing

- Pages are MDX. Navigation is `meta.json`.
- The docs app at `apps/docs` mounts this directory and builds with Fumadocs.

## License

MIT.
