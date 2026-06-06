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
_Add entries after implementing Flexbox._

## Milestone 4: Responsive Design
_Add entries after implementing media queries._

## Stretch Features
_Add entries if you implement any stretch features._