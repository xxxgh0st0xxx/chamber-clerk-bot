# Codex Operating Instructions

Codex and future agents must follow these rules before making changes.

## Required reading order

1. Read `README.md`.
2. Read this file.
3. Read `.agents/coordination.yaml`.
4. Read relevant files in `docs/` before editing implementation files.

## Project identity

This repository supports the **Chamber Clerk Bot**, a Discord bot for a digital-first International Private Law Chamber.

The project is private-law only. It is not a state, government, public court, police authority, sovereign body, election system, taxation system, or public-law replacement.

## Doctrine preservation rules

Do not remove or weaken the following:

1. The Chamber only designs private law.
2. Chamber authority is voluntary, membership-based, and contract-based.
3. No Chamber rule overrides host-state law.
4. The Chamber appoints the Chief Arbitrator.
5. The Chief Arbitrator administers arbitration under Chamber rules.
6. Special Arbitration Review is the internal appeal/review mechanism.
7. Committee members may act as review arbiters only when appointed under the rules.
8. All adopted rules, motions, reports, and decisions are archived and versioned.

## Security rules

- Never commit secrets.
- Never hardcode Discord tokens.
- Never commit `.env`.
- Use `.env.example` only.
- Do not require Message Content Intent for MVP.
- Do not store sensitive arbitration evidence.
- Store only case metadata, procedural status, panel members, deadlines, and published summaries.
- Use role-based permissions for all administrative commands.

## Development workflow

- Work from a branch.
- Keep changes scoped to the issue.
- Open a pull request for review.
- Update `.agents/coordination.yaml` after meaningful work.
- Add an `agent_log` entry with date, actor, summary, files touched, and status.
- Do not mark anything complete unless it is implemented or clearly documented as future work.

## Communication style

When leaving notes for the owner or future agents:

- Be direct.
- Separate facts from assumptions.
- Flag blockers clearly.
- Do not invent legal claims.
- Keep public-law and sovereignty language out of the project.

## Definition of done for MVP code

The MVP should run after:

1. installing requirements,
2. creating `.env` from `.env.example`,
3. setting `DISCORD_TOKEN`, `CLIENT_ID`, `GUILD_ID`, and optionally `ADMIN_LOG_CHANNEL_ID`,
4. running `python bot.py`.
