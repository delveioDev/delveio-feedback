# DelveIO

[DelveIO](https://www.delveio.dev) is a leaderboard, stats tracker, and in-game addon for World of Warcraft Delves.

This repo is the public hub for bug reports, feature requests, and documentation about how DelveIO works.

## How It Works

1. You sign in on the website with your Battle.net account (OAuth)
2. We pull your character's delve completion data from Blizzard's official API
3. A score is computed based on your completions
4. Your character appears on the public leaderboard

Your data is re-synced whenever you manually sync from your profile, and all tracked characters are automatically refreshed once per day.

## What Data We Collect

When you sign in and sync a character, we make requests to Blizzard's official Battle.net API. Specifically:

- **Character profile**: name, realm, region, faction, race, class, spec, level, and avatar
- **Achievement statistics**: delve completion counts per delve and per tier (pulled from Blizzard's achievement/statistics tree)

**What we store:**

- Character name, realm, region, faction, race, class, active spec, role, level
- Per-delve completion counts and highest tier completed
- A computed delve score (see Scoring below)
- Your Battle.net account ID (to link characters to your account)
- An encrypted refresh token (to enable automatic daily re-syncs)

**What we do NOT store or access:**

- Your Battle.net password (OAuth never exposes this)
- Your email address
- Your friends list, guild roster, or chat logs
- Any personal information beyond what is listed above
- Payment information of any kind

## How Scoring Works

Your delve score is computed from four components:

- **Tier points**: higher tier completions are worth more points
- **Breadth bonus**: reward for completing a variety of different delves, not just the same one repeatedly
- **Volume bonus**: reward for total number of completions across all delves
- **Nemesis multiplier**: bonus for completing the hardest content (Torment's Rise)

The score is calculated once when your character syncs and stored in the database. The leaderboard sorts by this pre-computed score.

## The Addon

The DelveIO WoW addon provides an in-game overlay with delve-related information. More details on installation and usage coming soon.

## Roadmap

View planned features and improvements:

- [Open feature requests](../../issues?q=is%3Aissue+is%3Aopen+label%3Afeature)
- [Completed features](../../issues?q=is%3Aissue+is%3Aclosed+label%3Afeature)

## Report a Bug or Request a Feature

- [Open a new issue](../../issues/new/choose)
- [View all open issues](../../issues?q=is%3Aissue+is%3Aopen)

## Links

- Website: [delveio.dev](https://www.delveio.dev)
