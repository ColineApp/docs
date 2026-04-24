# Coline Documentation

Public documentation content for [Coline](https://coline.app).

This repository contains the MDX pages and Fumadocs metadata used by the Coline
docs site. It intentionally does not include the Next.js docs application,
deployment configuration, environment files, or private workspace settings.

## Structure

- `index.mdx` - docs landing page
- `meta.json` - top-level navigation
- `api/` - public API and MCP docs
- `authentication/` - API keys, OAuth, scopes, and security
- `developers/` - developer onboarding
- `integrations/` - app and webhook guides
- `platform/` - Coline platform concepts
- `sdk/` - SDK guides and examples

## Editing

Edit pages as MDX and navigation as `meta.json`. The consuming docs app mounts
this repository at `apps/docs/content/docs` and builds it with Fumadocs.

Do not commit `.env` files, real API keys, private OAuth secrets, production
tokens, workspace exports, or deployment credentials.

## License

MIT.
