# Prompt Relay Workflow

## Purpose

This repository is the communication layer between the owner, ChatGPT, Codex, and future agents.

The intended workflow is:

1. The owner gives the goal to ChatGPT.
2. ChatGPT turns the goal into a clear Codex prompt.
3. The owner pastes that prompt into Codex.
4. Codex implements work in this repository through commits, branches, issues, and pull requests.
5. ChatGPT reads Codex's repository updates.
6. ChatGPT uses the new repo state to create the next Codex prompt.

## Role of ChatGPT

ChatGPT is used as the prompt architect, reviewer, and planning assistant.

ChatGPT should:

- read repository docs and recent changes before drafting new Codex prompts
- preserve the private-law doctrine
- identify what Codex already completed
- identify the next narrow implementation task
- write prompts that are specific, bounded, and testable
- help review Codex outputs and turn findings into follow-up prompts

ChatGPT should not assume work is complete unless it can see the relevant files, commit, pull request, issue, or documented result.

## Role of Codex

Codex is the implementation agent.

Codex should:

- read `README.md`, `CODEX.md`, and `.agents/coordination.yaml`
- implement the task given in the current prompt
- work in branches and pull requests where possible
- update docs when behavior changes
- update `.agents/coordination.yaml` after meaningful work
- avoid secrets and `.env` commits

## Role of the owner

The owner controls the project direction.

The owner may:

- paste ChatGPT-generated prompts into Codex
- approve or reject Codex work
- give ChatGPT repo updates or ask ChatGPT to inspect the repo
- ratify chamber doctrine and major architecture choices

## Prompt design standard

Each Codex prompt should include:

1. Repository context
2. Current known state
3. Exact task
4. Files to inspect first
5. Files likely to edit
6. Doctrine guardrails
7. Security guardrails
8. Definition of done
9. Required output summary

## Do not do

- Do not ask Codex to build everything at once after the MVP is scaffolded.
- Do not let prompts drift into public-law, sovereignty, policing, taxation, or criminal-law framing.
- Do not ask Codex to handle Discord bot tokens or secrets directly.
- Do not store private arbitration evidence in the repo or Discord database.

## Best prompt loop

Use this loop repeatedly:

```text
Inspect repo -> identify gap -> write narrow Codex prompt -> Codex implements -> inspect changes -> write next prompt.
```
