# SDD: Portfolio UI Refinement

## 0. Inputs

### 0.1 My portfolio (project to refine)
```
[ https://saurabh-pande.netlify.app/ / "C:\Users\soura\OneDrive\Desktop\!recent\Important!\Portfolio ]
don't worry about this path in this workspace you have to work see `index.html` & `css`
```

### 0.2 Reference portfolios (for design inspiration only, do not copy)
1. https://bootstrapfolio.vercel.app/ (See how well design project Card 3 in row & connect section also so clean)
2. https://kunaltijareportfolio.netlify.app/ (See cleanesss of this site)

### 0.3 Extra notes (optional)
```
[ ANYTHING ELSE I WANT CHECKED OR CHANGED ]
```

## 1. Objective
Review and refine my existing portfolio so that it looks **clean, organised, eye-friendly, and market-ready**. My current portfolio is already good, so this is a refinement and not a redesign. The focus is cleanliness, visual consistency, and polish.

Use the reference portfolios only to understand how a clean, well-structured, market-standard portfolio looks (for example, how neatly their project cards are structured). Do **not** copy there whole project just for reference and build my porfolio accordingly with this existing.

## 2. Requirements
1. **Inspect first.** Study my entire portfolio and both reference portfolios before making any change.
2. **Cleanliness check.** Decide whether the portfolio looks clean and organised. If not, fix it, using the references as guidance.
3. **Colors.** Replace deep, harsh, overly saturated, or generic AI-style colors with a soft, professional, human-friendly palette that is easy on the eyes.
   - No irritating colors. Do not use danger or warning style colors (strong red, orange, or neon tones) for normal UI. Keep red or amber only for real error or warning states.
   - Keep text readable with good contrast, in every theme the portfolio supports.
4. **Tone of the layout (not needy, not greedy).** The recruiter already knows I am open to opportunities, so the portfolio should not feel needy or desperate for a job. The "available for opportunities" message and the Connect section should stay, but they should look calm, confident, and organised, with less visual pressure (no loud banners, no aggressive buttons, no repeated pleading text).
5. **Layout and polish.** Improve spacing, typography, visual hierarchy, alignment, and overall consistency. Make project cards well structured, consistently sized, and neatly aligned. Keep a sticky navbar that is clean and consistent.
6. **Review every project's presentation.** Check UI/UX, how functionality is presented, edge cases, error states, spelling, and grammar.
7. **Responsiveness.** All layouts must be consistent and polished on desktop, laptop, tablet, and all mobile sizes. Nothing may break at any width.
8. Keep the design clean, readable, accessible, and recruiter-friendly.

## 3. Strict Constraints
- Do **not** change any URL, route, link destination, API, business logic, or existing functionality.
- Do **not** remove or break any link, button, feature, section, or integration.
- Do **not** change or remove my current projects. They are good. Only refine how they are presented.
- Fix only UI and UX related issues. No unrelated refactoring.
- Do not copy any reference portfolio. The result must be original, human-designed, and not generic or AI-generated.
- Work only on the improvements described in this spec.

## 4. Acceptance Criteria
- [ ] The portfolio looks clean, organised, and professional, and feels human-designed.
- [ ] The color palette is soft and eye-friendly, with no harsh, danger-style, or generic AI colors.
- [ ] The portfolio does not feel needy or greedy, and the Connect section is still present and working.
- [ ] Sticky navbar and consistently sized, well-aligned project cards.
- [ ] Fully responsive on desktop, tablet, and all mobile sizes, with no layout breakage.
- [ ] No spelling or grammar mistakes.
- [ ] All existing links, routes, and features work exactly as before.
- [ ] No new console errors, broken links, or UI regressions.

## 5. Verification and Report
- Test the changes in a browser (all screen sizes) and check the console for errors.
- Confirm every link still points to the same destination as before.
- Report: files updated, what was changed and why, and checks performed.
- If something could not be tested, say so clearly. Do not claim it was tested.

---
### Execution order for the agent
Read Section 0 → inspect my portfolio and the references → decide what needs cleaning → apply refinements in small steps → test after each step → verify links, console, and responsiveness → final report. If a change might touch a link, route, or feature, stop and ask first.