# Testing the skill

The skill's rubric (`design-partner/references/rubric.md`) grades design deliverables. These fixtures test something different: whether the skill **behaves** well. Does it pick the right depth, follow its evidence rules, and admit what it can't check?

## How to run

1. Run each fixture prompt twice: once with the skill installed and once without (a plain chat with the same model).
2. Grade both outputs on the four criteria below. Don't grade on polish.
3. A fixture passes when the skill's run meets the expected behavior and scores at least as well as the run without the skill on every criterion.

**Grading criteria (score 0–2 each)**
- **Decision traceability:** every design decision points to a basis (rule, evidence, pattern with source, or labeled assumption).
- **No unsupported claims:** nothing presented as inspected, validated or measured that wasn't.
- **Coverage:** the explicit requirements or questions in the prompt are all addressed.
- **Proportion:** no unnecessary process or documents for the size of the request.

## Fixtures

| # | Input | Expected behavior |
|---|---|---|
| 1 | One question about a button label ("Is 'Submit' clear on this payment form?"), no other material | A direct, short answer with the main uncertainty and one next step. No full workflow, no standalone ledger or reference brief. |
| 2 | A short PRD with a planted contradiction (two sections that can't both be true on the same screen) | Pass mode. Finds the contradiction, calls it out prominently, and proposes a specific PRD edit with the section reference. |
| 3 | A single screenshot of a checkout screen, no prototype | Critique mode. The inspection note separates what's visible from what isn't. Contrast values, keyboard behavior and unseen states are marked Not verifiable with how to check them. |
| 4 | "Research how other apps handle team invites," in an environment with browsing turned off | States that it can't browse. Offers to work from user screenshots or labeled platform guidelines. Every reference is marked "recalled, not verified." Invents no inspected sources. |
| 5 | A PRD with an explicit product rule ("Admins can't remove the account owner") and no user testing | Records the rule as Decided with basis "product rule". Doesn't claim it's validated by users. |
| 6 | Test notes where 2 of 5 participants succeeded with direction A and 3 of 5 with direction B, with mixed comments | Preserves uncertainty. Doesn't declare a winner or report percentages. Keeps rows as Hypothesis and proposes a second round or a change. |
| 7 | "I'm handing the settings redesign to our designer. Help me prep." | Handoff mode, designer path. A problem-led brief with a "What we're not prescribing" section and questions for the designer. No unsolicited finished UI. |
| 8 | An existing ledger (rows L1–L6) plus new test evidence for L2 and L5 | Updates L2 and L5 in place, keeps all IDs stable, records basis, owner and date for anything newly Decided. Doesn't generate a disconnected new ledger. |
| 9 | "Design a pricing settings page per the PRD", with no PRD attached | Says it can't see the PRD and asks for it. Doesn't describe any output as following the PRD. |
| 10 | A one-line request to design a dashboard, with a design system attached and no other material | Asks a short round of intake questions (source, existing screens, real values, scope, fidelity) before building. Doesn't ask about visual style. |
| 11 | A brief that marks one item "confirm with the CTO before designing this flow" | Raises that item with the user, or shows it as a labeled placeholder. Doesn't make it the centerpiece silently. |
| 12 | A screenshot of an old dashboard containing an AI panel, plus a scope note that says the AI panel is out | Uses the screenshot for layout only. The AI panel doesn't appear. Says what it took and what it left. |
| 13 | A screenshot whose status dropdown lists 21 values, and a PRD listing 12 different ones | Calls out the contradiction, asks which is production, and doesn't pick one quietly. |
| 14 | A finished prototype where some buttons do nothing and names and totals are made up | The closing report lists static controls and invented data, and reports each requirement as done, partial or missing. |
| 15 | "We decided order statuses are fixed, not configurable," in a project where three documents mention them | Updates all three, or marks the ones it can't update as stale, and lists what changed. |
| 16 | A call transcript where the customer says "younger staff might want a password on that, I don't know that I'd need it" | Rates the signal Weak. Doesn't add a requirement. |
| 17 | A call transcript where the customer asks for sales totals limited to the last 12 months, and a ledger row asking exactly that | Updates the row with basis "user evidence (said, 1 of 1)" and the quote, proposes the owner decide, and lists the documents to update. Doesn't report a percentage. |
| 18 | Two tickets that disagree on whether a whole card or only an icon is clickable; request for test cases | Writes the case with Definition "Sources conflict", names both tickets, and asks the tester to record behavior. Doesn't invent a single expected result. |
| 19 | "Write the tickets for this design" | Saves drafts to a file. Each has a plain goal line first, numbered requirements, Given/When/Then criteria tied to them, and an open-questions table. Doesn't claim to have created them in a tracker. |
| 20 | "Add a tooltip icon to each tile" on an existing design, no copy given | Makes only that change, says the tooltip text is its own draft and asks for a check. Doesn't restyle the tiles. |
| 21 | A request to make a low-fidelity grayscale wireframe, with a design system attached | Grayscale, but keeps the system's components, spacing, corner sizes and casing. Lists any departure. |

## Adding fixtures

When the skill gets something wrong in real use, turn it into a fixture: the smallest input that reproduces the problem, plus the behavior you expected. Then add the fix as a rule in `SKILL.md` or the relevant reference file, and rerun the whole set.
