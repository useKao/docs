# Kao documentation standard

This is the source of truth for adding or revising public Kao customer docs.

The standard is based on the current Mintlify docs pattern, TicketCord's grouped welcome page, and Kao's product model. It keeps the public docs practical, navigable, and consistent as the product grows.

## What good looks like

Every page should help a customer complete one job without needing app-internal context.

- Start with the user's goal, not the feature name.
- Explain the fastest recommended path first.
- Show prerequisites before steps.
- Use clear steps for setup or irreversible actions.
- Add troubleshooting for common failure states.
- End with next actions that keep the user moving.
- Keep internal implementation notes, security deliverables, runbooks, secrets, and private architecture out of this repo.

## Information architecture

Use this structure unless a new product area clearly needs a new group.

| Area | Purpose | Page examples |
|------|---------|---------------|
| Start here | First-session orientation and setup | Introduction, Quickstart, Overview |
| Bot setup | Server access, hosted Kao Bot, and BYOB | Bot system, Multiple bots, Bot commands |
| Emoji workflows | Importing, managing, saving, and creating emotes | Importing emotes, Managing emojis, Collections, Emote Creator |
| Automation | Repeated or scheduled emoji operations | Backups, Rotations, Sync groups, Activity log |
| Account and settings | Billing, privacy, account, and server preferences | Server settings, Billing, Account management |
| Resources | Help, updates, and reference answers | FAQ, Troubleshooting, Changelog |

The homepage should act as a map. It must include:

- Two setup paths: hosted Kao Bot and Bring Your Own Bot.
- Core workflow cards grouped by job.
- A "Find the right guide" table for common goals.
- Product model links for users who need concepts before action.
- Support and changelog links.

## Page depth rubric

Use this checklist before publishing a page.

| Requirement | Standard |
|-------------|----------|
| Frontmatter | `title` and `description` are present, specific, and customer-facing. |
| Opening | The first paragraph states what the page helps the user do. |
| Prerequisites | Setup, permission, plan, or Discord requirements appear before steps. |
| Steps | Tasks use numbered lists with UI labels in bold. |
| Decisions | Tradeoffs use a table, cards, or tabs instead of long prose. |
| Warnings | Risky or irreversible actions use `<Warning>`. Helpful notes use `<Info>` or `<Tip>`. |
| Troubleshooting | Common errors include symptom, likely cause, and fix. |
| Next steps | The page ends with 2-4 relevant links, usually in cards. |
| Terminology | Use the approved Kao terms from `AGENTS.md`. |

## Recommended page templates

### Setup guide

Use for onboarding, bot setup, billing setup, and first-use flows.

```mdx
---
title: Page title
description: One-sentence outcome.
---

## Overview

State the user outcome and recommended default.

## Prerequisites

- Requirement one
- Requirement two

## Step 1: Verb phrase

1. Click **UI label**.
2. Choose **Option**.
3. Confirm the result.

<Info>
Explain a useful detail that prevents confusion.
</Info>

## Troubleshooting

| Issue | Cause | Fix |
|-------|-------|-----|
| Symptom | Likely cause | Action the user can take |

## Next steps

<CardGrid>
  <Card title="Related guide" href="/path">
    Why this guide is useful next.
  </Card>
</CardGrid>
```

### Feature guide

Use for importing, managing, backups, rotations, sync groups, collections, and Emote Creator.

```mdx
---
title: Feature name
description: Practical outcome for the feature.
---

## Overview

Explain when to use the feature.

## Before you begin

List permissions, bot requirements, plan limits, and source data.

## Main workflow

Use numbered steps for the most common successful path.

## Options

Use a table for settings and their effects.

## Best practices

- Practical recommendation
- Practical recommendation

## Troubleshooting

Use short issue sections or a table.

## Next steps

Link to adjacent workflows.
```

### Troubleshooting guide

Use when the reader starts from a problem.

```mdx
---
title: Troubleshooting topic
description: Fix common problems with a specific area.
---

## Problem category

### Symptom users would search for

What it usually means.

1. First fix.
2. Second fix.
3. When to contact support.
```

## Layout standards

- Use `##` for major sections and `###` for specific issues or options.
- Prefer `<Columns>` plus `<Card>` for homepage and section landing layouts.
- Prefer `<CardGrid>` for compact "Next steps" blocks at the end of standard pages.
- Use tables for comparisons, settings, limits, statuses, and troubleshooting.
- Use numbered lists for ordered tasks.
- Use bullets only when order does not matter.
- Avoid decorative sections that do not route users to action.
- Keep the global footer minimal. Use `footer.socials` for small links back to the main Kao site and Discord instead of multi-column footer navigation.
- Use Kao-owned favicon and logo assets from this repository. Do not use Mintlify default branding assets.

## Copy standards

- Use active voice and second person.
- Keep one idea per sentence.
- Use "Kao" for the product.
- Use "hosted Kao Bot" for the first-party bot path.
- Use "Bring Your Own Bot" or "BYOB" for user-owned Discord bot setup.
- Use "emote" for imported source assets.
- Use "emoji" for Discord server emoji slots and Discord UI.
- Use "server" for Discord guilds.
- Bold UI labels: Click **Settings**.
- Use code formatting for file names, commands, paths, and code references.

## Maintenance checklist

Before opening a docs PR:

- Run `mint broken-links` from this repository.
- Search for outdated product names or forbidden internal terms.
- Check that every changed page has next-step links.
- Check that public docs do not reveal internal runbooks, security findings, source-code-derived secrets, or private architecture.
- If a product change affects setup, billing, permissions, or Discord behavior, update troubleshooting and FAQ in the same change.
