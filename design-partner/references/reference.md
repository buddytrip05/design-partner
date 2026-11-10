# Reference mode: borrow decisions, not looks

Use when the user shares screenshots, images or links they like, when they point at an existing screen to extend, or when a risky question could be answered by how shipped products handle it. The point is decisions, not a mood board.

## Part 1: Reading a reference the user gave you

### Ask what it's for

One reference can be used four ways. Ask, or state your reading before you build:

- **Recreate:** this is our current screen; match it, then change only what was asked.
- **Structure:** borrow the layout and flow, not the content.
- **Content:** these are the real fields, values or copy; use them verbatim.
- **Feel:** density, tone, level of polish.

Also ask what must **not** carry over. An old screenshot often contains a feature that's out of scope; if nobody says so, it gets copied in.

### Extract, in this order

1. **What it shows.** Regions top to bottom, what's most prominent, the primary action. Only what's visible.
2. **Real values.** Status lists, column names, labels, numbers. Copy them exactly. Note typos in the source as typos; don't reproduce them and don't silently fix names the team uses.
3. **Hierarchy and density.** What the eye hits first, how much is on screen, what's hidden behind a click.
4. **Components.** Which of the user's design-system components each part maps to. Anything with no match is a gap to raise.
5. **States shown and missing.** A screenshot is one state. List the ones you can't see.
6. **What you can't know.** Behavior, hover, what happens on click, responsive layout. Mark these *Not verifiable from a screenshot*.

### Map it to their system

Borrow structure; apply the user's own colors, type and components. If the reference's style conflicts with their design system, the design system wins, and you say so: "Kept your palette and type; took only the layout from the reference."

### Record it

Use `assets/templates/reference-brief.md`. For each reference: source locator, how you accessed it, what it shows, what to borrow, **why it might not fit**, and what you deliberately ignored. If a reference was supplied and you used nothing from it, say that too.

## Part 2: Finding shipped patterns

### Sources, in order of preference

Use the best one available and tell the user which you used.

| Source | Cost | Good for |
|---|---|---|
| **Mobbin** (via a connector or skill, if the user has one) | Paid | Real screens and full flows from shipped apps, searchable by pattern |
| **Banani References** | Free | Real screens from popular apps |
| **VP0** | Free | iOS design library with pages written for AI agents to read |
| **App Store and Google Play screenshots** | Free | Any shipped app. These are marketing-picked, not always the real UI |
| **Screenshots the user provides** | Free | Competitors, their own product, anything they've seen |
| **Apple Human Interface Guidelines, Material Design, GOV.UK Design System** | Free | The rules shipped apps follow; strong on accessibility and forms |

Be careful with **Dribbble and Behance**: much of it is concept work that never shipped. Don't present it as proof that a pattern works.

If you can't browse or search in this environment, say so. Ask for screenshots, or work from platform guidelines you know well, labeled "recalled, not verified".

### How to search

Search by **problem or pattern**, not by famous app:
- "multi-select list with some items unavailable"
- "gift registry showing what's already purchased"
- "order status timeline after checkout"

Look at related industries. A gift registry problem might be solved best by a wedding registry, a group-gift app, or a food-delivery order tracker.

Start with one to three references per question, and expand (up to about eight) only when the evidence is thin or conflicting.

### The reference brief

For every reference:

1. **Source locator:** URL, file name, or frame ID.
2. **Evidence access:** *inspected directly*, *reported by the user*, or *recalled, not verified*.
3. **What it shows:** observed behavior or layout.
4. **Problem it solves,** in the reference's own context.
5. **What to borrow:** the specific interaction, not "the look".
6. **Why it might not fit us:** differences in users, stakes, scale or rules.

The last item is the one people skip and the one that matters most. Example: a wedding registry tracks quantities ("6 total, 1 purchased"), but a kids' bookshelf only cares about single titles, so borrow the "what's left" summary but not the quantity counter.

## Citing in the design

When a screen uses a borrowed pattern, note it next to the screen: "Pattern: nested select with a partly checked parent row (Shopify, inspected via Mobbin)". This gives stakeholders a receipt instead of a matter of taste.

## Avoiding sameness

Shipped patterns are the skeleton; the user's brand and design system are the skin. If every team researches the same apps with the same AI, products converge. The "why it might not fit us" column and the user's own design system are the friction that keeps the product distinct.
