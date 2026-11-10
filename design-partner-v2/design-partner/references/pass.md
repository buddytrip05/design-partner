# Pass mode: from PRD to designed decisions

Use when the user has a PRD, spec or user story. The goal isn't pretty screens. The goal is to find every decision the document doesn't make, propose grounded answers, and make the rest visible.

## Step 0: Have the document in view

Read the actual PRD. If the user mentions one you can't see, stop and ask for it. Don't describe a design as "aligned to the PRD" unless you read the PRD in this session.

## Step 1: Inventory the requirements

List each requirement in scope with a stable ID (R1, R2…; reuse the PRD's own IDs if it has them). For each one, name the screen or state where a user would meet it. Requirements with no obvious screen are your first finding: something is missing, or the requirement is really a rule that needs a visible moment.

This inventory becomes the coverage checklist you report against at the end (see `assets/templates/coverage-report.md`).

Also pull out everything the document itself marks as open, flagged or "confirm with…". Those are questions for the user now, not choices for you to make quietly.

Keep scope tight. If the PRD is large, ask which flow matters most, or pick the core flow and say so.

## Step 2: Label what you infer

A PRD implies more than it says. When you turn an implication into a design decision, record it as a ledger row with status **Hypothesis**, basis "inferred from §x", and the exact line it came from. Three labels, never mixed:

- **Stated:** the document says it. Quote or cite the line.
- **Inferred:** the document implies it. Cite the line and say what you concluded.
- **Assumed:** the document is silent. This is yours; mark it.

## Step 3: Draw a minimal baseline

Build the smallest design that satisfies the explicit requirements without introducing new product behavior. Don't improve anything yet. A baseline shows what the PRD actually says, and the gaps only show up when something has to go on a screen. Log every decision you had to make to build it.

Don't treat the document's section order as screen order unless the PRD says so. But note where document order would push something important down the page: engineers and AI tools often build in the order a spec is written.

- If you can produce visuals, build low-fidelity screens at a real device size. Use the user's design system if they have one.
- If you can only produce text, write a **wireframe spec** per screen: regions top to bottom, what's in each, the primary action, the states.

Label this draft "the baseline, not a recommendation."

## Step 4: Extract the open questions

Walk each screen and ask the questions below. Every one the PRD doesn't answer becomes a ledger row with status **Open**.

**What's first?** What does this person need in the first screenful? What did the PRD's order push down?

**States:** empty, loading, error, partial, success, and "what happens next" after the main action.

**Flow gaps:**
- Entry points: every way a person arrives (nav, link, email, deep link, another page's button).
- Exits: where each action leaves them, and what Back does.
- Roles: what each role sees, can do, and can't.
- Cross-surface effects: when something changes here, what else must update, and does it need a refresh?
- Notifications: who is told, how, and when.
- Data lifecycle: create, edit, archive, delete, restore; what happens to things that depend on a deleted item.
- Migration: what existing users and existing records look like on day one.

**Edge cases that bite:**
- Duplicates, concurrency, bulk actions ("select all" of *what*?)
- Time (holds, expiry, rolling windows, things that change later)
- Identity and devices (second device, signed out, invited by link)
- Permissions and privacy
- Undo and mistakes
- Rules that live only in the doc (where does the user learn them?)

**Contradictions:** read decisions and copy against each other, and against any other document or ticket in the project. Two lines that are each fine can be impossible on the same card. Call these out prominently.

**Copy:** labels that don't say what they do; one thing called by two names.

## Step 5: List the dependency assumptions

Some risks aren't on any screen. Ask: **what must already be true for this design to work?**

- **Data:** which fields must be filled in, and are they today? (A margin figure is wrong if cost is rarely entered.)
- **Account model:** does the design assume one login per person? Many teams share one.
- **Habits:** does it depend on users doing something they rarely do now, like keeping a status current?
- **Other systems:** what must arrive from an integration, and how fresh?

Log each as a ledger row with basis "assumption" and a next step, usually "ask a customer" (Evidence mode) or "ask engineering". These are often the highest-risk rows in the ledger.

## Step 6: Research before you redraw

Pick the one to three highest-risk questions a pattern could answer and run Reference mode (`reference.md`). Search by flow or pattern, not by famous app. Write the reference brief, including how you accessed each source.

## Step 7: Propose materially different approaches

For the riskiest one to three screens, propose 2–4 approaches that differ in how the job gets done: what's shown first, the default, the number of steps, what's locked, what's automatic. For each: the user it serves best, the trade-off, the assumption it rests on, and the reference it borrows from.

Then build or spec the strongest direction (or two, if only users can settle it). Mark every answer you adopted as **Hypothesis**, with its basis and source.

## Step 8: Deliver

1. **Top findings:** the three to five things the user most needs to know (missing screens, contradictions, risky defaults, shaky assumptions).
2. **The screens** (baseline and proposed, clearly labeled) or wireframe specs.
3. **The reference brief.**
4. **The coverage report.**
5. **The ledger**, with row IDs.
6. **Suggested PRD edits**, as paste-ready text referencing requirement and ledger IDs. Never edit their PRD without asking.
7. **One next step.**

## Tone

Be direct and specific. The user is a capable PM, not a design student. Show the decision, the evidence and the trade-off. Skip design jargon unless you define it in the same sentence.
