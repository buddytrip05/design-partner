# Rubric: make good output repeatable

Run this on every screen or deliverable before handing it over. It's the "eval" for design work: simple, checkable, and the same every time.

## The ten checks

| # | Check | Pass when |
|---|---|---|
| 1 | **Requirements covered** | Every in-scope requirement is visible on a screen or state, or explicitly listed as out of scope. Each is reported as done, partial or missing. |
| 2 | **States exist** | Empty, loading and error states exist wherever there's data or an action. The "what happens next" after the main action is shown. |
| 3 | **Patterns cited** | Each borrowed interaction names its source and how it was accessed, or is labeled as a guess. |
| 4 | **Design system applied** | The user's real components, tokens, icons and copy rules are used, not look-alike markup. Departures are listed with a reason. With no system: clearly labeled placeholders. |
| 5 | **Questions flagged** | Anything the source doesn't answer is in the ledger as Open or Hypothesis and marked on the screen. Anything the source itself flags as open was asked, not chosen. Requirement changes are called out. |
| 6 | **Accessible basics** | Tap targets roughly 44px or larger, text contrast meets WCAG AA, meaning never depends on color alone, labels on inputs. |
| 7 | **Sources honest** | No claim to follow a document that wasn't read. Stated, inferred and assumed are kept apart. Quotation marks only around exact words. Every note is true of the screen it describes. |
| 8 | **Invented content labeled** | Made-up names, numbers and copy are identified as placeholders, agree with any figure in the source, and are the same across files. |
| 9 | **One source of truth** | No two files in the project disagree on a rule, a value list or a number. Anything superseded is updated or marked stale. |
| 10 | **Checked for real** | Every changed screen was looked at, and the check showed the right screen. Controls that don't work are disclosed. Nothing overlaps or overflows. |

For handoff and QA deliverables, add:

| # | Check | Pass when |
|---|---|---|
| 11 | **Handoff complete** | Every state has a spec with exact copy. Every requirement has acceptance criteria. Every ticket can be read cold. Tickets are saved to a file as drafts. |
| 12 | **Tests traceable** | Every test case names its source and how defined its expected result is. Undecided results are marked "Record", not given an invented expectation. |

Score each as **Pass**, **Fix**, **N/A**, or **Not verifiable**. Fix every "Fix" before delivering, or list it as a known gap.

Report only what the material supports. If contrast values, target sizes, keyboard behavior, focus order or accessible names can't be inspected, mark them **Not verifiable** and state how to check them. Never present a visual review as an accessibility audit.

## Grader prompt

If you can run a second pass (or the user wants to grade output from any AI tool), use this:

> You are reviewing a product design deliverable for a team without a dedicated designer. Score it against these checks: requirements covered, states exist, patterns cited, design system applied, questions flagged, accessible basics, sources honest, invented content labeled, one source of truth, checked for real. For each, answer Pass, Fix, N/A or Not verifiable, and for every Fix give the exact screen and what's wrong in one line. For every Not verifiable, say how to check it. Then list any decision the design made that the source material did not support, and any place two files disagree. Be strict; "probably fine" is a Fix.

## Golden set

Encourage the user to keep three to five screens they consider excellent for their product (their own best work or shipped references) in a folder, and to compare new output against them. "Good" becomes something they can point at, not argue about.

## The rules loop

You don't learn from feedback between sessions on your own. The user's context does. When the same rubric failure or the same user correction appears twice:

1. Write it as a one-line rule: "Always show the hold length before the giver commits." "Use the production status list verbatim."
2. Suggest the user add it to a `DESIGN_RULES.md` file in their project (starter: `assets/templates/design-rules.md`).
3. On future runs, read that file first and follow it. Mention when a rule shaped a decision.

Good candidates for rules: the product's nouns, fixed value lists, ticket conventions, copy casing, things a customer warned against, and anything the user has corrected before.

## Testing the skill itself

This rubric grades design deliverables. To check that the skill *behaves* well (picks the right mode, follows its evidence rules, admits limits), see the fixture set in the repository's `evals/` folder.
