# ADR 0002: Require provenance before changing emission factors

- **Status:** Accepted
- **Date:** 2026-11-17

## Context

The factors in `app.py` are marked as examples. The repository does not document their sources, data vintages, boundaries, or validation.

## Decision

Every new or changed factor must include source, date, geography, activity definition, unit, boundary, gas basis, assumptions, uncertainty, and reuse license. Do not call a factor validated until a competent reviewer has assessed it.

## Consequences

Changes may take longer when appropriate evidence is unavailable, but factors become auditable. Contributors must provide provenance and independently checked examples. Public claims must match the evidence.

## Revisit when

The project adopts a formal factor dataset, methodology standard, or documented external review process.
