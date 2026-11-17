# 🛡️ Project Security Notes

The current app has no authentication, database, public application API, or required secret values.

## Repository hygiene

- Never commit `.env`, Streamlit secrets, tokens, passwords, private inputs, or deployment credentials.
- Review dependencies and update for security fixes.
- Use least-privilege Actions permissions.
- Pin third-party Actions to reviewed immutable revisions where practical.
- Keep sensitive details out of public issues.

## Hosting

Streamlit executes Python on the host. TLS, access controls, resource limits, log retention, and patch management must be configured at the hosting layer. The repository alone does not provide those controls.

## Reporting

Follow [SECURITY.md](../SECURITY.md). Do not publish exploitable details in a public issue before the maintainer has assessed the report. The lack of explicit application storage does not establish a hosting provider's retention policy; see [privacy.md](privacy.md).
