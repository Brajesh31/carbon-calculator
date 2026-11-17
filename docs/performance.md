# ⚡ Performance Notes

The current app is a single-page Streamlit script with four inputs and basic arithmetic. It does not perform database queries, external API calls, batch processing, or file transformations.

## Keep it proportionate

- Do not add infrastructure without evidence of a bottleneck.
- Keep calculation functions deterministic and inexpensive.
- Avoid network lookups during every Streamlit rerun.
- If factors become external, define versioning and refresh behavior.
- Measure before optimizing.

## Investigation

Record host, Python and Streamlit versions, startup time, session count, and reproducible steps. Separate startup, widget rerun, and network latency. Never publish personal user inputs or secrets in performance reports.

No formal performance benchmark or service-level objective currently exists.
