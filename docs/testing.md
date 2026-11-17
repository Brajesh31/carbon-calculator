# 🧪 Testing and Validation

## Current coverage

There is no automated calculation test suite. Repository CI checks Python syntax and local Markdown links only. They do not establish factor accuracy, scientific validity, interface correctness, accessibility conformance, or deployment reliability.

## Automated checks

- Python syntax compilation for `app.py`.
- Relative Markdown link validation.
- GitHub Actions on pushes and pull requests.

## Manual smoke test

1. Create an isolated virtual environment.
2. Install Streamlit using [installation.md](installation.md).
3. Run `python -m streamlit run app.py`.
4. Confirm the country selector and four inputs render.
5. Calculate with all-zero inputs.
6. Calculate with representative non-zero values.
7. Change each input independently.
8. Inspect terminal and browser for errors.
9. Repeat keyboard-only and at narrow width.

Use fictional, non-sensitive values.

## Calculation cases to automate when logic is extracted

| Case | Expected property |
|---|---|
| All zeros | All category outputs and total are zero |
| One category non-zero | Other categories remain zero |
| Minimum values | Finite and non-negative output |
| Maximum values | Finite result within independently derived bounds |
| Unit conversion | kg to tonnes divides by 1,000 |
| Annualization | Correct documented time-period conversion |
| Rounding | Total policy independently tested |
| Invalid values | Explicit rejection or safe handling |

Expected fixtures must be independently derived, not copied from the formula under test.

## Scientific review

Passing CI is not scientific validation. Sources, boundaries, units, and assumptions require competent review before results are described as validated. See [methodology.md](methodology.md).
