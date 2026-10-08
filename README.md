# Tuflex

**Discover beautiful places across Kenya and East Africa.**

Tuflex (formerly *Situflex*) helps people find parks, hikes, beaches and cultural sites, see where they are on a map, and plan where to go next. It started as a month-long side project, beginning in Kenya and growing across East Africa.

> Forked from [FaithHenzen/Never-Stop-Travelling](https://github.com/FaithHenzen/Never-Stop-Travelling).
> This fork adds: landing page navbar, forms, and the Discover, Map and How it works pages (more coming, one feature at a time).

![Status](https://img.shields.io/badge/status-in%20development-yellow)

## Table of contents

1. [Current status](#current-status)
2. [Pages in detail](#pages-in-detail)
3. [Project structure](#project-structure)
4. [Design and code decisions](#design-and-code-decisions)
5. [Placeholder data](#placeholder-data)
6. [Getting started](#getting-started)
7. [Known limitations](#known-limitations)
8. [Changelog](#changelog)
9. [Credits](#credits)

## Current status

🚧 **Early development.** Building one feature at a time. The page structure is plain HTML; styling and interactivity come next.

**Done so far**
- [x] Landing page navbar
- [x] Forms (login and register)
- [x] Discover page: 8 places across 4 categories, plus a search form
- [x] Map page: place list and embedded map of Kenya
- [x] How it works page: steps, categories and FAQ
- [x] Shared navigation across pages

**Up next**
- [ ] Fix the login flow (currently being debugged)
- [ ] Hero section
- [ ] Write the CSS and apply a look for each category
- [ ] Make search and category filtering work
- [ ] Interactive map with a marker per place
- [ ] Move place data into one shared source
- [ ] Save places and build simple trip plans
- [ ] Photos for each place

## Pages in detail

### Discover (`discoveries.html`)
- Header and nav shared with every page.
- A search form (name or county), in place but not connected yet.
- Four category sections: Wildlife, Hikes, Coast and Culture.
- A card per place with category, name, county, a one-line description and a "View on map" link.

### Map (`map.html`)
- A sidebar listing every place with its county and category.
- Each place links to its exact location on OpenStreetMap, opening in a new tab.
- An embedded OpenStreetMap of Kenya in an `<iframe>`, so no JavaScript is needed.

### How it works (`how-it-works.html`)
- A three-step ordered list: create an account, discover places, see it on the map.
- The four categories you can explore, a short FAQ, and a closing call to action.

### Login and Register
Built with the forms. Login is currently being debugged.

## Project structure

```
Never-Stop-Travelling/
├── index.html           Landing page
├── discoveries.html     Discover places, grouped by category
├── map.html             Place list and embedded map
├── how-it-works.html    How Tuflex works
├── login.html           Log in
├── register.html        Create an account
└── README.md            This file
```

Match the file names above to the ones in your repository.

## Design and code decisions

- **Plain HTML structure first.** The pages are raw HTML with no CSS and no JavaScript, so the look can be written by hand later without untangling the markup.
- **Classes, not ids.** Everything is styled through descriptive class names (`.card`, `.place`, `.step`, `.category-item`), which keeps selectors flat and easy to override.
- **Semantic elements.** `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` and `<footer>`. The how-it-works steps use an ordered list because they are a real sequence, and the FAQ uses a definition list.
- **Category classes.** Each place carries its category as a class (`.wildlife`, `.hikes`, `.coast`, `.culture`), so each category can have its own look.
- **Navigation.** One nav pattern is repeated on every page (Home, Discover, Map, How it works, Login), with `.active` on the current page.
- **Visual explorations to rebuild in CSS:** a coast palette (teal, sand, navy), a savannah look for Wildlife (amber, terracotta, deep brown) and a mountain dusk look for Hikes (indigo, slate, soft gold). These replaced the original theme of green, white, black and red.

## Placeholder data

| Place | County | Category |
|-------|--------|----------|
| Maasai Mara | Narok | Wildlife |
| Lake Nakuru | Nakuru | Wildlife |
| Amboseli | Kajiado | Wildlife |
| Hell's Gate | Nakuru | Hikes |
| Mount Kenya | Nyeri | Hikes |
| Diani Beach | Kwale | Coast |
| Lamu Old Town | Lamu | Culture |
| Fort Jesus | Mombasa | Culture |

Places are written directly into the HTML. Adding one means copying an existing card (Discover) and list item (Map).

## Getting started

```bash
git clone https://github.com/karimiwambui383/Never-Stop-Travelling.git
cd Never-Stop-Travelling
```

Open `index.html` in your browser to view the site. Or serve the folder locally:

```bash
python3 -m http.server 8000
```

then visit `http://localhost:8000`. The embedded map and map links need an internet connection.

## Known limitations

- **Unstyled pages.** There is no CSS yet, so everything uses browser defaults. `.map-frame` needs a width and height before the map shows properly.
- **Search does nothing yet.** The form is markup only.
- **Static map.** Selecting a place opens OpenStreetMap in a new tab and does not move the embedded map.
- **Login bug.** The login flow has a known issue being debugged.
- **Hand-written data.** Places are repeated in two files and must be edited in both.

## Changelog

- **2026-10-08**: Added Discover, Map and How it works pages, shared navigation, and this detailed README. Renamed the project from Situflex to Tuflex.
- **2026-10-02**: Added landing page navbar and forms.

## Credits

Original project by [FaithHenzen](https://github.com/FaithHenzen). Fork maintained by [karimiwambui383](https://github.com/karimiwambui383).

Map data &copy; [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors. Check the original repository for its license terms.