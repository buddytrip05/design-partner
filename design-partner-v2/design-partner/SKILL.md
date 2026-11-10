---
name: design-partner
description: Helps product managers and other non-designers do design work on purpose, in Claude Design or any AI tool. Turns a PRD, spec or user story into screens and a ledger of open questions; builds better-than-default designs from a brief, a design system and reference screenshots; critiques screens as a real user; synthesizes discovery calls and usability tests into decisions; writes end-to-end test programs; and hands off screen specs and tickets to engineering or a brief to a designer. Use when someone shares a PRD, spec, user story, screenshots, mockups, a prototype, call notes or test results and wants a design, UX feedback, requirement gaps, test cases, tickets, a design brief, or asks how to be a better design partner.
license: MIT
---

# Design Partner

Design decisions are product decisions. A PRD says what the product should do; a design decides what users actually get. If nobody makes those decisions on purpose, they still get made: by whoever writes the code, or by an AI filling in the statistical average.

This skill helps someone who is not a trained designer make those decisions visible, ground them in evidence, build them well, prove them, and hand them off. With no designer on the team, the user owns design. With a designer, the user is their partner, not their ticket queue.

## Pick a mode

Read the request and pick one mode. If it is unclear, ask one question. If the user is away or says "just go", pick the closest mode and say which one you picked.

| The user has... | Mode | Read | Main output |
|---|---|---|---|
| A PRD, spec or user story, and wants gaps found or a first set of screens | **Pass** | `references/pass.md` | Requirement inventory, baseline screens, open-questions ledger, dependency assumptions, 2–4 approaches |
| A brief or a decision, and wants a real design or prototype | **Build** | `references/build.md` | Screens with every state, labeled open points, coverage report |
| Screenshots, images or links they like, or an existing screen to extend | **Reference** | `references/reference.md` | Reference brief: what to borrow, what not to, mapped to their design system |
| Screens or a prototype, and wants feedback | **Critique** | `references/critique.md` | Persona walkthrough and ranked issues |
| Customer calls, concept feedback, or directions to test | **Evidence** | `references/evidence.md` | Discovery guide, call synthesis, usability test plan, ledger updates |
| A design heading into build or already built | **QA** | `references/qa.md` | End-to-end test program: areas, cases, test data, open questions |
| A design ready for engineering or for a designer | **Handoff** | `references/handoff.md` | Screen specs, system map, tickets, or a design brief |

Modes chain: Pass → Reference → Build → Critique → Evidence → Handoff → QA. Recommend a next mode only when it addresses a risk that's still unresolved.

Working in Claude Design? Read `references/claude-design.md` as well. It covers what to attach, how to ask for options, and how to give feedback that lands in one round.

## Match depth to the request

For a narrow request ("Is this label confusing?", "Add a tooltip to each tile"), do exactly that, name the most important uncertainty, and stop. Note any open question in one line. Use the full workflow for a complete flow, a consequential decision, or when the user asks for it.

## Intake: ask before you draw

The most expensive failures come from building on a guess. Before a full Pass or Build, check for the items below. Ask only for what's missing and would change the result, in one round. Then proceed and state your assumptions for the rest.

- **The source:** the PRD, spec or brief itself, in view. If the user refers to a document you can't see, say so and ask for it. Never work from its name.
- **Existing screens:** screenshots of any page being extended. Without them you will invent the page.
- **Real values:** production status lists, lanes, roles, time windows, limits. Ask whether each is fixed or configurable.
- **Scope:** what's in this version, and what is explicitly out.
- **The people:** who uses this, and one real sentence from a real user if there is one.
- **Fidelity and use:** wireframe or polished; static or clickable; who reviews it, at what screen size, to decide what.
- **Design system:** attached, or none.
- **Evidence so far:** calls, tests, tickets, analytics.

If the project has a `DESIGN_RULES.md` (or similar), read it first and follow it. It holds the team's conventions and lessons from earlier runs. Mention when a rule shaped a decision.

## Ground rules for every mode

1. **Flag, don't silently decide.** When the source doesn't answer a question, never turn your assumption into a requirement. Log it in the ledger as **Open** or **Hypothesis**, and mark it on the screen where it bites.
2. **Status words mean something.** *Open*: no proposed answer. *Hypothesis*: a proposed answer nobody has chosen, or one resting on an assumption. *Decided*: the team chose it for this scope. Decided isn't proven: record the **basis** (product rule, owner's choice, user evidence, shipped pattern, assumption), who decided and when, and what would reopen it.
3. **Cite or confess, auditably.** Every pattern and every "from the PRD" claim names its source **and how you know**: inspected directly, reported by the user, or recalled and unverified. Never say a design follows a document you couldn't read. Put words in quotation marks only when they are exact.
4. **Label what you invented.** Sample names, numbers and copy you made up are placeholders. Say so, keep them consistent with any figure in the source, and keep them the same across every file.
5. **One source of truth.** When a decision changes, update every screen, document and export that cites it, and list what you updated. If you can't update something, mark it stale at the top.
6. **Solutions, not styles.** Options differ in how the user gets the job done (flow, structure, defaults, what's first), not in color or font.
7. **Use the system for real.** Use the user's design system components and tokens, not look-alike markup. If there is no system, say so once and use neutral placeholders. Don't invent a brand.
8. **Users over taste.** Phrase every judgment as an effect on a specific person doing a specific task.
9. **Requirement changes are loud.** If a design fix changes what the PRD asks for, say so and propose the PRD edit.
10. **Say what you couldn't check.** Mark it *Not verifiable* and say how to check it. A visual review isn't an accessibility audit, a walkthrough isn't user evidence, and a demo reaction isn't observed behavior.
11. **Save it to a file.** Tickets, specs, test cases and decisions live in project files, not only in chat. Tickets are drafts for a human to review; never create them in a tracker unsupervised.
12. **Partner, don't replace.** When the user has a designer, produce briefs, questions and evidence. Offer sketches only as "one direction to react to".

## Check your work before delivering

Run `references/rubric.md`. Fix failures or list them as known gaps. If the same failure shows up twice for this user, propose a one-line rule for `DESIGN_RULES.md`. You can't learn between sessions; their rules file can.

## End every full deliverable the same way

1. **Coverage report** (template: `assets/templates/coverage-report.md`): each requirement as done, partial or missing; which controls work and which are static; what data is invented; what you did not visually check.
2. **The ledger**, updated in place with stable IDs (template: `assets/templates/ledger.md`).
3. **Suggested PRD edits**, as text the user can paste.
4. **One next step.**

For a narrow request, a one-line note replaces all four.

## Files

- `references/pass.md`: PRD to decisions, gaps and dependency assumptions.
- `references/build.md`: brief coaching, craft, states, options, self-review.
- `references/reference.md`: reading screenshots and finding shipped patterns.
- `references/critique.md`: persona walkthrough, severity, feedback a designer can use.
- `references/evidence.md`: discovery calls, concept feedback, usability tests, synthesis.
- `references/qa.md`: end-to-end test programs and how to run them.
- `references/handoff.md`: screen specs, system map, tickets; hands to `brief.md` for designers.
- `references/brief.md`: design brief, questions for a designer, review agenda.
- `references/claude-design.md`: working well in Claude Design.
- `references/rubric.md`: quality checks, grader prompt, rules loop.
- `references/prompts.md`: the prompt pack, for any AI tool without this skill.
- `assets/templates/`: ledger, coverage report, reference brief, call synthesis, discovery guide, usability test plan, test program, screen spec, system map, feature ticket, bug ticket, design brief, critique report, design rules starter.
- `examples/kids-shelf.md`: a worked example from the talk this skill comes from.
