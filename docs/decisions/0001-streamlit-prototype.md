# ADR 0001: Keep the single-page Streamlit prototype

- **Status:** Accepted
- **Date:** 2026-11-17

## Context

The application is one Streamlit script with four inputs, fixed example factors, and a result view. It has no API, database, or multi-step workflow.

## Decision

Keep the single-page structure while product scope and methodology are clarified. Do not add a backend or database merely for appearance.

## Consequences

The app remains straightforward to run, but UI and arithmetic are coupled and harder to test independently. If calculations grow, extract pure functions and tests before introducing broader infrastructure.

## Revisit when

The application adds multiple workflows, external calculation consumers, persistent accounts, or substantially more complex calculations.
