# QA definition of done (template)

The Manager has an agent copy this to `team/notes/qa-definition-of-done.md` and fill it in for the project. It's the bar for every **Release audit**: a piece of work is done only when every applicable line
passes, on the current working tree.

## 0. How every audit runs
1. **Build:** the project builds cleanly.
2. **Layer 1, checklist:** every line below, on everything in scope.
3. **Layer 2, automated checks:**
   - **Accessibility scan:** run axe through Playwright on every screen in scope, at every width in §1. 0 critical or
     serious issues.
   - **Visual comparison:** screenshot every screen in scope at every width and compare with the last release's
     screenshots (kept in `team/notes/qa-baseline/`). Every difference must be intended; flag the rest. After a
     passed release, the new screenshots become the baseline.
   - The project's own automated tests, if any: they pass, or every difference is explained and approved.
4. **Layer 3, user journeys:** real-user walkthroughs for the personas the change touches, with real clicks only.
5. **Report:**
   - PASS/FAIL per item.
   - Each failure says where (screen or page, width, state), what's wrong and what's expected, with a screenshot path.
   - Usability findings are reported separately from bugs, with severity (high, medium, low).

## 1. Coverage (what "every" means)
- **Widths:** <e.g. 1440 · 1280 · 1024 · 768 · 375 · 360 · 320>
- **States / variants:** <every state, dialog, menu and message reachable>
- **Roles / themes / modes:** <list>

## 2. Layout and responsiveness
- [ ] No sideways scroll at any width.
- [ ] No cut text a user needs to read.
- [ ] Nothing off-screen or overlapping.
- [ ] Sticky bars never cover content.
- [ ] Alignment and spacing follow the project's rules.

## 3. Interaction
- [ ] Touch targets are at least 44 × 44 below tablet width.
- [ ] Menus and dialogs close on Esc, on an outside click and after a choice. Focus goes in and comes back.
- [ ] Every action confirms itself (a message using the same verb, a visible change, or a dialog result).
- [ ] Data stays the same across screens: one source, no conflicting figures or names.

## 4. Visual rules
- [ ] Design tokens only; shared components only; no one-off styling.
- [ ] <the project's own visual rules>

## 5. Content
- [ ] Exact copy from the spec, word for word.
- [ ] No placeholder tags or lorem ipsum.
- [ ] One date format, one number format.

## 6. Accessibility
- [ ] 0 critical or serious automated accessibility issues (axe scan, Layer 2).
- [ ] Every input and link has an accessible name.
- [ ] Every flow can be completed with the keyboard alone.

## 7. Scope
- [ ] Nothing was built that the spec doesn't list. Gaps are flagged, not filled.
