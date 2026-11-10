# QA mode: an end-to-end test program anyone can run

Use when a design is heading into build or is already built, and someone needs to prove it works as designed. The output is a test program: test cases grouped into areas, the data to run them against, and the open questions that block them. Template: `assets/templates/test-program.md`.

This is functional testing ("does it do what we decided?"), not usability testing ("can people use it?"). For the second, use Evidence mode.

## Step 1: Gather every source, and rank them

A test case needs an expected result, and expected results come from sources: tickets, the PRD, the design or wireframes, a system map, and answers from the PM. List the sources at the top of the program, with the date you read them.

Sources will disagree. Agree a precedence with the user before writing cases (for example: tickets win for this version, then the PRD, then the wireframes) and state it. When a case rests on that ruling, say so in the case.

## Step 2: Split into areas

An area is a chunk one person can run in a sitting. Give each a short prefix for case IDs, and say who is best placed to run it.

Useful area types:

- **One per surface or page.**
- **Navigation:** login landing, menus, every in-app button and link.
- **Browser behavior:** Back, Forward, refresh, bookmarks, new tabs. Rarely specified; always worth recording.
- **Totals reconciliation:** every count and sum on screen against the test data, and against each other across pages.
- **Cross-surface updates:** change something on one page, check every other page that should reflect it. One case per rule in the system map.
- **Permissions and roles.**
- **Notifications and emails.**
- **Responsive layout.**
- **Empty, loading and error states,** if not covered per surface.

## Step 3: Write the cases

Each case has:

| Field | Meaning |
|---|---|
| **ID** | Area prefix + number (DSH-01). Stable; never renumber |
| **Title** | What's being checked, in plain words |
| **Priority** | High / Med / Low |
| **Build status** | The least-ready status of the tickets behind it: Built, In QA, In dev, Not started, Blocked, No ticket. Dated |
| **Definition** | How sure the expected result is (below) |
| **Tickets** | Keys, with their status on the date read |
| **Before you start** | Preconditions and which test data |
| **Steps** | Numbered, one action each |
| **Expected** | What must happen for a Pass, as checkable bullets |
| **Open questions** | Linked OQ IDs |
| **Result, tester, date, notes** | Filled in when run |

**Definition is the important field.** It stops a tester failing something nobody has decided:

- **Defined:** a source states the expected result.
- **Inferred:** implied by a source but not stated. Say what you inferred from.
- **Sources conflict:** two sources give different results. Name both; ask the tester to record what happens.
- **Not defined:** no source says. The case exists to record behavior for a ruling.

Writing rules:

- One behavior per case. If Expected has an "and also" from a different feature, split it.
- Write for someone who has never seen the product. Name the button as it appears on screen.
- Expected results are observable: exact copy in quotation marks, exact order, exact count.
- Where the outcome is undecided, write "Record" and what to note. Recording is not a failure.
- Derive cases from the design's states: every empty state, every error, every limit, every role difference gets one.
- Note dependencies between cases ("Run after DSH-12: opening the item counts as activity").
- Cover what should **not** happen: the tile that isn't clickable, the account that should be unchanged.

## Step 4: Build the test data

Test cases are only checkable against known data.

- **A small named set:** SB-01, T-01… with exactly the properties the cases need, including one actor with nothing (for empty states) and items just inside and just outside every time window.
- **Relative dates:** "D" is the day of testing, so the set doesn't expire.
- **What needs seeding:** mark rows that can't be created in the app (backdated records) for engineering.
- **An expected-totals ledger:** what every count and sum should show right after setup, overall and per actor. Totals cases check against it.
- **Handling warnings:** anything a tester might do that spoils the data ("don't open SB-09 until…").

## Step 5: Log open questions

Writing cases exposes gaps faster than anything else. Each becomes an open question:

| ID | Priority | Status | Question | Answer so far | Still open | Affects |
|---|---|---|---|---|---|---|

"Affects" lists case IDs, so an answer tells you exactly which cases to update. Link each OQ to a ledger row if one exists; add a row if not. When the PM answers, record the answer and date, update the cases, and move the question to Closed.

## Step 6: Say how to run it

Open the program with:

- **A readiness note:** how many cases depend on unbuilt work, and how many have no single expected result yet. Those get marked Blocked, not Fail.
- **A run order.** Reconcile totals first, before anything changes the data. Run cases that change data last. Say when to reset.
- **Result definitions:**
  - **Pass:** every expected result happened.
  - **Fail:** any didn't. Note what you saw; first line is the issue title.
  - **Blocked:** can't run yet (not built, data missing, result undecided).
  - **N/A:** doesn't apply to this setup.

## Step 7: Manage the run

- **Issues log:** one shared list (ISS-001…) with title, case ID, area, severity, what happened, expected, steps, browser and device, evidence link, who and when. Before logging, check for an existing similar issue and add to it instead.
- **Triage states:** New, Confirmed, In tracker (with key), Fixed – retest, Closed, Duplicate, Not a bug.
- **Several testers:** a case passes only if everyone who ran it passed. Show the roll-up ("2 pass · 1 fail").
- **Progress report:** by area: passed, failed, blocked, not run; open High issues; open questions still blocking cases.
- **Refresh:** build status goes stale. Re-read ticket status before each pass and say when you last did.
- **Sign-off:** state the bar up front (for example: all High cases pass, no open High issues, every "Not defined" case has a ruling or an accepted follow-up).

## Honesty rules for QA

- You wrote the cases from documents. You did not run them. Never report a case as passing unless a person ran it and said so.
- If you can't see current ticket status, say the date of your snapshot.
- A failed case that turns out to be an undecided requirement is a question, not a bug. Move it.

## Fallback

In a tool that can't make an interactive page, deliver the program as one document using the template. Checkboxes and a notes line per case are enough.
