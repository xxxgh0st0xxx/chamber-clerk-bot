# Chamber Clerk Bot

Coordination and implementation repository for the **Chamber Clerk Bot**, a Discord-based digital chamber system for an International Private Law Chamber.

The project starts digital-first as a Discord server. The long-term vision may include a formal institution, arbitration chamber, review chamber, committee rooms, offices, law library, archive, and physical headquarters, but the MVP is the server and bot infrastructure.

## Core purpose

The bot supports a private-law chamber that can manage:

- membership and onboarding
- committees and committee reports
- private-law motions, clauses, articles, and amendments
- adoption and versioning of chamber rules
- doctrine archives and markdown exports
- arbitration registry metadata
- Special Arbitration Review procedure
- audit logging and role-based permissions

## Institutional doctrine

1. The Chamber only designs private law.
2. Chamber authority is voluntary, membership-based, and contract-based.
3. No Chamber rule overrides host-state law.
4. The Chamber appoints the Chief Arbitrator.
5. The Chief Arbitrator administers arbitration under Chamber rules.
6. Special Arbitration Review is the internal appeal/review mechanism.
7. Committee members may act as review arbiters only when appointed under the rules.
8. All adopted rules, motions, reports, and decisions are archived and versioned.

## Important limits

This project must not be framed as a government, public-law system, sovereign body, police power, taxation authority, or replacement for public courts. It is a private, voluntary, contractual governance-design and arbitration-administration system.

## Working with Codex and agents

Before editing, agents must read:

1. `README.md`
2. `CODEX.md`
3. `.agents/coordination.yaml`

All meaningful work should happen through issues, branches, and pull requests. Agents must update `.agents/coordination.yaml` after major changes.

## Security rules

- Never commit Discord bot tokens.
- Never commit `.env`.
- Use `.env.example` only.
- Do not store sensitive arbitration evidence in Discord or the database.
- Avoid Message Content Intent for the MVP.
- Use slash commands only for the MVP.
- Restrict administrative commands by Discord role.

## Target Discord deployment

The bot is intended for the Discord server represented by this invite:

`https://discord.gg/SvJxJxQ26`

Bots are not added through the normal server invite. They are added through a Discord OAuth2 bot invite URL generated from the Discord Developer Portal.

Required OAuth2 scopes:

- `bot`
- `applications.commands`

Invite URL format:

```text
https://discord.com/oauth2/authorize?client_id=YOUR_CLIENT_ID&permissions=268823632&scope=bot%20applications.commands
```

## MVP technology

- Python
- discord.py
- Slash commands / application commands
- SQLite for MVP
- PostgreSQL-ready structure later
- python-dotenv
- Role-based permissions
- Markdown export
- Docker-ready where practical

## Current status

Planning and coordination scaffold.
