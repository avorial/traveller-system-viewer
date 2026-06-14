# Traveller System Viewer

A browser-based visual system viewer for Traveller worlds.

The app loads canonical world data from [Traveller Map](https://travellermap.com),
expands the system procedurally, and renders it with custom planet and star
artwork. It is designed for quick campaign use: enter a sector and hex, generate
a visual system, then export the result for notes, handouts, or VTT use.

## Features

- Traveller Map lookup by sector and four-digit hex.
- Cinematic system view using image-based planet and star assets.
- Perspective orbital map with projected orbit ellipses, grid, AU labels, and
  local moon orbits.
- Seeded procedural names so players using the same seed see the same generated
  body names.
- UWP and PBG translation panel for fast referee reference.
- SVG tab export and PNG download.
- Static-site friendly: no build step and no server required for GitHub Pages.

## Use

Open `index.html` in a browser, or use the published GitHub Pages site.

Default example:

- Sector: `Solomani Rim`
- Hex: `0233`
- World: Jardin

Use the controls at the top of the page to switch between the cinematic view and
the orbital view. The name seed controls generated world and moon names; keep the
same seed for repeatable results across sessions.

## Data Model

The current app uses Traveller Map as the canonical source for the mainworld:

- name
- sector and hex
- UWP
- PBG
- remarks
- allegiance
- stellar string

The rest of the system is procedurally filled in by the browser. Body counts are
guided by Traveller Map data where available, but secondary worlds, moon details,
and orbital spacing are still display-oriented approximations.

## Roadmap

The next major improvement is to use
[traveller-world-gen](https://github.com/Elured-code/traveller-world-gen) as the
system data generator and keep this project focused on visualization.

That would let this viewer render richer and more rules-grounded data:

- World Builder's Handbook style orbit slots.
- Real secondary world and moon profiles.
- Gas giant and belt detail.
- Orbital periods, eccentricity, and inclination.
- JSON import/export for generated systems.

In that model, `traveller-world-gen` provides the system JSON and this app
provides the visual presentation using these planet and star graphics.

## Project Structure

- `index.html` - single-page app, renderer, Traveller Map loader, and export tools.
- `planet/` - planet artwork used by the renderer.
- `stars/` - star artwork used by the renderer.
- `.github/workflows/static.yml` - GitHub Pages deployment workflow.

## Notes

This is an unofficial fan project for use with Traveller. Traveller is owned by
Mongoose Publishing. This project is not affiliated with or endorsed by Mongoose
Publishing.
