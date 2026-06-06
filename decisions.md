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
_Add entries after applying styles._

## Milestone 3: Flexbox Layout
_Add entries after implementing Flexbox._

## Milestone 4: Responsive Design
_Add entries after implementing media queries._

## Stretch Features
_Add entries if you implement any stretch features._