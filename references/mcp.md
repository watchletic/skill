# Watchletic MCP tools

Use the connected universal Watchletic MCP at `https://api.watchletic.com/mcp`. Read-only is the default permission. An active Watchletic Club membership is required for data tools, but a user may connect or revoke a client without one.

Start with `get_account_status`, `get_catalog` when capability discovery is needed, and `get_training_context` for ordinary analysis. Drill into one activity, structured workout, analytics view, or explicitly selected raw channel only when it answers a named question. Selecting route or location data reveals precise location information. Request live-tracking recipients only when the user specifically asks about them.

File tools return sanitized metadata, a short-lived MCP resource, and a ten-minute HTTPS download. Report `raw_data_unavailable` and partial bulk exports rather than implying missing samples can be recovered.

All mutations use this sequence:

1. Call the focused preview tool with the exact proposed action.
2. Show the returned action summary, before/after diff, and warnings.
3. Ask for explicit confirmation immediately after showing that preview.
4. Call the matching apply tool with the unchanged action and confirmation token.

Every mutation operation has a matching focused preview/apply pair, such as `preview_activity_update` and `apply_activity_update`. Pass the unchanged action fields and confirmation token to the matching apply tool. Never apply after an ambiguous reply, after changing the payload, or using an expired preview. Preview again instead.

A Read-only connection can analyze and preview but cannot apply. If an apply tool returns an authorization challenge, explain that Full access is needed and let the user reconnect through Watchletic. Do not seek alternate credentials.
