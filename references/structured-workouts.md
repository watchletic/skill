# Structured-workout workflow

Use “structured workout” consistently. A structured workout may have a date or be unscheduled; the current model has no time of day.

Before drafting, obtain:

- the user's goal and target date;
- days and approximate time available each week;
- activity and workout preferences;
- recent training context and current readiness;
- injuries, symptoms, medical restrictions, or other health constraints.

Do not diagnose or override health advice. If constraints make a suggestion unsafe or too uncertain, narrow the recommendation and encourage appropriate professional guidance.

Create a JSON batch with `operations`. Each create contains `title`, `activityType`, `locationType`, `isMetric`, `isRecurring`, `parts`, nullable `date`, nullable `recurringUntil`, and nullable `external`. Updates and deletes include the exact current `expectedRevision`.

Always preview:

```sh
watchletic structured-workouts validate --file proposed-workouts.json --json
```

Show the returned diff in useful language, including dates, titles, activity types, recurrence, replacements, and deletions. The preview is not permission to mutate. Ask for explicit confirmation after showing it.

Only after confirmation:

```sh
watchletic structured-workouts apply --file proposed-workouts.json --yes --json
```

The apply command validates again and commits the validated batch atomically. If a revision changes, fetch current structured workouts, revise the proposal, preview it again, and ask again. Never add `--yes` during validation.
