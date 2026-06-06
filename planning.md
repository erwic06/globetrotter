What location are you building this guide for, and why did you choose it?

Hawaii! I'm building it for Hawaii because despite the large volume of travel guides, only a small fraction give what I believe to be an authentic experience. Similarly I wanted to build a small guide for what I thought the "Eric" experience is so that when I go back I can use it myself to give myself all my nostalgic experiences.

Who is your primary audience? (e.g., first-time visitors, backpackers, families, local residents)

Everyone! First-time visitors, local residents, and probably myself.

What do you want visitors to feel or know after spending 5 minutes on your site?

That I love seafood.

What's one design decision — color, layout, or tone — that reflects your destination's identity?

Gonna be going for lots of blue and green and gonna attach lots of beautiful beach scenery. Classic Hawaii travel guide.

---

## Design Intent (Milestone 2)

**Color palette + three feeling words**
- Ocean blue (`#1b6f8c`) for the deep Pacific, used for the header, links, and accents.
- Lagoon teal (`#2aa9a0`) as a brighter secondary for hovers and highlights.
- Palm green (`#3c7a4f`) as a supporting natural tone.
- Sand (`#f6efe2`) as the page background and warm sun (`#f4a259`) as a small warm accent so it doesn't read as cold.
- Three feeling words: **fresh, warm, easygoing.**

**Typography (heading font / body font)**
- Headings: **Poppins** (Google Font) — rounded, friendly, a little modern; reads as approachable rather than corporate.
- Body: **Lato** (Google Font) — a clean, highly readable sans-serif that stays calm next to the louder headings.
- Reasoning: a relaxed beach guide shouldn't feel like a serious newspaper, but body text still needs to be effortless to read on a phone.

**One visual choice tied to the destination's identity**
- A full-width hero photo with text laid over a soft dark gradient, echoing standing on the sand looking out at the water — the first thing you'd actually see in Hawaii.

---

## Flexbox Layout Plan (Milestone 3)

**Header / navigation**
- Logo on the left, nav links in a row on the right, on the same line. Use `justify-content: space-between` to push them apart and `align-items: center` to vertically center.
- Desktop: links sit in one horizontal row. Smaller screens: allow them to wrap; full single-column stacking is handled in Milestone 4.

**Home — highlight cards**
- Three teaser cards arranged side by side in a row at desktop width, equal width, even gaps. `flex-wrap: wrap` so they drop to fewer-per-row as space shrinks.

**Top Attractions**
- Three attraction cards in a row at desktop, equal width, consistent gap. Wrap to 2-up / 1-up as the screen narrows.

**Food Guide**
- Each entry is a horizontal row: image on the left, text block on the right (image ~40% width, text fills the rest). On narrow screens the image stacks above the text (Milestone 4).

**Photo Gallery**
- A flexible grid of figures, 3 per row at desktop, wrapping naturally. Equal-ish sizing with a consistent gap so it reads as a tidy grid.

**Spacing/sizing notes**
- Use the `gap` property for spacing between flex items (cleaner than margins).
- Cards should grow to fill the row evenly (`flex: 1` with a sensible `min-width` so they wrap instead of getting too skinny).
