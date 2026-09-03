---
name: watchletic
description: Use the official Watchletic CLI to inspect, analyze, export, and safely change a Watchletic user's cloud data, including settings, activities, readiness, analytics, training load, integrations, routes, layouts, devices, and structured workouts. Use when a user asks about their Watchletic training, wants files or raw channels, or wants structured workouts drafted or scheduled.
---

# Watchletic

Use the official `watchletic` CLI. Never query Supabase, inspect Watchletic storage, or construct undocumented HTTP requests.

Start with `watchletic auth status --json`, then use `watchletic context --json` for bounded, deterministic summaries. The context intentionally omits full curves, raw samples, private live-tracking recipients, and complete structured-workout steps; fetch a referenced activity or structured workout only when the question requires it. Read [references/commands.md](references/commands.md) for exact commands and [references/data-model.md](references/data-model.md) when interpreting fields or availability.

For analysis, explain what the deterministic data supports, distinguish observations from inference, and report incomplete cloud data instead of filling gaps. Request raw channels only when a specific question requires them. Follow [references/analysis-and-scheduling.md](references/analysis-and-scheduling.md).

Use “structured workouts” exclusively. Before suggesting them, ask about goals, target dates, weekly availability, preferences, injuries, and health constraints. Draft a batch file, validate it, and show the returned schedule diff. Follow [references/structured-workouts.md](references/structured-workouts.md).

Get explicit user confirmation immediately before every settings change, structured-workout mutation, deletion, integration action, readiness/training-load change, or analytics rebuild. Never pass `--yes` until that confirmation has been given in the conversation. A prior general request to analyze or help is not mutation confirmation.

Watchletic does not host an LLM. Keep analysis and inference agent-side. Respect Read-only sessions and Watchletic Club access errors; explain the limitation without trying alternate credentials or data paths.
