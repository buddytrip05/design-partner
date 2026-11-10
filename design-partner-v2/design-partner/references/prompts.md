# The prompt pack

These prompts carry the core of this skill into any AI tool (Claude, ChatGPT, v0, Lovable, Figma Make, Cursor and others). Share them with users who don't have the skill installed. Fill in the brackets.

## 1. Use on every design prompt

> Using this PRD and its constraints, propose four materially different interaction approaches. Explain each approach's trade-offs and assumptions. Flag unanswered questions instead of silently turning them into requirements.

The last sentence does the heavy lifting: it turns the model into a requirements auditor.

## 2. Research with Mobbin (or any pattern library)

> Search Mobbin for how shipped apps handle [screen or flow]. Pull 5–8 examples. For each: the problem it solves, the interaction worth borrowing, and why it might not fit [product]. Then build [screen] from those patterns and cite the app behind each decision.

## 3. Research for free, with screenshots

> Here are [N] screenshots of [flow] from [apps]. For each: the problem it solves, what to borrow, and why it might not fit us. Then propose two materially different versions of [screen] grounded in them, with trade-offs.

## 4. Screen-by-screen critique

> Walk this flow as [persona] trying to [task]. On each screen, list where they'd hesitate, what they'd misunderstand, and what they'd reach for that isn't there. Propose one fix per issue and flag any fix that changes a requirement.

## 5. Find the gaps in a PRD

> Draw this PRD literally, screen by screen, in the order it's written. Don't improve anything. Then list every question you had to answer to draw it that the PRD doesn't answer: states, edge cases, duplicates, timing, permissions, what happens after the main action, and any two lines that contradict each other on the same screen.

## 6. Write a design brief for a designer

> Turn this PRD and these open questions into a design brief for a designer. Include the problem, the people, success criteria, rules and constraints, edge cases, open questions for design, references with why they might not fit, and a section called "What we're not prescribing". Don't include mockups.

## 7. Plan a small usability test

> From these open questions, pick the two riskiest and write a usability test plan: one realistic task that doesn't use interface words, an intro script, an observation sheet with columns for hesitated, misunderstood and reached for, and five debrief questions. Assume about five participants per round, or three or four per group if there are distinct user groups.

## 8. Grade the output

> Review this design against these checks: requirements covered, states exist, patterns cited, design system applied, questions flagged, accessible basics, sources honest, invented content labeled, no two files disagree. Pass, Fix, N/A or Not verifiable for each, with the exact screen and problem for every Fix, and how to check anything Not verifiable. Then list any decision it made that the source material didn't support.

## 9. Brief a design so it lands the first time

> Design [feature] for [people]. The job of this screen: [one line]. Show [named screens] with these states: [closed, loading, populated, empty, error]. Use these real values verbatim: [lists]. Out of scope: [list]. Do not present these as settled: [open decisions]; show them as labeled placeholders. Also give me a short user flow, the trade-offs, a recommendation, and the decisions product and engineering must make. Before you build, ask me anything that would change the design. When you finish, tell me which requirements are done, partial or missing, what you invented, and what doesn't work yet.

## 10. Read a screenshot before using it

> Here is a screenshot of [what]. Use it for [recreating / structure / content / feel]. Do not carry over [list]. Before building, tell me: what it shows top to bottom, the exact values and labels in it, which of our design-system components each part maps to, which states it doesn't show, and what you can't know from a screenshot.

## 11. List what the design assumes

> List everything that must already be true for this design to work: data that must be filled in, how accounts and logins must be set up, habits users must have, and what must arrive from other systems. For each, say how we'd find out if it's true and what the design does if it isn't.

## 12. Synthesize a customer call

> From this transcript, write: a five-sentence summary leading with what changes a decision; a customer snapshot; takeaways for engineering and for sales; a table of each thing we showed with their reaction and a signal rating (Strong, Conditional, Weak, Change requested, Confirms current design, Unknown); pain points outside this feature; and exact quotes. Mark anything hypothetical as Weak. Write Unknown where they didn't react. Then list which of our open questions this call answers.

## 13. Write an end-to-end test program

> From these tickets, this PRD and this design, write a test program. Group cases into areas with ID prefixes. For each case: priority, build status, how defined the expected result is (Defined, Inferred, Sources conflict, Not defined), preconditions, numbered steps, and observable expected results. Where no source says what should happen, write "Record" instead of inventing an answer. Add a small named test data set with relative dates and an expected-totals table, and a list of open questions with the cases each one affects.

## 14. Draft tickets for engineering

> From this design and spec, draft tickets as a file for my review; don't create them anywhere. Smallest unit per ticket, with copy changes grouped one ticket per page. Each ticket: a one-line plain goal first, background, numbered functional requirements (FR-01…), acceptance criteria in Given/When/Then that name the requirement they prove, an open-questions table (# / Question / Why it matters), non-goals and priority. Flag anything undecided inside the ticket it affects. Don't state a root cause or technical approach as fact.

## 15. Keep everything consistent

> We changed this decision: [old] → [new]. Find every screen, document, ticket and test case in this project that mentions it, update each one, and give me the list of what you changed and anything you couldn't.
