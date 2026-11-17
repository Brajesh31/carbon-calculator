# 👤 User Guide

## Start the app

Follow [installation.md](installation.md), then run:

```bash
python -m streamlit run app.py
```

Open the local URL shown in the terminal, usually `http://localhost:8501`.

## Enter activity values

1. Select India in the country selector.
2. Enter daily commute distance in kilometres.
3. Enter monthly electricity consumption in kWh.
4. Enter waste generated per week in kilograms.
5. Enter the number of meals per day.
6. Select **Calculate CO2 Emissions** to show results.

## Read the output

The app displays four category estimates and a total in tonnes of CO₂ per year. The current total is a sum of category values rounded to two decimal places.

## Important interpretation guidance

The factors are example values without documented sources or validation. Commute and diet assumptions are ambiguous, and important footprint categories are not included. Do not use the result as a complete personal footprint or for formal reporting.

For input definitions, see [data-dictionary.md](data-dictionary.md). For formulas and limitations, see [calculation-reference.md](calculation-reference.md) and [methodology.md](methodology.md).
