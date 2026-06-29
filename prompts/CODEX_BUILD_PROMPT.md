# Codex Build Prompt

Paste this into Codex when ready to build the first MVP.

```text
You are working in the chamber-clerk-bot repository.

Before editing, read:
1. README.md
2. CODEX.md
3. .agents/coordination.yaml
4. docs/PROJECT_BRIEF.md
5. docs/PRIVATE_LAW_CHAMBER_DOCTRINE.md
6. docs/BOT_REQUIREMENTS.md
7. docs/PROMPT_RELAY_WORKFLOW.md

Task:
Build the first runnable Python Discord bot skeleton for Chamber Clerk Bot.

Requirements:
- Use Python and discord.py.
- Use slash commands only.
- Use python-dotenv for configuration.
- Use SQLite for the MVP.
- Do not require Message Content Intent.
- Do not hardcode secrets.
- Create .env.example, but do not create .env.
- Add a clean README setup section if needed.

Initial files to create:
- bot.py
- config.py
- db.py
- permissions.py
- utils.py
- cogs/__init__.py
- cogs/membership.py
- cogs/committees.py
- cogs/motions.py
- cogs/arbitration.py
- cogs/review.py
- cogs/archives.py
- requirements.txt
- .env.example
- .gitignore

Minimum functionality:
1. Bot starts with DISCORD_TOKEN from environment.
2. Bot syncs slash commands to GUILD_ID if provided.
3. Database initializes required tables.
4. Add a /ping command for health check.
5. Add basic permission helper based on Discord role names.
6. Add audit_log table and helper.
7. Add placeholder cogs with at least one safe command per module.

Doctrine guardrails:
- Keep the system private-law only.
- Keep all authority voluntary, membership-based, and contract-based.
- Do not add public-law, sovereignty, policing, taxation, or government-claim language.
- Preserve the Chief Arbitrator and Special Arbitration Review concepts as internal private procedure only.

Definition of done:
- Project installs with pip install -r requirements.txt.
- Project runs with python bot.py after .env is configured.
- Slash commands sync.
- SQLite database is created locally under data/.
- No secrets are committed.
- .agents/coordination.yaml is updated with an agent_log entry.

Output:
After implementation, summarize:
- files created
- commands available
- how to run
- anything not completed
```
