# Watchletic skill

A portable AI skill for analyzing and safely managing Watchletic cloud data through the connected Watchletic MCP or the official `watchletic` CLI fallback.

The canonical repository is [watchletic/skill](https://github.com/watchletic/skill). This repository is independent from the CLI.

## Installation

Install the skill from GitHub:

```sh
npx skills add watchletic/skill
```

The skill keeps AI inference agent-side, starts from bounded deterministic summaries, and requires explicit confirmation before mutations. The universal MCP endpoint is `https://api.watchletic.com/mcp`.
