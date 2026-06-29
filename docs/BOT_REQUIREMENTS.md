# Bot Requirements

## Project name

Chamber Clerk Bot

## Goal

Build one modular Discord bot that manages a digital-first International Private Law Chamber.

The bot should support members, committees, motions, private-law drafting, adopted rules, archives, arbitration registry, Special Arbitration Review, audit logs, and role-based permissions.

## Tech stack

- Python
- discord.py
- Slash commands / application commands only
- SQLite for MVP
- PostgreSQL-ready structure later
- python-dotenv
- Markdown exports
- Docker-ready where practical

## Security requirements

- Do not hardcode the Discord bot token.
- Use `.env` for secrets.
- Add `.env` to `.gitignore`.
- Include `.env.example` only.
- Do not require Message Content Intent for MVP.
- Do not store sensitive arbitration evidence.
- Arbitration module should only track case metadata, parties, deadlines, procedural status, panel members, and published summaries.
- Commands that change institutional records must require authorized roles.
- Every important action should write to `audit_log`.
- If `ADMIN_LOG_CHANNEL_ID` is configured, send major action logs there.

## Suggested Discord roles

- Founder
- Chamber Chair
- Chief Arbitrator
- Clerk
- Committee Chair
- Member
- Probationary Member
- Guest
- Review Arbiter
- Arbitrator

## Required modules

1. Membership
2. Committees
3. Motions / private-law drafting
4. Arbitration registry
5. Special Arbitration Review
6. Archives / doctrine search
7. Logging
8. Permissions

## Required slash commands

### Membership

- `/apply`
- `/approve_member user`
- `/set_member_status user status`
- `/member_profile user`

### Committees

- `/create_committee name description`
- `/assign_committee user committee role`
- `/committee_info committee`
- `/committee_report committee title body`

### Private-law drafting

- `/submit_motion title body`
- `/amend_motion motion_id body`
- `/send_to_committee motion_id committee`
- `/set_motion_status motion_id status`
- `/adopt_rule motion_id`
- `/view_motion motion_id`
- `/view_rule rule_id`
- `/search_doctrine query`

### Arbitration registry

- `/open_case title claimant respondent notes`
- `/assign_arbitrator case_id user`
- `/set_case_status case_id status`
- `/publish_award case_id summary`
- `/seal_case case_id`

### Special Arbitration Review

- `/request_special_review case_id grounds`
- `/appoint_review_chair review_id user`
- `/add_review_arbiter review_id user`
- `/recuse_arbiter review_id user reason`
- `/review_decision review_id decision`

### Archives

- `/archive_document title body type`
- `/export_minutes title body`
- `/export_rulebook`

## Suggested database tables

1. `members`
2. `committees`
3. `committee_members`
4. `motions`
5. `amendments`
6. `adopted_rules`
7. `arbitration_cases`
8. `review_requests`
9. `review_panel_members`
10. `archives`
11. `audit_log`

## MVP priorities

1. SQLite database initialization
2. Slash command sync
3. Role-based permission checks
4. Membership commands
5. Committee commands
6. Motion submission and adoption
7. Archive search
8. Arbitration case registry
9. Special Arbitration Review commands
10. Markdown export of adopted rulebook
