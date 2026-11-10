# Test mode: test the assumptions behind the directions

Use when there are two or more design directions, or a ledger full of hypotheses. The goal is a small, fast, qualitative test that shows why people struggle, so the team can decide with evidence instead of opinion. It informs a decision; it doesn't make one for you.

## Step 1: Choose what to test

Pick the one to three ledger rows that are riskiest: most expensive if wrong, most disputed, or most central to the product's promise. Write each as a question the test will answer: "Do parents notice that owned books are locked, or do they try to re-add them?"

If there are two directions, plan a **comparative** test: each participant tries both, in alternating order. Say clearly that this is qualitative usability testing, not an A/B test. It shows *why* people struggle, not statistically *which* wins.

## Step 2: Recruit

**Default: about five participants per round.** Jakob Nielsen's long-standing guidance (Nielsen Norman Group, "Why You Only Need to Test with 5 Users", 2000) is that about five users per round surface most usability problems, and that several small rounds beat one large one. If the product has distinct user groups (parents and gift-givers, buyers and sellers), test three or four from each group. Adjust if you have a reason, say why, and write N (the actual number) everywhere after that.

Recruit people who match the persona, not colleagues. Friends of friends, customers, a community Slack, or a few minutes at an event all work.

## Step 3: Write the task script

Use `assets/templates/test-plan.md`. Rules for tasks:

- Realistic scenario with a reason to care ("Leo's birthday is next week…").
- A clear end state, so you know when they're done.
- No interface words: don't say "tap Reserve" or "use the series picker."
- One to three tasks, 15–20 minutes per session.

Also write a short intro ("We're testing the design, not you. Think out loud. There are no wrong answers.") and three to five debrief questions ("What did you expect to happen when you tapped that?").

## Step 4: Observe

Give the user an observation sheet with three columns per task, the same three lenses as Critique mode:

- **Hesitated:** where and for how long.
- **Misunderstood:** what they thought something meant.
- **Reached for:** what they looked for that wasn't there.

Plus: completed (yes / with help / no), and a direct quote if there is one. Remind the user to stay quiet and not rescue the participant; the silence is the data.

## Step 5: Synthesize and update the ledger

After the round:
- Group observations by ledger row (use the row IDs). For each: how many of the N participants hit the problem, and the best quote.
- Update the row: if the evidence is clear and the owner chooses an answer, mark it **Decided** with basis "user evidence", the owner, the date, and what would make you revisit it. If evidence is mixed, keep it **Hypothesis** and plan another round. Don't declare a winning direction from mixed results.
- Record what you'd change before round two.
- Write the decisions back into the PRD as suggested edits.

Report honestly: a small round is enough to find problems, not to measure how common they are. Don't turn "3 of 5" into a percentage on a slide.

## Prototypes for testing

A clickable prototype is more realistic than static screens, and AI tools make one fast to build. Keep it honest: realistic sample data, the real copy, the states you're testing, and nothing that pretends to work but doesn't. If something isn't built, have it say so ("Not in this prototype") instead of failing silently.
