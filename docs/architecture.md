# Architecture

## Scope

Personal Carbon Calculator is a small, single-process Streamlit application.
The current implementation lives in the repository-root `app.py`; it does not
use a separate service layer, application database, external API, or background
worker. The repository does not declare a supported Python version or pin
Streamlit in a dependency manifest.

## Request and calculation flow

1. Streamlit renders the country selector and four input controls in the
   browser.
2. Widget values are sent to the Python process for the active Streamlit
   session. Streamlit reruns the script when a widget changes.
3. `app.py` converts each input to an annual quantity and applies the fixed
   factor under `EMISSION_FACTORS["India"]`.
4. Each category result is converted from kilograms to tonnes and rounded to
   two decimal places. The displayed total is the sum of those rounded
   category results, rounded again to two decimal places.
5. The result block is rendered when the user clicks **Calculate CO2
   Emissions**.

The currently implemented calculations are:

| Category | Input period | Annualization in source | Example factor in source | Display calculation |
| --- | --- | --- | --- | --- |
| Transportation | Daily kilometres | Distance × 365 | 0.14 kg CO2/km | Annual km × factor ÷ 1,000 |
| Electricity | Monthly kWh | kWh × 12 | 0.82 kg CO2/kWh | Annual kWh × factor ÷ 1,000 |
| Diet | Meals per day | Meals × 365 | 1.25 kg CO2/meal | Annual meals × factor ÷ 1,000 |
| Waste | Kilograms per week | kg × 52 | 0.1 kg CO2/kg | Annual kg × factor ÷ 1,000 |

The values are labeled as examples in source and do not have documented
provenance. In particular, the diet factor's source comment mentions a
per-kilogram basis while the dictionary key labels it per meal. The commute
control does not define whether distance is one-way or round-trip or how many
days per year it applies. The output calls the gas CO2; it should not be
interpreted as a complete CO2-equivalent life-cycle footprint.

## Main components

- **Presentation:** Streamlit page configuration, headings, controls, and
  category/total results are all declared in `app.py`.
- **Configuration/data:** The India label, fixed factors, input ranges, and
  annualization constants are embedded in the same file.
- **Persistence:** The app has no explicit database or result export. It does
  not intentionally write submitted values to a project data store. The host
  still processes widget values for an active app session; hosting and platform
  logs are outside this repository's control.
- **Integration:** There is no application API or authentication layer.

## Current design constraints

The presentation and arithmetic are coupled, which makes independent
calculation checks harder. Factors cannot be dated, selected by region, or
audited against a local source file. The total is based on already-rounded
categories. The national comparison is a hard-coded sentence with no citation.
These constraints should be addressed before describing the estimate as
validated or extending it to consequential uses. The proposed sequencing is in
[ROADMAP.md](../ROADMAP.md).
