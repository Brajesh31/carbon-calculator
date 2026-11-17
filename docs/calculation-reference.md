# 🧮 Calculation Reference

## Current formulas in app.py

The source annualizes each input before multiplying by its example factor.

```text
transport_kg = (daily_distance_km × 365) × 0.14
electricity_kg = (monthly_kwh × 12) × 0.82
diet_kg = (meals_per_day × 365) × 1.25
waste_kg = (weekly_waste_kg × 52) × 0.1

category_tonnes = round(category_kg / 1000, 2)
total_tonnes = round(sum(category_tonnes), 2)
```

The constants above are copied from the current source. They are example values without documented provenance.

## Important implementation details

- The total is calculated from category values already rounded to two decimal places.
- The commute quantity is multiplied by 365 even though the control is described as a daily commute.
- Diet is multiplied by a meal count even though the inline factor comment refers to kg of food.
- The app labels results as CO₂, not CO₂e.
- No factor metadata or version is attached to the result.

## Safe change procedure

Before changing a formula, define input semantics, units, boundary, and factor provenance. Create an independent worked example. Add automated tests around a pure function, update the UI wording and methodology guide, and describe result changes in CHANGELOG.md.
