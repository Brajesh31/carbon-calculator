# ❓ Frequently Asked Questions

## Is this a scientifically accurate carbon footprint calculator?

No. It is an educational prototype. The current factors are examples without documented source, date, boundary, or validation. See [methodology](methodology.md).

## Which country is supported?

India is currently the only country option.

## What inputs are collected?

Daily commute distance, monthly electricity consumption, meals per day, and weekly waste. See [data dictionary](data-dictionary.md).

## Why does the app multiply commute distance by 365?

That is what the current code does. It is a major assumption because the app does not ask for commute days per year or whether distance is one-way or return. Do not assume this is an appropriate travel model.

## Why is the diet factor unclear?

The dictionary labels the factor per meal, while its inline comment refers to a per-kilogram basis. The dimensional mismatch needs to be resolved before the output can be trusted.

## Does the result include all greenhouse gases?

No. The current result is labeled CO₂ and does not represent a complete CO₂e lifecycle footprint.

## Does the app save my results?

The repository has no explicit database or result persistence. Streamlit processes widget values on its server for the active session. Hosting provider logging and retention are separate.

## Is there an API?

No public application API is implemented. See [api.md](api.md).

## Can I deploy it publicly?

A compatible Streamlit host can run it, but a public deployment should make the prototype limitations clear and should not solicit sensitive inputs. See [deployment](deployment.md).

## How can I suggest a factor update?

Use the methodology-change issue template and provide source, date, geography, units, boundary, gas basis, license, and independent calculation evidence.
