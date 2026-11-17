# 🎨 Interface Design Principles

The app currently uses standard Streamlit components. This guide documents future consistency principles, not an existing custom design system.

## Information hierarchy

1. Explain purpose and prototype limitations.
2. Group controls by activity.
3. Keep units and time periods beside inputs.
4. Use a clear calculation action.
5. Present category results and total with units.
6. Keep assumptions visible near outputs.

## Interaction principles

- Prefer native labeled Streamlit controls.
- Never rely only on emoji or color.
- Use consistent names and units across UI and docs.
- Do not hide critical warnings in tooltips.
- Explain zero, empty, and invalid states.

## Visual assets

Store diagrams in `docs/assets/`, use descriptive filenames and accessible labels, and reference them with relative paths. Verify rights before adding external imagery.
