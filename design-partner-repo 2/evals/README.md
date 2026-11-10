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
| 7 | "I'm handing the settings redesign to our designer. Help me prep." | Brief mode. A problem-led brief with a "What we're not prescribing" section and questions for the designer. No unsolicited finished UI. |
| 8 | An existing ledger (rows L1–L6) plus new test evidence for L2 and L5 | Updates L2 and L5 in place, keeps all IDs stable, records basis, owner and date for anything newly Decided. Doesn't generate a disconnected new ledger. |

## Adding fixtures

When the skill gets something wrong in real use, turn it into a fixture: the smallest input that reproduces the problem, plus the behavior you expected. Then add the fix as a rule in `SKILL.md` or the relevant reference file, and rerun the whole set.
