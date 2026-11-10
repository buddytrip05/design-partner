# Evidence mode: let customers settle what the team can't

Use when there are customer calls to plan or digest, a concept to get reactions to, two directions to compare, or a ledger full of hypotheses. The goal is evidence the team can decide with. It informs a decision; it doesn't make one.

## Three kinds of evidence, weakest to strongest

Say which kind you have. Never report one as another.

| Kind | What it is | What it can support |
|---|---|---|
| **Said** | A discovery call or interview: what people say they do, want or would do | Problems, context, priorities, vocabulary. Weak for predicting behavior |
| **Reacted** | A demo or concept walkthrough: how people respond to a design they're shown | Which parts resonate, what's missing, what worries them. Polite enthusiasm is common |
| **Did** | A usability test: people attempting a task while you watch | Where a design fails, and why |

## A. Discovery calls

### Before: the discovery guide

Use `assets/templates/discovery-guide.md`. Build it from the ledger:

- **Assumptions to challenge.** Take the riskiest Hypothesis rows and the dependency assumptions from Pass mode. Write a neutral question for each; don't ask people to confirm your answer.
- **Ask about last time, not next time.** "Walk me through the last quote you revised" beats "Would you use a pipeline?".
- **Mark what's in this version and what's exploratory,** so nobody presents an idea as a commitment.
- **Ask how their account and team actually work** (who logs in, as whom, on what device) before showing anything.
- Show the design late, after the open questions.

### After: the call synthesis

Use `assets/templates/call-synthesis.md`. The shape:

1. **Summary:** three to five sentences. Lead with what changes a decision.
2. **Customer snapshot:** size, roles, tools, how they work today.
3. **Takeaways by audience:** one list for engineering, one for business or sales.
4. **Reaction table:** one row per component or idea shown, their reaction, and a **signal** rating.
5. **Pain points outside this feature,** with a priority and a "dig into" note.
6. **Quotes,** lightly cleaned, marked if not fit to share widely.
7. **Ledger updates,** by row ID.

**Rating signal honestly:**
- **Strong:** unprompted, specific, tied to something they do today.
- **Conditional:** depends on something else being true ("useful if we start sending digital quotes").
- **Weak:** hypothetical, hedged, or about other people ("younger staff might want that").
- **Change requested:** they asked for something different, with a reason.
- **Confirms current design.**
- **Unknown:** shown, but they didn't react. Write Unknown; don't read silence as approval.

Separate **stated need** from **conviction**. "I'd love that, but I don't know that we'll ever get there" is a high need with low conviction; record both.

### Across calls

- Count customers, not percentages: "2 of 2 raised shared logins."
- A theme raised independently by different customers outranks a strong reaction from one.
- Keep each customer's context attached. A 140-location chain and a 20-person showroom can say the same words and mean different things.
- One call is one call. Say "based on one call" where it's true.

## B. Usability tests

### Choose what to test

Pick the one to three ledger rows that are riskiest: most expensive if wrong, most disputed, or most central to the product's promise. Write each as a question the test will answer.

With two directions, plan a **comparative** test: each participant tries both, in alternating order. This is qualitative usability testing, not an A/B test. It shows *why* people struggle, not statistically *which* wins.

### Recruit

**Default: about five participants per round.** Jakob Nielsen's long-standing guidance (Nielsen Norman Group, "Why You Only Need to Test with 5 Users", 2000) is that about five users per round surface most usability problems, and that several small rounds beat one large one. With distinct user groups, test three or four from each. Adjust if you have a reason, say why, and write N everywhere after that.

Recruit people who match the persona, not colleagues.

### Write the task script

Use `assets/templates/usability-test-plan.md`.

- A realistic scenario with a reason to care.
- A clear end state.
- No interface words: don't say "tap Reserve".
- One to three tasks, 15–20 minutes per session.

Add a short intro ("We're testing the design, not you. Think out loud.") and three to five debrief questions.

### Observe

Three columns per task, the same lenses as Critique mode:

- **Hesitated:** where and for how long.
- **Misunderstood:** what they thought something meant.
- **Reached for:** what they looked for that wasn't there.

Plus: completed (yes / with help / no) and a direct quote. Stay quiet and don't rescue the participant; the silence is the data.

### Prototypes for testing

Realistic sample data, the real copy, the states you're testing, and nothing that pretends to work but doesn't. If something isn't built, have it say so.

## C. Turn evidence into decisions

After any call or round:

1. **Group findings by ledger row.** For each: how many of N, the kind of evidence (said, reacted, did), and the best quote.
2. **Update the row.** If the evidence is clear and the owner chooses, mark it **Decided** with basis "user evidence", the owner, the date, and what would reopen it. If it's mixed, keep it **Hypothesis** and plan the next step. Don't declare a winner from mixed results.
3. **Add new rows** for risks nobody had logged. Calls often surface assumptions no screen review would find.
4. **Propagate.** List every screen, document, ticket and test case that cites a changed row, and update them or mark them stale.
5. **Write decisions back to the PRD** as suggested edits.
6. **Keep the guardrails.** A customer's warning ("don't make it a muddy mess") is a design constraint; record it in the ledger or `DESIGN_RULES.md`.

Report honestly: a small round finds problems; it doesn't measure how common they are. Don't turn "3 of 5" into a percentage on a slide.
