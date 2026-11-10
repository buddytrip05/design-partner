# Design Partner

**A skill that helps product managers and other non-designers make design decisions on purpose.**

A PRD says what the product should do. A design decides what users actually get. If nobody makes those decisions deliberately, they still get made: by whoever writes the code, or by an AI filling in the average.

Design Partner is an [Agent Skill](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) for Claude. It turns the workflow from the talk *Every PM Is a Designer* into something you can run on your own product:

- **No designer on your team?** It helps you own design: find the gaps in your PRD, ground answers in apps that already shipped, and test before you build.
- **Have a designer?** It helps you be their partner, not their ticket queue: better briefs, better questions, feedback in user terms instead of taste.

## Four modes

| Mode | Give it | You get |
|---|---|---|
| **Pass** | A PRD, spec or user story | Screens (or wireframe specs), every question the PRD doesn't answer, a reference brief from shipped apps, 2–4 materially different approaches, and a requirements ledger |
| **Critique** | Screenshots, mockups, a prototype or a URL | A walkthrough as a real persona doing a real task: where they'd hesitate, misunderstand or reach for something missing, ranked by severity, each flagged if the fix changes a requirement |
| **Brief** | A feature you're handing to a designer | A design brief (problem, people, rules, edge cases, open questions, references, and what you're *not* prescribing), questions to ask your designer, and a review agenda |
| **Test** | Two directions, or a ledger full of guesses | A five-person usability test plan: task script, observation sheet, debrief questions, and how to update the ledger afterward |

Every mode ends with an updated **requirements ledger**, so open questions stay visible until real evidence settles them.

### Built in

- **A quality rubric** the skill runs on its own output: requirements covered, states exist, patterns cited, design-system tokens only, questions flagged, accessible basics.
- **A rules loop.** When the same mistake shows up twice, the skill suggests a one-line rule for a `DESIGN_RULES.md` file in your project, and reads that file on every future run. The model doesn't learn between sessions; your rules file does.
- **Research that works without a budget.** It uses Mobbin if you have it connected, and otherwise free sources: Banani References, VP0, App Store and Google Play screenshots, Apple's Human Interface Guidelines, Material Design and the GOV.UK Design System.
- **A prompt pack** (`design-partner/references/prompts.md`) you can paste into any AI tool, even without installing the skill.

## Try it

After installing, ask Claude things like:

- "Here's my PRD for team invites. Run a design pass on the invite flow."
- "Critique these checkout screenshots as a first-time customer trying to use a promo code."
- "I'm handing the onboarding redesign to our designer next week. Write the design brief."
- "We have two directions for the gift page. Plan a usability test."
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
├── SKILL.md                     # modes, ground rules, when to use what
├── references/
│   ├── pass.md                  # PRD → screens → open questions → approaches
│   ├── critique.md              # persona walkthrough, severity, feedback a designer can use
│   ├── brief.md                 # design brief, partnering, review agenda, alignment
│   ├── test.md                  # five-person usability tests and synthesis
│   ├── research.md              # where to find shipped patterns; the reference brief
│   ├── rubric.md                # quality checks, grader prompt, rules loop
│   └── prompts.md               # the prompt pack, for any AI tool
├── assets/templates/            # ledger, reference brief, design brief, critique report, test plan
└── examples/kids-shelf.md       # worked example from the talk
```

## Principles

1. **Flag, don't silently decide.** Unanswered questions become ledger rows, not quiet requirements.
2. **Cite or confess.** Every pattern names its source or admits it's a guess.
3. **Solutions, not styles.** Options differ in how the job gets done, not in color.
4. **Users over taste.** Feedback describes what happens to a person doing a task.
5. **A shipped pattern is a better hypothesis, not a decision.** Users decide.
6. **Partner, don't replace.** With a designer in the room, bring the problem and the evidence, not the finished screen.

## Background

This skill comes from *Every PM Is a Designer*, a workshop by Buddy Triplett for BPM Dallas (November 10, 2026), which ran one real PRD through two AI design workflows: drawing the PRD literally, and researching shipped patterns first. The research-first path answered most of the questions the literal draft exposed, found a contradiction in the spec, and surfaced a screen the PRD never had. The worked example in `examples/kids-shelf.md` walks through it.

## Contributing

Issues and pull requests are welcome, especially new worked examples, better research sources, and rules you've learned the hard way.

## License

[MIT](LICENSE)
