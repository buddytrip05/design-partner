# Rubric: make good output repeatable

Run this on every screen or deliverable before handing it over. It's the "eval" for design work: simple, checkable, and the same every time.

## The six checks

| # | Check | Pass when |
|---|---|---|
| 1 | **Requirements covered** | Every in-scope requirement is visible on a screen or state, or explicitly listed as out of scope. |
| 2 | **States exist** | Empty, loading and error states exist wherever there's data or an action. The "what happens next" after the main action is shown. |
| 3 | **Patterns cited** | Each borrowed interaction names its source (app, guideline, design system) or is labeled as a guess. |
| 4 | **System tokens only** | Colors, type and spacing come from the user's design system, or from clearly labeled placeholders. No one-off styles. |
| 5 | **Questions flagged** | Anything the source material doesn't answer is in the ledger as Open or Hypothesis, not silently decided. Requirement changes are called out. |
| 6 | **Accessible basics** | Tap targets roughly 44px or larger, text contrast meets WCAG AA, meaning never depends on color alone, labels on inputs. |

Score each as **Pass**, **Fix**, **N/A**, or **Not verifiable**. Fix every "Fix" before delivering, or list it as a known gap.

Report only what the supplied material supports. If contrast values, target sizes, keyboard behavior, focus order or accessible names can't be inspected (common with screenshots and text wireframes), mark them **Not verifiable** and state how to check them. Never present a visual review as an accessibility audit.

## Grader prompt

If you can run a second pass (or the user wants to grade output from any AI tool), use this:

> You are reviewing a product design deliverable for a team without a dedicated designer. Score it against these six checks: requirements covered, states exist, patterns cited, system tokens only, questions flagged, accessible basics. For each, answer Pass, Fix, N/A or Not verifiable, and for every Fix give the exact screen and what's wrong in one line. For every Not verifiable, say how to check it. Then list any decision the design made that the source material did not support. Be strict; "probably fine" is a Fix.

## Golden set

Encourage the user to keep three to five screens they consider excellent for their product (their own best work or shipped references) in a folder, and to compare new output against them. "Good" becomes something they can point at, not argue about.

## The rules loop

You don't learn from feedback between sessions on your own. The user's context does. When the same rubric failure or the same user correction appears twice:

1. Write it as a one-line rule: "Always show the hold length before the giver commits." "Never pre-check items the family already owns."
2. Suggest the user add it to a `DESIGN_RULES.md` file in their project (or their project instructions, or the design system docs).
3. On future runs, read that file first and follow it. Mention when a rule shaped a decision.

Over time the rules file becomes the team's design memory: small, specific, and earned.

## Testing the skill itself

This rubric grades design deliverables. To check that the skill *behaves* well (picks the right mode, follows its evidence rules, admits limits), see the fixture set in the repository's `evals/` folder.
