# Data model and units

Public DTOs use camelCase. Timestamps are ISO 8601, dates are `YYYY-MM-DD`, and measurements use SI units unless the field explicitly says otherwise. `revision` is the concurrency value for `If-Match`; the CLI manages it for ordinary update/delete commands.

Activities are completed workout metadata. Only user-editable fields such as `title` and `analyticsExcluded` can change. `rawDataAvailable` says whether Watchletic has uploaded samples for that activity. Metadata may exist when raw data does not.

Common raw channels include heart rate in beats/min, power in watts, speed in metres/second, distance/elevation/stride length in metres, temperatures in degrees Celsius, RR intervals and ground contact time in seconds, and DFA-alpha1 as dimensionless. Location tuples contain timestamp, latitude, longitude, altitude, horizontal accuracy, vertical accuracy, and speed. Use the `channelUnits` object returned with JSON raw data as authoritative.

Structured workouts are date-based and may be unscheduled. Their nested parts describe goals and targets. Do not invent a time-of-day field.

Routes contain coordinate/elevation arrays. Layouts and Bluetooth devices represent logical cloud profiles. Pairing and live hardware control are not public data operations.

Integration responses expose connection status and supported actions, but not provider credentials.

Agent context schema version 2 summarizes the 90-day analytics window into selected duration highlights and estimate-support activity IDs. Readiness includes recent entries and seven-day comparisons. Upcoming structured workouts include computed step counts, estimated duration/distance, target types, and IDs for focused retrieval rather than their full parts.
