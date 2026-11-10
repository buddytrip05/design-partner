# Build mode: a design that's better than the default

Use when the user wants a real design or prototype, not just an audit. A default AI design is plausible and generic: invented pages, one happy state, made-up numbers, look-alike components. This mode replaces each of those with something deliberate.

## Step 1: Shape the brief

A thin prompt gets an average design. If the request is short, don't refuse it and don't guess: turn it into the brief below, fill in what you know, and ask the user for the rest in one round (see Intake in `SKILL.md`). Show them the filled-in brief so they can correct it.

**The brief shape that works:**

1. **The job, in one line.** What this screen or card helps a person decide or do. ("Help a rep decide which job to open next.") Without it you get five variations of fields instead of one answer.
2. **The people,** and a real sentence from one of them if there is one.
3. **Concepts and screens, by name.** "Two flows: (A) …, (B) …. For each: the list page, the create flow, the warning state."
4. **States to show.** Closed, loading, populated, empty, error: name the ones that matter.
5. **What's out.** Non-goals, and anything in a reference that must *not* be copied.
6. **What must stay open.** Decisions nobody has made. These become labeled placeholders, not settled UI.
7. **Real values.** Status lists, roles, limits, time windows, and the copy if it's fixed.
8. **Deliverables besides screens.** A short user flow, trade-offs, a recommendation, a list of decisions for product and engineering.
9. **Fidelity and use.** Wireframe or polished; static or clickable; who reviews it, on what screen, to decide what.

If the user can answer only three, ask for 1, 3 and 5.

## Step 2: Ground it

- **The page being extended:** work from a screenshot or the real code, never from memory of what such a page "usually" looks like. If you have neither, mark the screen "Invented layout: needs a real reference".
- **References:** run Reference mode on any screenshot the user supplied. Use it for what they said to use it for (layout, not content, or the reverse).
- **The design system:** read it before drawing. Use its real components, tokens, icons and copy rules. Looking similar is not the same as using it.

## Step 3: Build with craft

- **Hierarchy from the job.** The first thing the eye lands on is the thing the person needs in order to decide. Everything else is quieter.
- **Density on purpose.** Add a number only if someone acts on it. More numbers on a dashboard make each one weaker.
- **Realistic sample data.** Use the domain's real kinds of things, with plausible names, amounts and dates, and a fixed "today" so date logic is checkable. Reuse the same sample set on every screen so totals reconcile.
- **Every state is a screen.** Empty, loading, error, partial, success, no permission, and "what happens next". Write the empty-state copy; don't leave a blank box.
- **One name per thing.** Pick the noun and use it everywhere.
- **Copy that explains the rule.** If a product rule lives only in the PRD, put a short line on the screen where the user meets it.
- **Open points on the screen.** Where a decision is open, show a labeled placeholder ("Proposed cap. Not decided.") next to the element, and collect all of them in one decisions list with a suggested owner each.
- **Not color alone.** Status and priority carry an icon or a word as well as a color.
- **Honest prototypes.** If a control doesn't work, either make it say so or list it. Never ship a button that silently does nothing without telling the user.

## Step 4: Options, when they help

Offer options when the decision is about *how the job gets done* and the user can only judge by seeing. Two or three, each with who it serves, the trade-off and the assumption behind it, and a recommendation. Give each a short ID (1a, 1b) so feedback can point at it.

Don't offer options to avoid deciding. If the job is clear, build one strong version.

## Step 5: Review your own work before the user does

1. **Look at every screen you changed.** Confirm the capture shows the screen you meant, not a different one.
2. **Check what overlaps and what overflows.** Floating panels over charts, and content added to a fixed-height area, are the usual faults.
3. **Read every label as the user.** Fix escape codes, placeholder text and inconsistent names.
4. **Run the rubric** (`rubric.md`), including the design-system check.
5. **Walk it as the persona** (a short Critique pass) on the main task.

## Step 6: Deliver

- The screens.
- **What changed,** if this is a revision: a short before-and-after list. Keep the previous version as a copy before a large rewrite.
- **The coverage report** (`assets/templates/coverage-report.md`): requirements done, partial, missing; working vs. static controls; invented data and copy; what wasn't visually checked.
- The ledger and one next step.

Say plainly what you did not do. "I wrote the tooltip text myself; please check it" is more useful than a summary that sounds finished.
