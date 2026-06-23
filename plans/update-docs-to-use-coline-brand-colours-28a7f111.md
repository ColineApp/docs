# Kairo Plan

# Findings

- This repository is primarily MDX content and navigation, not the actual styled docs application.
  - `README.md` states: “The docs app at apps/docs mounts this directory and builds with Fumadocs.” (`README.md`)
  - There are no CSS, Tailwind config, theme, or component files in this repo root.

- The current repo contains documentation copy only:
  - Landing page content is in `index.mdx`.
  - Product docs are individual MDX pages such as `docs.mdx`, `notes.mdx`, `tasks.mdx`, etc.
  - Navigation is driven by `meta.json`.

- There are a few content-level references to legacy color names that conflict with the requested Meridian-first branding system:
  - `developers/getting-started/first-steps.mdx:51-55`
    - Example uses `color: 'blue'`
  - `sdk/typescript.mdx:158`
    - Comment lists color names including `blue`, `purple`, `pink`, etc.
  - `notes.mdx:227-228`
    - Mentions note colors “Blue” and “Purple”

- No centralized design-token implementation exists in this repository:
  - Searches did not reveal theme variables, Tailwind tokens, CSS custom properties, or brand palette definitions.
  - This strongly suggests the actual visual branding work must happen in the external `apps/docs` application referenced in `README.md`.

# Plan

1. Update the docs application theme layer in the external `apps/docs` project
   - Files likely to change there:
     - global CSS/theme token files
     - Tailwind config
     - Fumadocs theme config
     - shared layout/components
   - Add the full Coline token system:
     - Meridian scale
     - Ember scale
     - Obsidian neutrals
     - Kairo opal colors
     - semantic colors
   - Set Meridian as the default primary/accent color.
   - Replace any existing generic blue/purple SaaS palette.

2. Apply the new brand rules to docs UI surfaces in the external docs app
   - Update:
     - primary buttons
     - links
     - focus rings
     - selected navigation states
     - cards
     - code-callout accents
     - hero sections
   - Ensure:
     - regular docs UI stays dark/neutral with restrained Meridian accents
     - Ember is only used for marketing/hero atmospheres
     - Kairo gradients only appear in Kairo-specific surfaces

3. Update homepage/landing visuals in `index.mdx`
   - Review the introduction and hero content for compatibility with the new branding direction.
   - If the Fumadocs setup supports MDX components/themes:
     - introduce Meridian terminology
     - optionally add branded callouts/cards matching the new palette
   - Keep the page visually restrained per the “dark infrastructure” guidance.

4. Clean up content references to old/generic color naming
   - Update:
     - `developers/getting-started/first-steps.mdx`
     - `sdk/typescript.mdx`
     - `notes.mdx`
   - Replace generic examples like `"blue"` with `"meridian"` where appropriate.
   - Ensure docs examples reflect the new default accent philosophy.

5. Add a canonical brand/color reference page
   - Create a dedicated MDX page documenting:
     - Meridian
     - Ember
     - Kairo opal palette
     - semantic colors
     - usage rules
   - Add it to `meta.json` navigation if desired.
   - This prevents future drift away from the branding system.

6. Audit gradients and decorative color usage in the external docs app
   - Remove:
     - rainbow gradients
     - purple-heavy AI styling
     - excessive decorative color
   - Replace with:
     - Daybreak gradient for marketing/hero contexts only
     - neutral graphite UI elsewhere

# Risks / open questions

- The actual styling system is not present in this repository.
  - The implementation almost certainly belongs in the separate `apps/docs` project referenced by `README.md`.
  - Without access to that repository, exact file targets for CSS/theme changes cannot be identified.

- It is unclear whether:
  - the docs app uses Tailwind, CSS variables, shadcn/ui, or Fumadocs theme tokens
  - branding is controlled centrally or component-by-component

- Some content pages intentionally describe user-selectable colors (`notes.mdx`, SDK examples).
  - A product decision is needed on whether those examples should:
    - remain generic,
    - explicitly include `meridian`,
    - or be rewritten around “theme accents” terminology.
