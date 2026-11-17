# 🛠️ Maintenance Guide

## Routine maintenance

- Review Python and Streamlit security advisories before upgrades.
- Select and test dependency versions before pinning them.
- Review Actions results after workflow changes.
- Triage reproducible defects and methodology concerns.
- Verify factor references, dates, and geographic applicability.
- Remove stale documentation and broken links.
- Revisit privacy and deployment guidance when integrations are added.
- Keep changelog entries aligned with user-visible changes.

## Factor maintenance

Do not update a factor using an unexplained number or secondary summary alone. Record publisher, source, date, geography, unit, boundary, gas basis, assumptions, uncertainty, and license. Preserve a change history and request competent review before describing data as validated.

## Dependency maintenance

The repository currently does not pin Streamlit or declare a supported Python version. Select a runtime, test the framework version against the app, confirm hosting compatibility, then add a reviewed dependency manifest. Upgrade in a branch and run smoke tests.

## Handover

Transfer repository and hosting ownership, deployment URL, runtime version, secret inventory without values, incident contact, and open issues. Revoke old access and rotate credentials when ownership changes.
