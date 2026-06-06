# Globetrotter: Hawaii Travel Guide

A personal, multi-page travel guide for Hawaii — built to share the attractions,
seafood, and scenery worth knowing about. Built as Project #1 of the Salesforce FTL
program to practice semantic HTML, CSS, Flexbox, and responsive design.

## Pages

- **Home** (`index.html`) — hero banner, intro, and links into the guide.
- **Top Attractions** (`attractions.html`) — three attractions with photos and descriptions.
- **Food Guide** (`food-guide.html`) — seafood spots, each aimed at a type of traveler.
- **Photo Gallery** (`gallery.html`) — captioned photos using `figure`/`figcaption`.

## Project structure

```
index.html, attractions.html, food-guide.html, gallery.html
css/styles.css      one shared stylesheet
images/             descriptively-named photos (placeholders for now)
wireframes/         page wireframes (add your sketches here)
planning.md         living spec: planning answers + design/layout/breakpoint intent
decisions.md        decisions log, one section per milestone
```

## Running it

It's a static site — open `index.html` in a browser, or serve the folder with any
static server (for example, `python3 -m http.server` then visit `http://localhost:8000`).

## Features

Required:

- [x] Home page with destination heading, intro paragraph, and hero image
- [x] Top Attractions page (3+ attractions: name, photo, description)
- [x] Guide page — Food Guide (3+ entries: title, address, description, link, traveler type)
- [x] Photo Gallery (5+ captioned images)
- [x] Navigation bar with working links, present on every page
- [x] Content organized with Flexbox
- [x] Smartphone-friendly via media queries

Stretch:

- [x] Custom Styling: Google Font (Poppins + Lato) and CSS beyond the basics (custom properties, `object-fit`, `linear-gradient`)
- [ ] Additional Media (embed a map, video, or song)
- [ ] Enhanced Layouts (CSS Grid)
- [ ] Interactive Navigation (dropdown with a nested dropdown)
- [ ] Travel Newsletter Form
- [ ] Deployment

## Notes

- Images in `images/` are placeholders; replace the files (keeping the same names)
  with real Hawaii photos and the markup needs no changes.
- `planning.md` and `decisions.md` were maintained throughout, with planning intent
  written *before* each milestone's code.
