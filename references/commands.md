# CLI commands

Use `--json` for stable machine-readable output. The CLI defaults to human-readable output. Do not expose stored credentials; `watchletic auth status --json` is redacted.

## Authentication and discovery

```sh
watchletic auth login
watchletic auth login --full
watchletic auth status --json
watchletic auth logout
watchletic me --json
watchletic catalog --json
```

Read-only is the login default. Full access enables mutations. The CLI refreshes stored sessions automatically. An ephemeral `WATCHLETIC_ACCESS_TOKEN` overrides stored credentials and is never persisted.

## Settings and training data

```sh
watchletic settings get --json
watchletic settings set --file settings-patch.json --json
watchletic activities list --from 2026-08-01T00:00:00Z --to 2026-09-01T23:59:59Z --json
watchletic activities get ACTIVITY_ID --json
watchletic readiness list --json
watchletic analytics get --json
watchletic analytics fitness --scope running --range 90d --json
watchletic training-load get --json
watchletic live settings --json
watchletic live sessions --json
```

Mutating commands prompt by default. After explicit conversation confirmation, rerun the exact command with `--yes --json` when the environment is non-interactive.

## Raw data and exports

Write downloaded health data outside a source checkout or under its ignored `exports/` directory. Never commit a user's FIT, GPX, TCX, native Watchletic, NDJSON, CSV, or bulk ZIP files.

```sh
watchletic activities raw ACTIVITY_ID --format json --json
watchletic activities raw ACTIVITY_ID --format ndjson --output exports/activity.ndjson --json
watchletic activities raw ACTIVITY_ID --format csv --output exports/activity.csv --json
watchletic activities export ACTIVITY_ID --format fit --output exports/activity.fit --json
watchletic activities export ACTIVITY_ID --format gpx --output exports/activity.gpx --json
watchletic activities export ACTIVITY_ID --format tcx --output exports/activity.tcx --json
watchletic activities export ACTIVITY_ID --format alpha1Csv --output exports/alpha1.csv --json
watchletic data export create --file bulk-export.json --json
watchletic data export status JOB_ID --json
watchletic data export download JOB_ID --output exports/watchletic-data.zip --json
```

Treat `raw_data_unavailable` as a real cloud-data gap. Do not suggest an Apple Health/HealthKit backfill. Bulk manifests may mark individual activities missing or format-unavailable; report partial exports.

## Other resources

`routes`, `layouts`, and `devices` support `list`, `get`, `create`, `update`, and `delete`. Logical Bluetooth profiles are cloud data; hardware scanning, pairing, and locators remain device-local. `integrations` supports `list`, `connect`, `options`, `import`, `export`, and `disconnect`. Connection flows are hosted in Watchletic, so provider credentials never enter the CLI or agent.
