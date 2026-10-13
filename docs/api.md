# API

## Current status

The repository does not expose an application API. It has no REST or GraphQL
routes, API specification, authentication tokens, or supported programmatic
contract. The current interface is a Streamlit page loaded from `app.py`.

Streamlit internally communicates between its browser frontend and Python
server, but that framework transport is not a public API for this project.
Clients should not depend on undocumented Streamlit messages or endpoint
details; they may change with Streamlit versions.

## Inputs and results

The user-facing page accepts four widget values: daily commute distance in
kilometres, monthly electricity in kWh, weekly waste in kilograms, and meals
per day. It displays annualized category estimates and a total after the
calculate button is clicked. These values are not currently accepted through a
separate callable function or external request handler. The calculation is
embedded in `app.py`; current formulas and assumptions are recorded in
[architecture.md](architecture.md).

There is no guarantee of API compatibility, response schema, rate limit,
availability, or data-retention behavior for automated clients because no such
API has been implemented or promised.

## If an API is proposed

Open an issue before implementing one. The design should define and review:

- A versioned request and response schema with explicit units and validation.
- The meaning and allowed range of every input, including commute basis and
  annualization assumptions.
- Factor source, geography, date, calculation boundary, attribution, and
  rounding behavior.
- Authentication, abuse prevention, rate limits, and deployment ownership.
- Whether requests or results are logged or retained, and for how long.
- Error responses and compatibility policy.

Do not publish the existing illustrative factors through a new endpoint as if
they were validated. Review the privacy and deployment implications in
[deployment.md](deployment.md) and [database.md](database.md) as part of any
proposal.
