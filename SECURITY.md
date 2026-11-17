# 🛡️ Security Policy

## Supported scope

Security reports are considered for the current default branch. The project is a small Streamlit prototype and currently has no authentication, database, public application API, or required application secrets.

## Reporting a vulnerability privately

Do not publish vulnerabilities, exploit details, credentials, or sensitive deployment configuration in a public issue.

Use GitHub private vulnerability reporting if enabled:
https://github.com/Brajesh31/carbon-calculator/security/advisories/new

If private reporting is unavailable, contact the maintainer through https://github.com/brajesh31. Include:
- A concise impact description.
- Affected commit or file.
- A safe reproduction or proof of concept.
- Any relevant sanitized logs.

Do not include personal data or live secrets.

## Security expectations

- Keep `.env`, Streamlit secrets, API tokens, and deployment credentials out of Git.
- Use host secret management for any future credentials.
- Keep dependencies reviewed and patched.
- Keep GitHub Actions permissions at the minimum required level.
- Review external actions and pin them to immutable revisions where practical.
- Avoid logging user activity values or sensitive context.
- Apply TLS, access control, resource limits, and logging retention at the host.

## Data handling note

The app has no explicit persistent storage, but Streamlit sends widget values to the Python server for the active session. This repository cannot guarantee what a hosting provider logs or retains. See [docs/privacy.md](docs/privacy.md).

## Scientific integrity and user trust

The factors currently embedded in the app are examples without documented provenance. Misrepresenting them as authoritative could mislead users and organizations. Do not market the current output as certified, verified, or complete. Report materially misleading claims as a project issue.

## Response

The maintainer will acknowledge and assess reports as reasonably soon as possible, coordinate remediation and disclosure where practical, and credit the reporter if requested. No fixed response or patch deadline is promised.
