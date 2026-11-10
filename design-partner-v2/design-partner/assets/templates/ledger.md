# Requirements ledger: [feature name]

An open question isn't a requirement yet. A design's answer is a hypothesis until someone chooses it, and "decided" still isn't the same as "proven".

**Source:** [PRD name and version, read on date] · **Updated:** [date]

| ID | Screen | Open question | Current answer on screen | Basis | Status | Next step | Traces to |
|---|---|---|---|---|---|---|---|
| L1 | [screen] | [the question the source doesn't answer] | [the answer currently designed, or "none"] | Product rule · Owner's choice · User evidence (said / reacted / did, N of N) · Shipped pattern · Inferred from §x · Assumption | Open · Hypothesis · Decided | [test with users / ask a customer / write into PRD §x / ask eng / ask legal] | [R-ID · ticket · test case IDs] |

Keep IDs stable across revisions. Update rows in place; don't renumber.

**Row types.** Most rows are about a screen. Mark a row **Dependency** in the Screen column when it's something that must already be true for the design to work (data filled in, one login per person, a habit users have).

**Status meanings**
- **Open:** nobody has proposed an answer.
- **Hypothesis:** there's a proposed answer, but nobody has chosen it, or it rests on an inference or assumption. A shipped pattern makes it a stronger hypothesis, not a validated one.
- **Decided:** the team chose an answer for the current scope. Record it below with its basis, owner, date, and what would make you revisit it.

## Decisions

| ID | Decision | Basis and evidence | Owner, date | Revisit if | Updated in |
|---|---|---|---|---|---|
| L3 | [what was chosen] | [rule / observation / quote / source] | [name, date] | [signal that would reopen it] | [every screen, doc, ticket and test case changed to match] |

## Known contradictions

| Topic | Source A says | Source B says | Ruling needed from |
|---|---|---|---|
| | | | |

## Suggested PRD edits

- [§section / R-ID] Add: "[exact sentence]". Because: [ledger ID].

## Roadmap bets (for Open and Hypothesis rows worth acting on)

- [L-ID] We believe [change] will [outcome] for [people]. We'll know when [signal].
