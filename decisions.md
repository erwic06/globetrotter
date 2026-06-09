# Globetrotter — Decisions Log

## Milestone 0: Setup and Planning
- Destination chosen: Hawaii
- Primary audience: Everyone (also me)
- One design decision that reflects the destination: A blue palette with beach scenery, plus a seafood-forward food guide, to capture an authentic, local-leaning Hawaii feel.
- Wireframe format used (hand-drawn / Figma / other): Figma agent, very generic but gave me a first step into thinking about header and image placements which was really helpful later down the line.

## Milestone 1: HTML Structure
- One HTML structure choice and why: Each repeating item (attractions, food entries, gallery photos) is an `<article>` or `<figure>` rather than a `<div>`. An `<article>` is the right tag for a self-contained piece of content that could stand on its own, and using it consistently is what lets a single CSS rule style every card identically later.
- One thing Claude generated that I changed, and why: 
- One place a wireframe guided a structure decision: The placement of the photos is of utmost importance for a travel guide like this, so it was ncie to have a wireframe that guided the placement of these beforehand.

## Milestone 2: CSS Styling
- One color/font choice and why it serves the destination: Headings use Poppins and the palette centers on ocean blue + lagoon teal over a warm sand background.s
- One Claude suggestion I rejected and why: Claude defaulted to a white background for professionality sake but I opted for a sandy color for the background to give it a less sterile "beach" vibe. I like it a lot.
- One style that didn't look right at first and what I changed: Some of the hero text was hard to read at first so I added some gradient behind to make it really pop out of the page.

## Milestone 3: Flexbox Layout
- One Flexbox property choice and why: Cards use `flex: 1 1 <basis>` (e.g. `1 1 280px`) plus `flex-wrap: wrap` on the container. This lets cards grow to fill the row evenly but wrap to a new row once they'd get narrower than the basis, which gives responsive behavior for free before media queries.
- One place Claude's layout didn't match the plan and what I changed: The food entry image (`flex: 0 0 40%` with `height: auto`) made the row as tall as the image, leaving whitespace beside short text. Changed it to a fixed `height: 300px` with `object-fit: cover` so the image crops to a tidy row height instead.
- One layout challenge that required adjusting structure and why: The food entries needed image-beside-text, so each entry's text is wrapped in a `.food-body` div. Making the `.food-card` a flex row lays out the image and that single text container side by side; without the wrapper the heading/address/description would each become separate flex items.

## Milestone 4: Responsive Design
- Breakpoints used and why: `max-width: 1024px` (tablet-and-down, light hero tweaks) and `max-width: 600px` (phones, the real layout shifts). Desktop is the unqualified base since the Flexbox cards already wrap on their own; the queries only override what doesn't fix itself.
- One section where mobile needed to feel genuinely different: The food guide switches each entry from image-left/text-right to a stacked card (`flex-direction: column`, image full-width on top). A 40%-wide image next to text is unreadable on a phone, so the image/text relationship changes rather than just shrinking.
- One Claude suggestion accepted/rejected and why: Kept `max-width` (desktop-first) queries instead of rewriting to mobile-first, because the base styles were already built for desktop and the cards wrap responsively; a full mobile-first rewrite would have been churn for no visible gain.

## Stretch Features
- Custom Styling: Added Google Fonts (Poppins + Lato) and used CSS properties beyond the basics: custom properties (`--ocean`, etc. in `:root`), `object-fit: cover`, and a `linear-gradient` overlay on the hero.