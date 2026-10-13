# Database and data handling

## Database status

The current application has no database. It does not configure a database
driver, open a connection, define a schema, run migrations, or save calculated
results to a persistent store. There is therefore no database setup, backup,
restore, or migration procedure for this repository.

## What happens to inputs

The browser sends Streamlit widget values to the Python process serving the
page. Streamlit manages widget values in the active app session, and `app.py`
uses those values to calculate and render the estimate. The source does not
explicitly write them to a file, database, external API, analytics service, or
export. A hosted deployment processes inputs on its server, so the app should
not be described as purely on-device or guaranteed to retain no data anywhere:
the hosting platform's logs, operational controls, and retention settings are
outside the code in this repository.

The app does not ask for a name, email address, account, or location beyond its
single India selection. Avoid entering identifying or sensitive information.
Before adding analytics, exports, accounts, external processing, or persistent
storage, document what is collected, where it is processed, who can access it,
how long it is retained, and how users can request deletion.

## Deployment and secrets

The current code requires no credentials and reads no environment variables.
The root `.env.example` records that there are no current settings. If a future
integration needs a secret, keep it out of source control and use the hosting
platform's secret manager. `.gitignore` excludes common `.env` files and
Streamlit secrets files.

For Community Cloud deployments, consult Streamlit's
[secrets management guide](https://docs.streamlit.io/deploy/streamlit-community-cloud/deploy-your-app/secrets-management).
See [deployment.md](deployment.md) for host responsibilities and
[SECURITY.md](../SECURITY.md) for reporting and security guidance.

## If persistence is proposed

Do not add a database solely because the app is hosted. First define the
user-facing need and a data-protection design. A proposal should identify data
minimization, purpose, retention, deletion, access controls, encryption,
connection-secret handling, backups, and any legal or policy review. Keep
calculation logic usable without persistence where practical, and update the
architecture and privacy documentation before collecting data.
