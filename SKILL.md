---
name: watchletic
description: Use connected Watchletic MCP tools or the official Watchletic CLI to inspect, analyze, export, and safely change a Watchletic user's cloud data, including settings, activities, readiness, analytics, training load, integrations, routes, layouts, devices, and structured workouts. Use when a user asks about their Watchletic training, wants files or raw channels, or wants structured workouts drafted or scheduled.
---

# Watchletic

Prefer connected Watchletic MCP tools. If they are unavailable, use the official `watchletic` CLI. Read [references/mcp.md](references/mcp.md) or [references/commands.md](references/commands.md) for the selected interface.

Start with `get_account_status`, then `get_training_context`. With the CLI fallback, start with `watchletic auth status --json`, then `watchletic context --json`. The context intentionally omits full curves, raw samples, private live-tracking recipients, and complete structured-workout steps; fetch a referenced activity or structured workout only when the question requires it. Read [references/data-model.md](references/data-model.md) when interpreting fields or availability.

For analysis, explain what the deterministic data supports, distinguish observations from inference, and report incomplete cloud data instead of filling gaps. Request raw channels only when a specific question requires them. Follow [references/analysis-and-scheduling.md](references/analysis-and-scheduling.md).

Use “structured workouts” exclusively. Before suggesting them, ask about goals, target dates, weekly availability, preferences, injuries, and health constraints. Draft a batch file, validate it, and show the returned schedule diff. Follow [references/structured-workouts.md](references/structured-workouts.md).

Get explicit user confirmation immediately before every settings change, structured-workout mutation, deletion, integration action, readiness/training-load change, analytics rebuild, or bulk-export creation. With MCP, preview first, show the exact diff and warnings, and call the matching apply tool only after confirmation. With the CLI, never pass `--yes` until that confirmation. A prior general request to analyze or help is not mutation confirmation.

Watchletic does not host an LLM. Keep analysis and inference agent-side. Respect Read-only sessions and Watchletic Club access errors; explain the limitation without trying alternate credentials or data paths.
