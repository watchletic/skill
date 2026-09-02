# Analysis and scheduling

Begin with:

```sh
watchletic context --from YYYY-MM-DD --to YYYY-MM-DD --timezone AREA/CITY --json
```

The context combines bounded settings, recent activity metadata, readiness, deterministic analytics, training load, and upcoming structured workouts. It deliberately excludes raw samples.

Analyze in this order:

1. Check `completeness`, the requested range/timezone, and Premium/access status.
2. Summarize actual frequency, duration, distance, training-load pattern, readiness, and scheduled work.
3. Use Watchletic's deterministic analytics and selected training-load sources before making qualitative inferences.
4. State uncertainty where activities are excluded, raw samples are absent, dates are sparse, or analytics are processing.
5. Request one relevant raw format/channel only if it can answer a named question, such as pacing drift, DFA-alpha1 response, route/elevation effects, or sensor quality.

For scheduling, preserve recovery and existing commitments, prefer incremental changes supported by recent load, and explain the reason for each workout. Respect the user's metric setting and week start. Scheduling advice is not medical advice.

After the user supplies goals, target dates, availability, preferences, injuries, and health constraints, create and validate a structured-workout batch as described in `structured-workouts.md`. Keep any AI-derived conclusions in the response and local draft; Watchletic does not host or retain the model's reasoning.
