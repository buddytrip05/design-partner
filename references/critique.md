# Critique mode: walk it like a real person would

Use when the user shares screens, screenshots, a mockup, a prototype or a live URL. The goal is feedback a designer can act on and a stakeholder can't dismiss as taste.

## Step 1: Set the persona and the task

You need a specific person and a specific job. Ask the user, or infer from the material and state it:

> **Persona:** Grandma Jo, 70, uses her phone for texting and photos, has never used this app.
> **Task:** "Leo's birthday is next week. Find a book he doesn't have, and make sure nobody else buys it."

A good task is realistic, has a clear end state, and doesn't use the interface's own words (say "make sure nobody else buys it", not "tap Reserve").

If the product serves several roles (buyer and seller, parent and giver), walk each role separately.

## Step 2: Walk it screen by screen

On each screen, as that person, look for three things. These are the same three things you'd watch for in a live usability test:

- **Hesitation:** where would they pause, re-read, or scroll looking for something?
- **Misunderstanding:** what would they think a word, icon or button means that it doesn't?
- **Reaching:** what would they look for that isn't there? A reach is a clue to an unmet expectation, not automatically a requirement.

Then check the screen against well-known usability heuristics where relevant, by name, so the feedback travels: visibility of system status, match with the real world, user control and freedom, consistency, error prevention, recognition over recall, and clear recovery from errors (from Jakob Nielsen's ten usability heuristics). Also check accessibility basics: contrast, tap targets of roughly 44px or more, text that doesn't depend on color alone.

## Step 3: Rate and flag

For each issue:
- **Severity:** *Blocker* (they can't finish or will do the wrong thing), *Major* (they finish with real friction or doubt), *Minor* (noticeable but recoverable), *Polish*.
- **Evidence:** which persona, which step, what they'd likely do.
- **Suggested fix:** one concrete option, with a source if it borrows a pattern. Offer a second if they're genuinely different.
- **Changes a requirement?** Yes or no. If yes, name the PRD line and propose the edit.

Also list **what's working** in one or two lines. Designers need to know what to protect, and it keeps the critique credible.

## Step 4: Deliver

Use `assets/templates/critique-report.md`: persona and task, a short summary (top three issues), the issue table sorted by severity, what's working, ledger updates, and the next step (usually: test the top two issues with five people).

## How to phrase feedback for a designer

This is the part that makes someone a design advocate instead of a backseat designer. Teach it when the user is going to share the critique:

- **Lead with the user and the task, not the pixel.** "Grandma doesn't see whether the book is already covered until the second screen" beats "move the status up."
- **Describe the problem; offer the fix as an option.** "One option is…" leaves room for the designer's better idea.
- **Separate evidence from opinion.** Say which issues came from a walkthrough (a hypothesis) and which came from real users (evidence).
- **Ask before you prescribe.** "What were you optimizing for here?" often reveals a constraint you didn't know.
- **Name what's working.** It tells the designer what to keep while they fix the rest.

Rewrite any taste-based comment the user gives you into this form, and show them the before and after.
