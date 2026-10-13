# Deployment

This guide covers the current Streamlit app and describes a hosted deployment
path. No deployment configuration or production hosting setup is included in
this repository. Deployment behavior, availability, and access controls depend
on the selected hosting provider.

## Before publishing

1. Review the app's estimate limitations in [README.md](../README.md) and
   [architecture.md](architecture.md). The factors and comparison statistic
   are not adequately sourced or validated.
2. Choose and document the Python and Streamlit versions to deploy. This repo
   currently has no dependency manifest or version pin. Streamlit recommends a
   `requirements.txt` for Community Cloud dependencies and recommends pinning
   Streamlit for predictable updates. See the official
   [dependency guide](https://docs.streamlit.io/deploy/streamlit-community-cloud/deploy-your-app/app-dependencies)
   and [app management guide](https://docs.streamlit.io/deploy/streamlit-community-cloud/manage-your-app).
3. Review public visibility and privacy. The current app has no login or
   privacy notice; avoid collecting identifying or sensitive information.
4. Confirm you have rights to publish all source, factor data, and assets.

## Streamlit Community Cloud

The current entrypoint is `app.py` in the repository root. To deploy through
Community Cloud:

1. Push the branch you intend to publish to GitHub.
2. In the Community Cloud workspace, create an app and select this repository,
   branch, and `app.py` entrypoint. The official
   [deployment guide](https://docs.streamlit.io/deploy/streamlit-community-cloud/deploy-your-app/deploy)
   describes the current selection flow.
3. Set the Python version in the deployment settings to one compatible with
   the version you selected during development.
4. Deploy and review the build logs and the running page. Keep the deployment
   current when the published branch changes.

Community Cloud can run this source with Streamlit and its dependencies even
without a `requirements.txt`, but the repository does not currently declare a
version. Add a reviewed dependency file before relying on repeatable builds.
Do not guess a version pin: select a version and validate it against the app.

The app currently needs no secrets. If a future integration adds credentials,
keep them out of Git and use the host's secret manager. Streamlit documents
[Community Cloud secrets management](https://docs.streamlit.io/deploy/streamlit-community-cloud/deploy-your-app/secrets-management).

## Other hosting platforms

Use a host that supports a persistent Python process and can serve a Streamlit
application. Install the versions declared by the project and start the
repository entrypoint with `streamlit run app.py`, following the provider's
instructions for binding the server to its assigned interface and port. Put
TLS, network access controls, health monitoring, and resource sizing at the
hosting layer as appropriate. Do not assume local development settings are
sufficient for an internet-facing service.

Streamlit uses a browser client and a Python server. In a hosted deployment,
the server runs on the host, and widget values are sent to that server for
processing; the app does not calculate only on a visitor's device. See
Streamlit's [client-server architecture guide](https://docs.streamlit.io/develop/concepts/architecture/architecture).

## After deployment

- Confirm the public URL, repository branch, and entrypoint are correct.
- Review startup logs and use representative non-sensitive inputs.
- Keep dependencies and the hosting runtime updated through a reviewed change.
- If the app is public, make the prototype's estimation limits visible to
  visitors.
- Follow the host's procedures for pausing, removing, or transferring the
  deployment.

For local execution, see [installation.md](installation.md). For data handling
limitations, see [database.md](database.md).
