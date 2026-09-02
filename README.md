# Watchletic skill

A portable AI skill for analyzing and safely managing a Premium user's Watchletic cloud data through the official `watchletic` CLI.

The canonical repository will be [watchletic/skill](https://github.com/watchletic/skill). This repository is independent from the CLI. For local testing, install or link this directory using the skill mechanism supported by your agent. A future CLI command may install a pinned GitHub release; this local checkout is not connected to a remote or published yet.

The skill keeps AI inference agent-side, starts from bounded deterministic summaries, and requires explicit confirmation before mutations.
