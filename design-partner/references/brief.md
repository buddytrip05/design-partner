# Brief (part of Handoff mode): be the partner, not the ticket queue

Use when the user works with a designer (or an agency, or a design-minded engineer) and needs to hand off work, or wants to work better with design.

The PM's job in a design partnership is to bring the **problem, the people, the rules and the evidence**, and to make sure the hard questions get answered on purpose. The designer's job is the solution. A good brief makes the designer faster and the result better. A brief that's really a finished mockup makes the designer a production artist.

## Step 1: Build the brief

Fill in `assets/templates/design-brief.md`. Draw from the PRD, any Pass-mode ledger, and what the user tells you. The sections:

1. **The problem, in one paragraph.** Who is stuck, doing what, and why it matters now.
2. **The people.** Each role, what they're trying to get done, and what they bring (skill, device, context, patience).
3. **What success looks like.** Observable outcomes and how you'll know: a metric, a task completion, a support ticket that stops arriving.
4. **Rules and constraints.** Product rules the design must make visible, platform, design system, technical limits, privacy, legal, deadline.
5. **Edge cases that must be handled.** From the ledger. These are the things engineering will otherwise decide.
6. **Open questions for design.** Questions you want the designer to answer, not answers you want them to draw.
7. **References.** Shipped patterns worth looking at, each with what to borrow and why it might not fit. Label them as inspiration, not instructions.
8. **What we're NOT prescribing.** Explicitly hand over layout, flow and visual decisions. Name anything that is actually fixed (and why).
9. **Evidence so far.** Research, tests, data, quotes. Mark what's evidence and what's hypothesis.

If the user hands you their own mockup to include, keep it, but label it "one direction to react to, not the answer."

## Step 2: Questions to ask your designer

Give the user 5–8 questions tailored to the brief. Good ones open up the designer's reasoning:

- What would you need to know to be confident in this direction?
- Which of these edge cases worries you most?
- Where do you think the PRD is asking for the wrong thing?
- What would you test first?
- What are you optimizing for on this screen, and what are you trading away?
- Is there a pattern in our design system that already solves part of this?

## Step 3: Run the review well

Give the user a 30-minute review agenda:

1. **Restate the problem and the people** (2 min). Make sure the room agrees on who this is for.
2. **Walk the main task as a user** (10 min). Use a prototype if there is one. Don't review screens out of order.
3. **Go through the ledger rows** (10 min). Which are answered? Which are still guesses? Which change the PRD?
4. **Decide next steps** (5 min). What to test, what to write back to the PRD, what moves to the roadmap.
5. **Capture decisions** (3 min). Update the ledger live.

During the review, feedback follows the rules in `critique.md`: user and task first, problem before fix, evidence separated from opinion.

## When there's no designer

Say so plainly: the user owns these decisions now. Offer to run Pass mode to produce the screens, then Critique mode on the result, then Evidence mode. Suggest they keep the brief anyway. It's the same thinking, and it's the document a future designer will thank them for.

## Turning the work into alignment and a roadmap

When the user needs to bring stakeholders along, add these to the deliverable:

- **Decision log:** every *Decided* ledger row, with the evidence or rule behind it and the date.
- **Roadmap bets:** every *Hypothesis* or *Open* row worth acting on, written as a bet: "We believe [change] will [outcome] for [people]. We'll know when [signal]." Note what evidence would change your mind.
- **Walkthrough script:** a five-minute script for walking executives through the prototype by task, not by screen, ending on the decisions you need from them.
