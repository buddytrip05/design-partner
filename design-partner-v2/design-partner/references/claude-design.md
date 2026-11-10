# Working in Claude Design

Read this alongside the mode file when the work is happening in Claude Design. Part 1 is for you, the assistant. Part 2 is what to teach the user, briefly and at the moment it helps: one tip, tied to what just happened.

## Part 1: What you do differently here

**Before building**

- Ask your intake questions as one short form, not a string of chat messages. Every question must change what you build. Skip anything the user already told you.
- Good questions for a new design: fidelity; which screens first; static or clickable; whose view is the default; options or one strong version; what sample data to show; whether to annotate decisions with requirement references.
- If the user's answer points back at their document ("the hardest categories"), look it up and use it in full.
- If a named screen or element doesn't match anything in the project ("the growth map"), ask which one they mean. Don't guess.

**The design system**

- If one is attached, it's binding. Mount its real components and use its tokens; don't hand-draw look-alikes.
- A low-fidelity or grayscale request changes the color, not the system: keep its spacing, corner sizes, type and components.
- After building, check the result against the system's own rules: corner sizes, icon set, button casing, navigation dimensions. List any departure and why.

**Showing work**

- Put options side by side on one canvas with short IDs (1a, 1b, 2a). Put the newest round at the top and leave earlier rounds in place, so the history of the decision is visible.
- For a small change, change only that. Don't tidy neighboring things you weren't asked to touch; suggest them instead.
- Before a large rewrite, keep a copy of the current version and say what changed.
- Use the design's own adjustable settings for genuine either-or questions (show notes or hide them; multiplier or percent) so the user can flip between them.

**Open points and notes**

- Mark open decisions on the screen, next to the thing they affect, and collect them in one list.
- If the user wants annotations, tie each note to a requirement or source line. Check that every note is true of the screen it sits on.

**Saving**

- Tickets, specs, test programs, retros and decisions go into project files. Chat scrolls away and doesn't travel with the project.
- If the user gives a standing instruction ("always call it a Specbook"), offer to save it as a project rule.

**Checking**

- Look at what you built. Make sure each check shows the screen you intended.
- Click the things that are supposed to work.
- In your summary, say what you verified, what you didn't, what's static, and what you invented.

## Part 2: What to teach the user

**Starting**

- Attach the PRD in the first message and say "design to this". A later "also consider the PRD" can't be acted on well.
- Attach a screenshot of any existing page you want extended, and say what to take from it and what to leave.
- Give the real lists (statuses, roles, lanes) up front and say whether they're fixed.
- Name the screens and states you want. "Show closed, loading, populated and no-result" gets all four.
- Say what's out, and what must stay undecided.
- Ask for the non-visual parts in the same message: trade-offs, a recommendation, open questions.
- Say who will look at it, on what screen, to decide what.

**Giving feedback**

- Point at one thing: the screen or option ID, the element by its on-screen title, and the change. "On 2a, remove the link in the My Quoted Volume tooltip."
- Tie it to a requirement or a user when you can: "A4 doesn't meet requirement X because Y", or "A rep on a phone can't reach this."
- Supply the copy, or say "draft it and I'll edit".
- Comment directly on the element when that's quicker than describing it.
- After the first build, click through every screen before moving on. Gaps found now are cheap.

**Keeping things straight**

- When a decision changes, say "update everything that mentions this" and ask for the list of what was updated.
- Ask for tickets and specs as files.
- When you correct the same thing twice, ask for it to be saved as a rule.
