# ♿ Accessibility Review

This checklist is guidance for the current Streamlit interface. It is not evidence that a formal accessibility audit has passed.

## Interaction checklist

- [ ] All controls are keyboard reachable and operable.
- [ ] Focus order follows the logical page sequence.
- [ ] Focus indicators are visible.
- [ ] Input labels identify activity and unit.
- [ ] Values are understandable without color alone.
- [ ] Calculate action has a clear accessible name.
- [ ] Updated results can be discovered without unexpected focus loss.
- [ ] Errors and invalid values are described in text.
- [ ] Contrast is sufficient for text and controls.
- [ ] Page works at high zoom and narrow viewport widths.

## Content checklist

- [ ] Emoji and color are not the only category identifiers.
- [ ] Daily, monthly, and weekly periods are explicit.
- [ ] Units appear beside result values.
- [ ] Prototype limitations are readable text.
- [ ] Headings follow a meaningful hierarchy.
- [ ] No flashing or time-limited interactions.

## Manual test procedure

1. Complete all inputs using only a keyboard.
2. Inspect accessible names and focus order.
3. Test at 200% zoom and on a narrow viewport.
4. Review with a screen reader where available.
5. Check contrast in supported display themes.
6. Record browser, OS, assistive technology, steps, and findings.

Automated checks cannot replace manual assistive-technology testing.
