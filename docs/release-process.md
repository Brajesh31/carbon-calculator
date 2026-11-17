# 📦 Release Process

The project does not yet have a formal release cadence. This document proposes a repeatable process.

## Pre-release checklist

- [ ] Review merged changes and open critical issues.
- [ ] Update `CHANGELOG.md`.
- [ ] Verify installation instructions and dependencies.
- [ ] CI checks pass.
- [ ] Manual smoke test completed.
- [ ] Calculation changes independently checked.
- [ ] Factor sources, units, boundaries, dates, and licenses reviewed.
- [ ] User-facing limitations updated.
- [ ] Accessibility reviewed for UI changes.
- [ ] No secrets, private data, or generated files included.
- [ ] Deployment uses the intended commit.

## Versioning proposal

When tagged releases begin, consider semantic versioning: MAJOR for incompatible behavior, MINOR for backward-compatible features, PATCH for fixes and documentation corrections. A factor update can materially change estimates even without an interface change, so call it out in release notes.

## Publish

1. Tag the reviewed default-branch commit.
2. Draft notes from the changelog.
3. Explain behavior, factor, and methodology changes.
4. Publish the GitHub release.
5. Verify deployment against the tagged source.
6. Record post-release issues.

Never claim certification without documented validation evidence.
