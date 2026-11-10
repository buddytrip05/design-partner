# Pass mode: from PRD to designed decisions

Use when the user has a PRD, spec or user story. The goal isn't pretty screens. The goal is to find every decision the document doesn't make, propose grounded answers, and make the rest visible.

## Step 1: Inventory the requirements

List each requirement in scope. For each one, name the screen or state where a user would meet it. Requirements with no obvious screen are your first finding: something is missing, or the requirement is really a rule that needs a visible moment (for example, "clicking a store link doesn't count as buying" needs a screen that tells the giver).

Keep scope tight. If the PRD is large, ask which flow matters most, or pick the core flow (the one the product exists for) and say so.

## Step 2: Draw it literally (the baseline)

Draw the requirements exactly as written, in the order written, without improving anything. This is deliberate: a literal draft is what the PRD actually says, and the gaps only show up when something has to go on a screen.

How to "draw" depends on your environment:
- If you can produce visuals (HTML, a design canvas, an artifact or a prototyping tool), build low-fidelity screens at a real device size (390×844 for phone). Use the user's design system if they have one.
- If you can only produce text, write a **wireframe spec** per screen: top-to-bottom list of regions, what's in each, the primary action, and the states.

Label this draft clearly as "the literal baseline, not a recommendation."

## Step 3: Extract the open questions

Walk each screen and ask the questions below. Every one the PRD doesn't answer becomes a ledger row with status **Open**.

**What's first?** What does this person need to see in the first screenful? What did the PRD's section order push down the page?

**States:** empty (first use, nothing yet), loading, error, partial, success, "what happens next" after the main action.

**Edge cases that bite:**
- Duplicates (the same thing added twice, by two people, or in two versions)
- Concurrency (two people acting at once)
- Bulk actions ("select all" of *what*? what's excluded? what's locked?)
- Time (holds, expiry, reminders, things that change later, like a new item joining a set)
- Identity and devices (the same person on a second device, signed out, invited by link)
- Permissions and privacy (who sees what, what's hidden, what's revealed later)
- Undo and mistakes (can they back out? what's irreversible?)
- Rules that live only in the doc (where does the user learn them?)

**Contradictions:** read decisions and copy against each other. Two lines that are each fine can be impossible on the same card. Drawing is how you find this; call it out prominently.

**Copy:** button labels that don't say what they actually do ("Select all" vs. "Select the 8 you don't have").

## Step 4: Research before you redraw

For the questions a pattern could answer, run research (see `research.md`). Search by flow or pattern ("multi-select with unavailable items", "registry showing what's already purchased", "order status timeline"), not by famous app. Pull 3–8 references per hard question and write the reference brief: problem it solves, what to borrow, why it might not fit.

## Step 5: Propose materially different approaches

For the riskiest one to three screens, propose 2–4 approaches that differ in how the job gets done: what's shown first, what's the default, how many steps, what's locked, what's automatic. For each: the user it serves best, the trade-off, the assumption it rests on, and the reference it borrows from.

Then build or spec the strongest direction (or two, if they're close enough that only users can settle it). Mark every answer you adopted as **Hypothesis** in the ledger, with its source.

## Step 6: Deliver

Deliver in this order:
1. **Top findings**, the three to five things the user most needs to know (missing screens, contradictions, risky defaults).
2. **The screens** (baseline and proposed, clearly labeled) or wireframe specs.
3. **The reference brief.**
4. **The ledger.**
5. **Suggested PRD edits**, written as a diff the user can paste: what to add, change, or decide. Never edit their PRD without asking.
6. **One next step:** usually "test rows X and Y with five people" (Test mode) or "bring this to your designer" (Brief mode).

## Tone

Be direct and specific. The user is a capable PM, not a design student. Show the decision, the evidence, and the trade-off. Skip design jargon unless you define it in the same sentence.
