# ⚠️ Known Issues and Limitations

These gaps are visible in the current code or repository configuration.

## Methodology

- [ ] Factors are examples with no recorded sources, dates, uncertainty, or validation.
- [ ] Commute input does not define one-way versus return distance or commute days.
- [ ] Daily commute value is multiplied by 365.
- [ ] Diet label implies per-meal factor, but code comment references per-kilogram basis.
- [ ] Electricity factor lacks grid region and reporting year.
- [ ] Waste factor lacks composition and disposal pathway.
- [ ] Output is CO₂, not a complete CO₂e footprint.
- [ ] National comparison text is hard-coded and uncited.
- [ ] Category values are rounded before total is summed.

## Engineering

- [ ] No automated calculation tests.
- [ ] No pinned dependency manifest or declared supported Python version.
- [ ] UI and calculation logic are coupled in `app.py`.
- [ ] No database, export, authentication, or public API.
- [ ] No formal keyboard/screen-reader audit recorded.
- [ ] No browser end-to-end test suite.
- [ ] Hosting logs and retention are provider-dependent.

Prioritize factor provenance and dimensional consistency before presenting results as dependable. Add calculation tests before expanding categories or geography. Do not add persistence without a user need and privacy review. Update this file only when code or evidence genuinely resolves an item.
