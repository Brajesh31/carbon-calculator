# Frequently asked questions

## What does the app estimate?

It estimates annual emissions for four inputs: transportation, electricity,
diet, and waste. It multiplies annualized quantities by fixed factors in
`app.py`, converts kilograms to tonnes, and shows category values and a total.
See [architecture.md](architecture.md) for the formulas as implemented.

## Which countries are supported?

Only India is selectable in the current interface. The code contains one set of
India-labeled example factors; there is no country-specific data selection
beyond that option.

## Are the numbers scientifically validated?

No. The source explicitly calls the factors examples and does not cite their
source, date, methodology, or boundaries. The diet factor's unit comment is
unclear, the commute distance assumptions are unspecified, and the result
covers only four categories. A national comparison sentence is also hard-coded
without a citation. Treat all displayed numbers as illustrative prototype
output, not as a verified personal footprint.

## Is the result CO2 or CO2-equivalent?

The interface labels the results as tonnes of CO2. The source does not define a
complete greenhouse-gas inventory or lifecycle boundary, so users should not
interpret it as a comprehensive CO2-equivalent estimate.

## How are values annualized?

Daily commute distance and meals per day are multiplied by 365. Monthly
electricity is multiplied by 12, and weekly waste is multiplied by 52. The
source has no input for commute days per week or whether distance means one-way
or return travel.

## Why do category totals and the grand total differ slightly from my own sum?

Each category is converted to tonnes and rounded to two decimal places before
the total is computed. The displayed total is the sum of those already-rounded
category values, rounded again to two decimal places.

## Does the app save my inputs?

The code does not explicitly write inputs or results to a database, file, or
external service. Streamlit processes widget values on the Python server for
the active session. Hosting platforms may have their own operational logging
and retention, which this repository does not configure. Do not submit
sensitive or identifying values. See [database.md](database.md).

## Does the app need an API key, environment variable, or database?

No. The current source reads no environment variables and does not connect to
an API or database. `.env.example` documents the current absence of settings.

## Is there a programmatic API?

No application API is implemented. The page uses Streamlit's own browser/server
interaction, which is not a supported project API. See [api.md](api.md).

## Can I use the estimate in a report or decision?

Not responsibly in its current state. Factors and assumptions have not been
validated or adequately sourced. Do not use the output for scientific,
regulatory, financial, purchasing, or other consequential decisions.

## How can I contribute or ask for help?

See [CONTRIBUTING.md](../CONTRIBUTING.md) for changes and factor-source
requirements, [SUPPORT.md](../SUPPORT.md) for help, and
[SECURITY.md](../SECURITY.md) for private vulnerability reports.
