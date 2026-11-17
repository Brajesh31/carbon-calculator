# 🧾 Assumptions Register

This register lists assumptions and unresolved decisions visible in the current prototype. Status is not a claim of scientific acceptance.

| ID | Area | Current assumption or ambiguity | Risk | Required resolution |
|---|---|---|---|---|
| A-01 | Transport | Daily commute input multiplied by 365 | May overstate annual travel if not daily year-round | Ask commute days and trip basis |
| A-02 | Transport | Distance meaning is not specified | One-way and round-trip values differ | Define input label and examples |
| A-03 | Electricity | One factor for India | Grid mix changes by region and year | Source dated regional factors |
| A-04 | Diet | Factor label and comment use different dimensions | Formula may be dimensionally invalid | Define meal or food-mass basis |
| A-05 | Waste | One factor per kg waste | Treatment route and composition change emissions | Define waste streams and disposal |
| A-06 | Output | CO₂ label | Could be mistaken for CO₂e footprint | Define gas coverage and exclusions |
| A-07 | Comparison | Hard-coded national statistic | May be stale or incomparable | Cite and define compatible boundary |
| A-08 | Rounding | Categories rounded before summation | Small differences accumulate | Define precision policy |

## Review workflow

For each assumption, record owner, evidence, decision, date, and affected code/tests/docs. Close an item only when implementation and documentation agree.
