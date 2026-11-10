# Design Partner

**A skill that helps product managers and other non-designers make design decisions on purpose.**

A PRD says what the product should do. A design decides what users actually get. If nobody makes those decisions deliberately, they still get made: by whoever writes the code, or by an AI filling in the average.

Design Partner is an [Agent Skill](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) for Claude. It turns the workflow from the talk *Every PM Is a Designer* into something you can run on your own product:

- **No designer on your team?** It helps you own design: find the gaps in your PRD, ground answers in apps that already shipped, and test before you build.
- **Have a designer?** It helps you be their partner, not their ticket queue: better briefs, better questions, feedback in user terms instead of taste.

## Seven modes

| Mode | Give it | You get |
|---|---|---|
| **Pass** | A PRD, spec or user story | A requirement inventory, baseline screens, every question the PRD doesn't answer, the assumptions the design depends on, 2–4 materially different approaches, and a ledger |
| **Build** | A brief or a decision | A real design with every state, open points labeled on the screen, and an honest report of what's done, partial, static and invented |
| **Reference** | Screenshots you like, or an existing screen | What each reference shows, what to borrow, why it might not fit, mapped to your own design system |
| **Critique** | Screenshots, mockups, a prototype or a URL | A walkthrough as a real persona doing a real task, ranked by severity, each issue flagged if the fix changes a requirement |
| **Evidence** | Customer calls, or directions to test | A discovery guide, a call synthesis with honest signal ratings, a small-sample usability test plan, and ledger updates |
| **QA** | A design heading into build | An end-to-end test program: areas, cases with build status and how well-defined each expected result is, test data, open questions |
| **Handoff** | A design ready to leave your hands | For engineering: screen specs, a system map and draft tickets. For a designer: a brief, questions and a review agenda |

Every full run ends with a **coverage report** and an updated **requirements ledger** with stable row IDs, so open questions stay visible until someone decides them, and every decision records its basis, owner and what would reopen it. Small questions get small answers.

Built for Claude Design, where it also coaches you on what to attach and how to give feedback that lands in one round. It works in any tool that reads skills, with text output where visuals aren't available.

### Built in

- **A quality rubric** the skill runs on its own output: requirements covered, states exist, patterns cited, design-system tokens only, questions flagged, accessible basics. Anything it can't check from the material it was given (like exact contrast from a screenshot) is marked *Not verifiable*, with how to check it.
- **Auditable evidence.** Every borrowed pattern records where it came from and how the skill knows: inspected directly, reported by you, or recalled and unverified.
- **A rules loop.** When the same mistake shows up twice, the skill suggests a one-line rule for a `DESIGN_RULES.md` file in your project, and reads that file on every future run. The model doesn't learn between sessions; your rules file does.
- **Research that works without a budget.** It uses Mobbin if you have it connected, and otherwise free sources: Banani References, VP0, App Store and Google Play screenshots, Apple's Human Interface Guidelines, Material Design and the GOV.UK Design System.
- **A prompt pack** (`design-partner/references/prompts.md`) you can paste into any AI tool, even without installing the skill.

## Try it

After installing, ask Claude things like:

- "Here's my PRD for team invites. Run a design pass on the invite flow."
- "Critique these checkout screenshots as a first-time customer trying to use a promo code."
- "I'm handing the onboarding redesign to our designer next week. Write the design brief."
- "We have two directions for the gift page. Plan a usability test."
- "Here are two discovery call transcripts. What do they settle, and what's still open?"
- "Write the end-to-end test program for this release from the tickets, the PRD and the design."
- "Draft the engineering tickets for this design as a file I can review."
- "Turn this ledger into a decision log and roadmap bets for my leadership review."

## Install

### Claude apps (claude.ai, desktop, mobile)
1. Download `design-partner.zip` from the [latest release](../../releases), or zip the `design-partner/` folder yourself. The folder name must stay `design-partner`.
2. Make sure code execution is turned on (Settings → Capabilities).
3. Go to **Customize → Skills**, click **+**, choose **Create skill → Upload a skill**, and upload the zip.

Skills are available on Free, Pro, Max, Ultra, Team and Enterprise plans. On Team and Enterprise, an owner can turn off uploading your own skills.

### Claude Code
Copy the `design-partner/` folder into your skills directory:

```bash
# for you, in every project
cp -r design-partner ~/.claude/skills/

# or for one project, shared with your team through the repo
cp -r design-partner .claude/skills/
```

### Other agents
Any tool that supports the Agent Skills format can load `design-partner/SKILL.md`. Without skill support, start with the prompt pack.

## What's inside

```
design-partner/
├── SKILL.md                     # modes, intake, ground rules
├── references/
│   ├── pass.md                  # PRD → inventory → gaps → dependency assumptions → approaches
│   ├── build.md                 # brief shaping, craft, states, options, self-review
│   ├── reference.md             # reading screenshots; finding shipped patterns
│   ├── critique.md              # persona walkthrough, severity, feedback a designer can use
│   ├── evidence.md              # discovery calls, concept feedback, usability tests, synthesis
│   ├── qa.md                    # end-to-end test programs and how to run them
│   ├── handoff.md               # screen specs, system map, tickets
│   ├── brief.md                 # design brief, partnering, review agenda (designer handoff)
│   ├── claude-design.md         # working well in Claude Design
│   ├── rubric.md                # quality checks, grader prompt, rules loop
│   └── prompts.md               # the prompt pack, for any AI tool
├── assets/templates/            # ledger, coverage report, reference brief, call synthesis,
│                                # discovery guide, usability test plan, test program, screen spec,
│                                # system map, feature ticket, bug ticket, design brief,
│                                # critique report, design rules starter
└── examples/kids-shelf.md       # worked example from the talk
evals/README.md                  # behavior tests for the skill itself
```

## Principles

1. **Flag, don't silently decide.** Unanswered questions become ledger rows, not quiet requirements.
2. **Cite or confess.** Every pattern names its source and how it was checked, or admits it's a guess.
3. **Say what you couldn't check.** A visual review isn't an accessibility audit, and a walkthrough isn't user evidence.
4. **Solutions, not styles.** Options differ in how the job gets done, not in color.
5. **Users over taste.** Feedback describes what happens to a person doing a task.
6. **Decided isn't proven.** A shipped pattern makes a better hypothesis; every decision records its basis and what would reopen it.
7. **Partner, don't replace.** With a designer in the room, bring the problem and the evidence, not the finished screen.

## Background

This skill comes from *Every PM Is a Designer*, a workshop by Buddy Triplett for BPM Dallas (November 10, 2026), which ran one real PRD through two AI design workflows: drawing the PRD literally, and researching shipped patterns first. The research-first path answered most of the questions the literal draft exposed, found a contradiction in the spec, and surfaced a screen the PRD never had. The worked example in `examples/kids-shelf.md` walks through it.

## Contributing

Issues and pull requests are welcome, especially new worked examples, better research sources, and rules you've learned the hard way. If the skill gets something wrong, add a fixture to `evals/README.md` that reproduces it.

## License

[MIT](LICENSE)
