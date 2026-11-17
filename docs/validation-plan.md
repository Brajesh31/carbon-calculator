# ✅ Validation Plan

## Objective

Define evidence needed before the prototype's results can be described as reliable estimates. This plan is not itself a validation result.

## Workstreams

### 1. Factor evidence
- Identify original data publishers.
- Record geography, reporting year, units, system boundary, gas basis, and license.
- Review uncertainty and applicability.

### 2. Dimensional analysis
- Verify every numerator and denominator.
- Resolve diet factor's meal-versus-mass inconsistency.
- Confirm all conversions preserve dimensions.
- Define commute and household allocation semantics.

### 3. Independent calculation
- Prepare hand-derived examples.
- Use an independent implementation or spreadsheet for cross-checking.
- Compare unrounded category results.
- Document rounding and aggregation policy.

### 4. Software tests
- Unit tests for calculation functions.
- Input validation tests.
- Regression tests for representative scenarios.
- UI smoke tests and accessibility review.

### 5. Expert review
- Obtain review from a qualified emissions-methodology practitioner.
- Record reviewer, date, scope, limitations, and accepted/rejected findings.
- Reassess when factor data or calculation boundaries change.

## Release gate

Do not use terms such as verified, certified, or scientifically accurate until evidence supports the specific claim and scope. Any unvalidated category must remain clearly labeled as illustrative.
