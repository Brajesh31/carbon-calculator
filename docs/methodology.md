# 🔬 Methodology, Emission Factors, and Data Quality

## 1. Scope

The application demonstrates annualizing a small set of activity inputs, multiplying them by example factors, and displaying category estimates. It is not a complete greenhouse-gas inventory, verified personal footprint, or substitute for a recognized reporting methodology.

The factors in `app.py` are explicitly examples. This repository does not document their sources, data vintages, system boundaries, uncertainty, licenses, or validation. Their presence in code is not evidence that they are correct.

## 2. Current factor values

| Activity | Source-code value | Implied unit | Critical gap |
|---|---:|---|---|
| Transportation | 0.14 | kg CO₂/km | Mode, occupancy, trip basis, and source unknown |
| Electricity | 0.82 | kg CO₂/kWh | Grid region, year, boundary, and source unknown |
| Diet | 1.25 | kg CO₂/meal label | Inline comment instead refers to kg CO₂ per kg |
| Waste | 0.1 | kg CO₂/kg | Composition, treatment route, and source unknown |

These values are transcribed for transparency, not endorsed.

## 3. Annualization in the current implementation

```text
annual_commute_km = daily_commute_km × 365
annual_electricity_kwh = monthly_electricity_kwh × 12
annual_meals = meals_per_day × 365
annual_waste_kg = weekly_waste_kg × 52
```

Each annualized activity quantity is multiplied by its example factor. The result in kilograms is divided by 1,000 and each category is rounded to two decimal tonnes. The displayed total sums those rounded category values.

This describes the current code, not a scientifically recommended assumption. The commute input does not define one-way or return distance and does not collect actual commute days.

## 4. Provenance required for every factor

Before a factor is introduced or changed, record:

- Publisher and source title.
- Publication date and effective/reporting period.
- Geographic coverage, such as country or electricity grid region.
- Activity definition and denominator.
- Explicit numerator and denominator units.
- System boundary, such as direct, upstream, or lifecycle emissions.
- Gas basis, CO₂ or CO₂e, including global-warming-potential basis if relevant.
- Conversion and allocation assumptions.
- Data uncertainty and known limitations.
- Reuse license and attribution requirements.

A URL without the unit, scope, and applicable geography is not adequate provenance.

## 5. Review procedure

1. Capture all provenance fields above.
2. Independently derive unit conversions.
3. Prepare hand-checkable examples, including zero and boundary cases.
4. Compare expected and computed values without reusing the same formula blindly.
5. Define a rounding policy and avoid early rounding where practical.
6. Request review by a person competent in the relevant emissions methodology.
7. Update the UI explanation, docs, tests, and changelog.
8. Preserve source version and review history.

## 6. Benchmarks and claims

The current app contains a hard-coded national per-capita comparison statement without a source or comparable boundary definition. Do not repeat it as a benchmark until its source, year, geography, gas basis, and scope are verified and shown to be comparable.

Do not claim the output is a complete footprint, a precise measurement, a verified reduction, or an official score. Do not rank or shame users based on the estimate.

## 7. Proposed factor record

| Field | Meaning |
|---|---|
| `factor_id` | Stable identifier |
| `activity` | Defined activity |
| `value`, `unit` | Factor and dimensions |
| `geography` | Applicable region |
| `valid_from`, `valid_to` | Validity dates |
| `source_title`, `source_url` | Provenance |
| `boundary`, `gas_basis` | Accounting scope |
| `license` | Reuse terms |
| `reviewed_by`, `reviewed_at` | Review record |

This is a future design proposal, not an existing database schema.
