# Handoff mode: give the next person what they need

Use when a design is ready to leave the user's hands. Two audiences, two different packages:

- **To a designer:** they own the solution. Hand over the problem, not a finished screen. Follow `brief.md`.
- **To engineering:** they build what's decided. Hand over decisions, states, rules and tickets. The rest of this file.

If the user has both, write the brief first.

## Before you write anything

1. **Read the ledger.** Anything still Open or Hypothesis that engineering would hit goes in the open-questions table of the ticket it affects. Don't present it as settled.
2. **Read `DESIGN_RULES.md`** for the team's ticket conventions (ID prefix, numbering, required sections). Their rules override the defaults here. If they have no rules and the choice matters, ask.
3. **Check for drift.** Compare the design, the PRD and any earlier documents. List contradictions and get them ruled on, or flag them in the tickets. Handing off two documents that disagree guarantees a wrong build.

## The package

### 1. Screen specs

One per screen: `assets/templates/screen-spec.md`. Purpose, entry points, regions, each element's behavior, every state with its copy, rules, what's out of scope, and which requirements and ledger rows it covers. Copy is exact and in quotation marks.

### 2. System map

`assets/templates/system-map.md`. A table of rules: when *this* changes, *these* surfaces update, in this way. Each rule gets an ID.

Write one whenever a change on one screen should show up somewhere else. It answers the questions screens can't: does this need a refresh, does it write to an activity log, does it send anything. It's also what cross-surface test cases are written from. If the design changes, re-issue the map; a stale map is worse than none.

### 3. Tickets

Feature tickets: `assets/templates/ticket-feature.md`. Bug tickets: `assets/templates/ticket-bug.md`.

**Feature ticket sections:**

- **Summary.** One plain-language goal line first ("Show a list of dealers per brand…"). No context paragraph before it.
- **Job to be done.** When / I want / so I can. Required on the parent story; optional on small child tickets.
- **Background.** What exists, why now, links to the screen spec and design.
- **Functional requirements.** Numbered FR-01, FR-02…, restarting in each ticket so a ticket stands alone. Refer across tickets as "TICKET-ID FR-03".
- **Acceptance criteria.** Given / When / Then, each ending with the requirement it proves, e.g. "(FR-05)". Every FR has at least one. Include the empty, error and permission cases.
- **Open questions.** A table: # (OQ-01) / Question / Why it matters.
- **Non-goals.** What this ticket does not do. Required on the parent story.
- **Priority.**

**Bug ticket sections:** type and component; summary; issue breakdown (Issue 1 / Issue 2 if the report holds more than one); acceptance criteria in Given / When / Then; suspected root cause, **labeled unconfirmed**; unknowns flagged for engineering; linked tickets.

**Splitting rules:**

- Smallest shippable unit per ticket.
- Exception: copy and label changes are grouped, one ticket per page, so engineers don't context-switch.
- When a report could be one ticket or two, ask before splitting.
- Flag gaps inline in the ticket, where they apply, rather than opening with a list of questions.

**Review rules:**

- Tickets are **drafts saved to a file** for a person to review. Don't create them in a tracker unsupervised, and don't leave them only in chat.
- Use a clear placeholder for ticket IDs that don't exist yet (PROJ-XXXX, or the team's prefix). Never reuse the FR format for ticket IDs.
- Give each ticket enough context to be read cold. A reviewer shouldn't need the conversation that produced it.
- Don't state a root cause, an estimate or a technical approach as fact. Those are engineering's.

### 4. Traceability

Add the ticket keys to the ledger rows and the coverage report, so each requirement can be followed: requirement → screen → ticket → test case. A requirement with no ticket, or a ticket with no requirement, is a finding.

## Deliver

1. The files: screen specs, system map, tickets.
2. **A handoff note:** what's decided, what's still open and who owns each question, known contradictions, and what in the prototype is illustrative (invented data, static controls).
3. The updated ledger.
4. One next step: usually QA mode, to write the test program from the same specs.

## Design QA after build

When the build is ready, compare it to the design before formal testing: screen by screen, state by state, copy word for word. List differences as one of: **bug** (build is wrong), **design change** (build is right; update the design and say so), or **question** (nobody decided). Then update the source of truth so the design and the product match again.
