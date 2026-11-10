# Research: where to find shipped patterns

Look at how shipped products solved a problem before proposing an answer. The point is decisions, not a mood board.

## Sources, in order of preference

Use the best one available and tell the user which you used.

| Source | Cost | Good for |
|---|---|---|
| **Mobbin** (via an MCP connector or skill, if the user has one) | Paid | Real screens and full flows from shipped apps, searchable by pattern |
| **Banani References** | Free | Real screens from popular apps |
| **VP0** | Free | iOS design library with pages written for AI agents to read |
| **App Store and Google Play screenshots** | Free | Any shipped app. Note: these are marketing-picked, not always the real UI |
| **Screenshots the user provides** | Free | Their competitors, their own product, anything they've seen |
| **Apple Human Interface Guidelines, Material Design, GOV.UK Design System** | Free | The rules and components shipped apps follow; strong on accessibility and forms |

Be careful with **Dribbble and Behance**: much of it is concept work that never shipped. Don't present it as proof that a pattern works.

If you can't browse or search in this environment, say so. Ask the user for screenshots, or work from platform guidelines you know well, labeled as such.

## How to search

Search by **problem or pattern**, not by famous app:
- "multi-select list with some items unavailable"
- "gift registry showing what's already purchased"
- "order status timeline after checkout"
- "barcode scanner continuous scanning"
- "onboarding adding family members"

Look at related industries. A gift registry problem might be solved best by a wedding registry, a group-gift app, or even a food-delivery order tracker.

Start with one to three references per question, and expand (up to about eight) only when the evidence is thin or conflicting. More than that turns into a mood board.

## The reference brief

For every reference, record (template: `assets/templates/reference-brief.md`):

1. **Source locator:** the URL, uploaded file name, or screenshot or frame ID.
2. **Evidence access:** *inspected directly*, *reported by the user*, or *recalled, not verified*. Never imply you inspected something you didn't access.
3. **What it shows:** the observed behavior or layout. Screenshots support claims about visible layout and copy, not unseen interaction behavior.
4. **Problem it solves:** in the reference's own context.
5. **What to borrow:** the specific interaction, not "the look".
6. **Why it might not fit us:** differences in users, stakes, scale or rules.

The third column is the one people skip and the one that matters most. Example: a wedding registry tracks quantities ("6 total, 1 purchased"), but a kids' bookshelf only cares about single titles, so borrow the "what's left" summary but not the quantity counter.

## Citing in the design

When a screen uses a borrowed pattern, note it next to the screen: "Pattern: Shopify's nested select (partly checked parent row, unavailable items locked)". This gives stakeholders a receipt ("an app millions of people use does this") instead of a matter of taste.

## Avoiding sameness

Borrow structure; keep the voice and look your own. Shipped patterns are the skeleton, the user's brand and design system are the skin. If every team researches the same apps with the same AI, products converge. The reference brief's "why it might not fit us" column and the user's own design system are the friction that keeps the product distinct.
