# Worked example: Kid's Shelf

This example comes from the workshop "Every PM Is a Designer" (BPM Dallas, November 2026). Kid's Shelf is a feature of a family book-club app: parents track the books their kids own, and relatives use a shared gift page so nobody buys a duplicate. Families, books and names below are sample data.

Use this example to calibrate depth and tone. Don't copy its content into other products.

## The PRD line

> §7.2 "Select all in this series" selects the visible items for review; it never adds blindly.

It reads as complete. It isn't.

## Pass mode, step 2: the baseline

Built as a minimal baseline of exactly what the PRD says (in the workshop, deliberately in document order), one tap on "Select all" checked a book the family already owns and one a relative had already reserved as a gift. The PRD has good duplicate rules elsewhere (badges, warnings, a review tray), but nothing says whether owned or reserved books can be picked in a bulk select.

## Pass mode, step 3: the questions it exposed

Walking the user story ("As a parent, I want to add every Benny Bramble book we have, with as few taps as possible, so our digital shelf matches our real one and we don't receive duplicates") showed that one "Select all" button hides three different jobs:

1. **"We own most of these."** Select all, then un-check the gaps. Fast, but it also checks books already on the shelf. The duplicate rules cover this case.
2. **"Not the ones we don't have."** Unowned books get marked as owned unless someone un-checks them. The duplicate rules can't help: there's no copy to match.
3. **"A new one comes out."** Is the series still complete? Nothing tells the parent.

## Pass mode, step 4: reference brief (excerpt)

| Reference | Evidence access | Problem it solves | What to borrow | Why it might not fit us |
|---|---|---|---|---|
| Shopify product picker | Inspected directly (Mobbin) | Picking many while skipping some | Partly checked parent row; unavailable items visible but locked | Merchants pick variants; parents pick stories |
| Crate & Barrel registry | Inspected directly (Mobbin) | Showing guests what's left to buy | "6 total · 1 purchased · 5 remaining" summary | Registries track quantities; we track single titles |
| Food-delivery order trackers | Inspected directly (Mobbin) | Showing what happens after you order | A step timeline on every order | Food arrives in minutes; gifts take weeks |

(In a real brief, the source locator column would hold the Mobbin links or screenshot IDs.)

## Pass mode, step 5: the proposed answer

Owned and reserved books stay visible but locked, and the button says what it really does: **"Select the 8 you don't have."** Pattern: Shopify's nested select.

Note that this answer still carries an assumption (that "don't have" means "want to add"), which is exactly ambiguity #2 above. That's why it's a hypothesis, not a decision.

## Other findings from the same pass

- **A contradiction.** The gifts screen copy (§7.10) says a surprise gift's "details" are hidden until it arrives; decision D-10 says surprise mode never hides that a book is covered. On one card, you can only do one. If the title is hidden, a parent can buy the same book. Fix: show the title; lock only the giver's name and note.
- **A missing screen.** Decision D-11 says clicking a store link doesn't count as buying; only the giver tapping "I bought it" does. No screen ever tells the giver. Fix: a confirmation screen with a four-step timeline (Reserved → Buy it anywhere → Tap "I bought it" → It lands on the shelf), borrowed from food-delivery trackers.

## The ledger (excerpt)

| ID | Screen | Open question | Current answer on screen | Basis | Status | Next step |
|---|---|---|---|---|---|---|
| L1 | Adding a series | Can owned or reserved books be selected? | No, locked | Shipped pattern (Shopify picker) | Hypothesis | Write into §7.2; test with parents |
| L2 | Gift page | What does a giver see first? | "Already have it?" title check | Shipped pattern (registries) | Hypothesis | Test with givers |
| L3 | Surprise gift | Can parents see the title? | Yes; giver and note hidden | Product rule (PRD D-10) | Decided | Fix §7.10 copy |
| L4 | After reserving | Does the giver know a store click isn't buying? | Four-step timeline | Shipped pattern (order trackers) | Hypothesis | Test with givers |
| L5 | Second device | How does a giver find their hold again? | Emailed manage link | Assumption | Open | Write into §7.9 |

L3 is Decided because the PRD already had a rule for it, not because users confirmed it. Revisit if parents in testing say seeing the title spoils the surprise.

## Evidence mode: the next step

Comparative test of the assumptions behind L1, L2 and L4: both directions, three or four parents and three or four gift-givers. Parent task: "Grandma dropped off three Benny Bramble books. Add them to the shelf." Watch whether anyone takes the "Select the 8" shortcut and adds books they don't own. Giver task: "Leo's birthday is next week. Find a book he doesn't have, and make sure nobody else buys it."
