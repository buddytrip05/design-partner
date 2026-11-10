# [Product or feature] — End-to-End Test Program

**Scope:** [surfaces covered]. Built from [tickets, PRD, design, system map, PM answers] as of [date].
**Source precedence where they disagree:** [e.g. tickets, then PRD, then wireframes].

**Totals:** [n] test cases in [n] areas · [n] open questions ([n] still open).

## 1. How to run this program

Run it top to bottom, or hand areas to different people.

> **Read before testing:** [n] of [n] cases depend on work that is not started or blocked, and [n] have no single expected result yet. Mark those Blocked, not Fail, until the build or ruling lands.

### Order

1. Load the test data in section 4. Ask engineering to seed the rows marked Eng.
2. Run Totals reconciliation first, before anything changes the data.
3. Run [surface areas].
4. Run [navigation areas].
5. Run Cross-surface updates last; they change the data.
6. Reset the test data before a second pass.

### Recording a result

- **Pass:** every expected result happened.
- **Fail:** any expected result didn't. Write what you saw in Notes (first line = issue title; add a recording or screenshot link), then log an issue. If a similar issue exists, add your note to it.
- **Blocked:** can't run yet: not built, test data missing, or the expected result is undecided.
- **N/A:** doesn't apply to this account or setup.
- Where a case says "Record", write what happened in Notes even if you mark Pass.

### Fields on each case

| Field | Meaning |
|---|---|
| ID | Area prefix + number |
| Priority | High / Med / Low |
| Build status | Least-ready status of the case's tickets as of [date]: Built, In QA, In dev, Not started, Blocked, No ticket |
| Definition | Defined · Inferred · Sources conflict · Not defined |
| Tickets | Keys with status on [date] |
| Before you start | Preconditions and test data |
| Steps | What to do, in order |
| Expected | What must happen for a Pass |
| Open questions | Linked items in section 5 |

## 2. Test areas

| Area | Prefix | Cases | Best run by | What it covers |
|---|---|---|---|---|
| [Login and navigation] | NAV | | Anyone | |
| [Surface] | | | [role] | |
| Totals reconciliation | TOT | | Detail-minded tester | Every count and sum against the test data, and across pages |
| Cross-surface updates | SYN | | Two testers, two browsers | A change on one page shows on every other page |
| Browser navigation | BRW | | Anyone | Back, Forward, refresh, bookmarks, new tabs |
| Responsive layout | RSP | | Anyone | |

## 3. Test cases

### [Area name] ([PREFIX]) — [n] cases

[What it covers.] Best run by: [who].

| ID | Title | Priority | Build | Definition |
|---|---|---|---|---|
| XXX-01 | | | | |

#### XXX-01 · [Title]

**Priority:** [High] · **Build status:** [Built] · **Definition:** [Defined]
**Tickets:** [KEY-123 (Done)]
**Open questions:** [OQ-01]

**Before you start:** [where you are; which test data; cases to run first]

**Steps**

1. [One action.]

**Expected**

- [Observable result. Exact copy in quotation marks.]
- [If undecided: "Not specified. Record."]

**Result:** ☐ Pass ☐ Fail ☐ Blocked ☐ N/A
**Tester / date:**
**Notes:**

## 4. Test data

Load on a clean test account before running Totals cases. D means the day you run the tests.

> **Engineering seeds:** rows marked Eng can't be created in the app. **Handle with care:** [anything a tester could do that spoils the data].

### Actors

| Actor | Type | Use |
|---|---|---|
| [A] | | Owner of [items] |
| [C] | | Has nothing; used for empty states |

### Records

| ID | [State] | Owner | Amount | Setup note | Seed |
|---|---|---|---|---|---|
| | | | | [just inside / outside a time window] | Eng |

### Expected totals

What each count and sum should show right after setup.

| [Scope: all] | Count | Amount |
|---|---|---|
| | | |

## 5. Open questions

### Still open

| ID | Priority | Status | Question | Answer so far | Still open | Affects |
|---|---|---|---|---|---|---|
| OQ-01 | | Open · Partly answered · Pending eng | | | | [case IDs] |

### Closed

| ID | Priority | Question | Answer (who, date) | Affects |
|---|---|---|---|---|

## 6. Issues and results

**Issues log**

| ID | Title | Case | Area | Severity | What happened | Expected | Steps | Browser / device | Evidence | Logged by, date | Status | Tracker key |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| ISS-001 | | | | High/Med/Low | | | | | | | New · Confirmed · In tracker · Fixed – retest · Closed · Duplicate · Not a bug | |

**Progress**

| Area | Pass | Fail | Blocked | Not run |
|---|---|---|---|---|

**Sign-off bar:** [e.g. all High cases pass; no open High issues; every Not defined case has a ruling].
