# Security Policy

## Supported code

Security reports are considered for the current main branch. This repository contains a small Streamlit application with no authentication, database, external API, or application secrets.

## Report privately

Do not publish a vulnerability or sensitive deployment details in a public issue. Use GitHub private vulnerability reporting for this repository if enabled:

https://github.com/Brajesh31/carbon-calculator/security/advisories/new

If private reporting is unavailable, contact Brajesh Kumar (@brajesh31) through https://github.com/brajesh31. Include the affected commit, impact, and a safe reproduction. Remove personal information and secrets from logs.

## Data and deployment notes

The app has no explicit persistence or secrets. Streamlit runs Python on the host and sends widget values between the browser and that app session. Do not collect identifying or sensitive data without a privacy design and clear user notice.

Keep local virtual environments, .env files, and Streamlit secrets outside Git. If a future integration requires credentials, use the deployment platform's secret manager rather than source code or a committed secrets.toml file.

## Accuracy and user safety

The current factors and national comparison are hard-coded, and the factors are described in source as example values without citations. Treat results as unverified estimates. This is a scientific-integrity and user-trust concern; it becomes a security issue if the app is used to make consequential claims or decisions without validation.

## Response

The maintainer will acknowledge and assess reports as reasonably soon as possible, coordinate a fix and disclosure where practical, and credit reporters if requested. No fixed response or patch deadline is promised.
