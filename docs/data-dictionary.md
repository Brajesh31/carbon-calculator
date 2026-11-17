# 📘 Data Dictionary

This dictionary describes the current user-facing input fields and the units implied by `app.py`. It is not a validated activity-data standard.

| Field | UI meaning | Unit | Period | Current transformation | Ambiguity |
|---|---|---|---|---|---|
| `country` | Country selector | Country label | N/A | Looks up factor set | India is currently the only option |
| `distance` | Daily commute distance | km | Daily | × 365 | One-way/return, commute days, mode, occupancy unspecified |
| `electricity` | Electricity consumption | kWh | Monthly | × 12 | Household versus individual allocation unspecified |
| `meals` | Number of meals | count | Daily | × 365 | Meal size/type and factor unit unresolved |
| `waste` | Waste generated | kg | Weekly | × 52 | Household allocation and waste treatment unspecified |

## Result fields

| Result | Unit shown | Meaning |
|---|---|---|
| Transportation emissions | tonnes CO₂/year | Annualized distance × example factor |
| Electricity emissions | tonnes CO₂/year | Annualized electricity × example factor |
| Diet emissions | tonnes CO₂/year | Annualized meal count × example factor |
| Waste emissions | tonnes CO₂/year | Annualized waste mass × example factor |
| Total emissions | tonnes CO₂/year | Sum of rounded category values |

## Future data requirements

Future fields should specify stable identifiers, units, allowed ranges, period, geography, allocation rule, null behavior, and validation. Do not silently change the meaning of an existing field.
