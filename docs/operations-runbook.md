# 🧭 Operations Runbook

## Local startup

```bash
python -m streamlit run app.py
```

Use the terminal URL and keep the process running while testing. Stop with Ctrl+C.

## Basic health check

- Confirm the configured host and branch.
- Confirm the entry point is `app.py`.
- Inspect deployment build and runtime logs.
- Open the app and test a non-sensitive sample.
- Confirm the warning and result categories render.
- Check that no startup traceback is present.

## Common incidents

### App unavailable
Check provider status, process health, configured port, branch, and runtime logs.

### App fails during startup
Check Python and Streamlit compatibility and inspect the complete traceback.

### Unexpected result
Do not patch factors by guessing. Reproduce with sample inputs, inspect the exact annualization and factor, and follow [methodology.md](methodology.md).

### Suspected data exposure
Restrict access, preserve evidence, rotate affected credentials, and follow provider incident procedures. Use private security reporting.

## Recovery and rollback

Use the hosting provider's documented rollback or redeployment mechanism. Verify the restored commit and smoke-test the app. No database backup or restore procedure exists because the application currently has no database.

## Operational limitations

This repository does not define production uptime, alerting, resource limits, backups, or a service-level objective. Those must be established by the deployment owner if the app is hosted publicly.
