# Globetrotter — Decisions Log

## Milestone 0: Setup and Planning
- Destination chosen: Hawaii
- Primary audience: Everyone
- One design decision that reflects the destination: A blue/green palette with beach scenery, plus a seafood-forward food guide, to capture an authentic, local-leaning Hawaii feel.
- Wireframe format used (hand-drawn / Figma / other): _TODO: add wireframe images to wireframes/_

## Milestone 1: HTML Structure
- One HTML structure choice and why: Each repeating item (attractions, food entries, gallery photos) is an `<article>` or `<figure>` rather than a `<div>`. An `<article>` is the right tag for a self-contained piece of content that could stand on its own, and using it consistently is what lets a single CSS rule style every card identically later.
- One thing Claude generated that I changed, and why: _TODO: fill in once you review/adjust the generated markup._
- One place a wireframe guided a structure decision: _TODO: tie a specific layout (e.g., the 3-up highlight grid on Home) back to your wireframe._

Notes:
- Shared `header`/`nav` block is duplicated across all four pages because plain HTML has no include/templating; a nav change must be made in all four files.
- The gallery uses `figure`/`figcaption` so each caption is semantically bound to its image as one unit, not a loose paragraph sitting near an `<img>`.

## Milestone 2: CSS Styling
- One color/font choice and why it serves the destination: Headings use Poppins and the palette centers on ocean blue + lagoon teal over a warm sand background. The blue/teal reads as Pacific water while the sand keeps it from feeling cold or clinical, matching the "fresh, warm, easygoing" intent.
- One Claude suggestion I rejected and why: _TODO: e.g., rejected a pure-white background in favor of warm sand so the page feels beachy rather than sterile._
- One style that didn't look right at first and what I changed: _TODO: e.g., hero text was hard to read over bright photos, so a bottom-up dark gradient was added behind it._

Notes:
- Palette is stored as CSS custom properties in `:root` so colors live in one place and can be tuned globally via `var(--name)`.
- Hero readability handled with a `linear-gradient` overlay rather than darkening the image itself, keeping the photo visible.
- Layout deliberately left block-level here; rows/columns are introduced with Flexbox in Milestone 3.

## Milestone 3: Flexbox Layout
- One Flexbox property choice and why: Cards use `flex: 1 1 <basis>` (e.g. `1 1 280px`) plus `flex-wrap: wrap` on the container. This lets cards grow to fill the row evenly but wrap to a new row once they'd get narrower than the basis, which gives responsive behavior for free before media queries.
- One place Claude's layout didn't match the plan and what I changed: The food entry image (`flex: 0 0 40%` with `height: auto`) made the row as tall as the image, leaving whitespace beside short text. Changed it to a fixed `height: 300px` with `object-fit: cover` so the image crops to a tidy row height instead.
- One layout challenge that required adjusting structure and why: The food entries needed image-beside-text, so each entry's text is wrapped in a `.food-body` div. Making the `.food-card` a flex row lays out the image and that single text container side by side; without the wrapper the heading/address/description would each become separate flex items.

Notes:
- Spacing between flex items uses the `gap` property instead of per-item margins (cleaner, no leftover trailing margin).
- Header uses `justify-content: space-between` + `align-items: center` to put the logo and nav on one line.

## Milestone 4: Responsive Design
- Breakpoints used and why: `max-width: 1024px` (tablet-and-down, light hero tweaks) and `max-width: 600px` (phones, the real layout shifts). Desktop is the unqualified base since the Flexbox cards already wrap on their own; the queries only override what doesn't fix itself.
- One section where mobile needed to feel genuinely different: The food guide switches each entry from image-left/text-right to a stacked card (`flex-direction: column`, image full-width on top). A 40%-wide image next to text is unreadable on a phone, so the image/text relationship changes rather than just shrinking.
- One Claude suggestion accepted/rejected and why: Kept `max-width` (desktop-first) queries instead of rewriting to mobile-first, because the base styles were already built for desktop and the cards wrap responsively; a full mobile-first rewrite would have been churn for no visible gain.

Notes / debugging:
- Hit a bug where the nav didn't wrap on phones and stretched the page. Cause: when the header became a column, the nav list shrank to its content width, so `flex-wrap` had no boundary to wrap against. Fix: `width: 100%` on `.nav-list` in the mobile query.
- Verified `document.documentElement.scrollWidth === window.innerWidth` (no horizontal overflow) at 500px, 768px, and 1200px across all four pages.

## Stretch Features
- Custom Styling: Added Google Fonts (Poppins + Lato) and used CSS properties beyond the basics: custom properties (`--ocean`, etc. in `:root`), `object-fit: cover`, and a `linear-gradient` overlay on the hero.
- (Not yet done: embedded map/video, CSS Grid, dropdown nav, newsletter form, deployment.)