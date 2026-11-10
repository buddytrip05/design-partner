# Pass mode: from PRD to designed decisions

Use when the user has a PRD, spec or user story. The goal isn't pretty screens. The goal is to find every decision the document doesn't make, propose grounded answers, and make the rest visible.

## Step 1: Inventory the requirements

List each requirement in scope with a stable ID (R1, R2…; reuse the PRD's own IDs if it has them). For each one, name the screen or state where a user would meet it. Requirements with no obvious screen are your first finding: something is missing, or the requirement is really a rule that needs a visible moment (for example, "clicking a store link doesn't count as buying" needs a screen that tells the giver).

Keep scope tight. If the PRD is large, ask which flow matters most, or pick the core flow (the one the product exists for) and say so.

## Step 2: Draw a minimal baseline

Build the smallest design that satisfies the explicit requirements without introducing new product behavior. Don't improve anything yet. This is deliberate: a baseline shows what the PRD actually says, and the gaps only show up when something has to go on a screen. Log every decision you had to make to build it; those are your first open questions.

Don't treat the document's section order as screen or navigation order unless the PRD says so. But do note where document order would push something important down the page: engineers and AI tools often build in the order a spec is written, so that's a real risk. (As a workshop exercise, drawing strictly in document order is a fast way to demonstrate specification gaps.)

How to "draw" depends on your environment:
- If you can produce visuals (HTML, a design canvas, an artifact or a prototyping tool), build low-fidelity screens at a real device size (390×844 for phone). Use the user's design system if they have one.
- If you can only produce text, write a **wireframe spec** per screen: top-to-bottom list of regions, what's in each, the primary action, and the states.

Label this draft clearly as "the baseline, not a recommendation."

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

Pick the one to three highest-risk questions a pattern could answer and run research (see `research.md`). Search by flow or pattern ("multi-select with unavailable items", "registry showing what's already purchased", "order status timeline"), not by famous app. Start with one to three references per question; expand only when the evidence is thin or conflicting. Write the reference brief, including how you accessed each source.

## Step 5: Propose materially different approaches

For the riskiest one to three screens, propose 2–4 approaches that differ in how the job gets done: what's shown first, what's the default, how many steps, what's locked, what's automatic. For each: the user it serves best, the trade-off, the assumption it rests on, and the reference it borrows from.

Then build or spec the strongest direction (or two, if they're close enough that only users can settle it). Mark every answer you adopted as **Hypothesis** in the ledger, with its basis and source.

## Step 6: Deliver

Deliver in this order:
1. **Top findings**, the three to five things the user most needs to know (missing screens, contradictions, risky defaults).
2. **The screens** (baseline and proposed, clearly labeled) or wireframe specs.
3. **The reference brief.**
4. **The ledger**, with row IDs.
5. **Suggested PRD edits**, written as text the user can paste: what to add, change, or decide, referencing requirement and ledger IDs. Never edit their PRD without asking.
6. **One next step:** usually "test L3 and L5 with a small round of users" (Test mode) or "bring this to your designer" (Brief mode).

## Tone

Be direct and specific. The user is a capable PM, not a design student. Show the decision, the evidence, and the trade-off. Skip design jargon unless you define it in the same sentence.
