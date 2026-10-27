# Personal Carbon Calculator

A small Streamlit app that estimates annual CO₂ emissions across transportation, electricity, diet, and waste using fixed example factors. The interface currently offers India as its only country.

This is an educational prototype, not a scientifically validated carbon-accounting tool. The source labels its emission factors as examples and supplies no source, date, or methodology for them. The displayed national per-capita comparison is also hard-coded without a citation. Do not use these values for reporting, policy, compliance, purchasing, or personal decisions until the factors and assumptions are independently validated.

## What the app does

The app collects four inputs:

- Daily commute distance in kilometres.
- Monthly electricity consumption in kilowatt-hours.
- Waste generated per week in kilograms.
- Number of meals per day.

It annualizes them in app.py, multiplies by the hard-coded India factors, converts kilograms to tonnes, and displays category and total estimates after the Calculate button is clicked.

The current annualization assumptions are 365 days for daily inputs and 52 weeks for weekly waste. The commute input does not ask whether the distance is one-way or round-trip, or how many days per week the commute occurs. The diet factor comment and unit basis are unclear. The result covers only four categories and excludes many parts of a personal footprint.

## Requirements

- Python 3
- Streamlit

The repository does not include a requirements.txt, pyproject.toml, or declared Python version. Dependency installation is therefore not locked or reproducible yet.

## Run locally

    python -m venv .venv
    .venv\Scripts\Activate.ps1
    python -m pip install --upgrade pip
    python -m pip install streamlit
    streamlit run app.py

On macOS or Linux, activate with:

    source .venv/bin/activate

Streamlit prints the local URL, usually http://localhost:8501. Stop the server with Ctrl+C.

## Repository layout

    app.py             Streamlit interface, emission factors, conversions, and result display
    docs/              Project, methodology, setup, and deployment guides
    .env.example       Notes that the current app needs no environment variables

## Data handling

The app does not connect to an API or database and does not explicitly save results. Streamlit processes widget values in the running app session. A hosted deployment runs on its host, so do not enter sensitive or identifying information.

## Contributing and security

Read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a change. Report vulnerabilities privately as described in [SECURITY.md](SECURITY.md).

## License

The project source is distributed under the MIT License. See [LICENSE](LICENSE). Confirm the rights for any added datasets, factors, or images separately.

Last updated: 2026-10-27 07:30 UTC
