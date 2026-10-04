# Holiday presentation sites

Static one-page websites for sharing family trip plans, served on GitHub Pages. Each trip is a self-contained folder; a landing page links them all.

## Layout

```
site/
  index.html            Landing page listing all trips (edit when adding a trip)
  alps-2027/            "The Alps by Train" — Bavaria / Switzerland / Italy, Sept 2027
    index.html          The whole trip page (styles inline, no build step)
    images/             Photos, referenced with relative paths (images/...)
  northern-spain/       "Green Spain" — Madrid / Asturias / Basque Country, Sept 2027
references/
  alps-2027/            Planning docs the trip page was built from:
    trip-logistics.md     car/train/transfer logistics, nights per stop
    trip-activities.md    destinations and activities
    advance-bookings.md   what needs booking ahead, and when
    website-prompt.md     the prompt used to generate the site
DEPLOY.md               Preview + GitHub Pages instructions
```

## Adding a new trip

1. Pick a slug, e.g. `japan-2028`.
2. Create `site/japan-2028/` with an `index.html` and an `images/` folder. Use only relative asset paths (`images/foo.jpg`) so the folder is portable, and include `<meta name="robots" content="noindex">` in the page head.
3. Create `references/japan-2028/` for its planning docs (`references/alps-2027/website-prompt.md` is a good starting template for generating the page).
4. Add a card for the trip in `site/index.html` — there's a commented-out template card in the file.
5. Optionally add a `← Trips` link back to `../` in the trip page's nav.
6. Push to `main`; GitHub Pages publishes it at `.../site/japan-2028/` (see [DEPLOY.md](DEPLOY.md)).

Existing trip pages are never affected by adding a new one — each folder is independent.
