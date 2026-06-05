# Documentation project instructions

## About this project

- This is the public Kao customer documentation site built on [Mintlify](https://mintlify.com).
- Pages are MDX files with YAML frontmatter.
- Configuration lives in `docs.json`.
- Run `mint dev` to preview locally.
- Run `mint broken-links` to check links.

## Terminology

- Use "Kao" for the product name.
- Use "hosted Kao Bot" for the first-party bot path.
- Use "Bring Your Own Bot" or "BYOB" for user-owned Discord bot setup.
- Use "emote" when referring to imported source assets and "emoji" when referring to Discord server emoji slots or Discord UI.
- Use "server" for Discord guilds in customer-facing copy.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Prefer practical setup steps and troubleshooting tables over marketing copy.
- Follow `DOCUMENTATION_SPEC.md` when adding or revising public docs pages.

## Content boundaries

- This repository is public. Do not copy internal implementation notes, admin runbooks, security deliverables, Superpowers plans/specs, or source-code-derived secrets into it.
- Customer-facing setup, feature, billing, support, changelog, and troubleshooting docs belong here.
- Internal docs stay in the app repository under `dev-docs/`, `deliverables/`, `workspace/`, or other private paths.
