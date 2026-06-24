# 🌿 Garden Planner

A free, offline, drag-and-drop tool for planning a home garden — plus a reusable AI skill
that captures the method behind it.

You describe your plot as **zones**, each with its **light** (full sun / partial / indoor)
and **size in feet**, then drag plants in. The planner shows how big things get and warns
you when a plant is in the wrong light.

👉 **[Open the planner](index.html)** — or download `index.html` and double-click it. No
install, no account, nothing leaves your browser.

## What it does
- **Add any number of zones** with a name, light setting, and length × width in feet.
- **Drag plants** from a large library (~95 popular home-garden species worldwide), browsable
  by category (Trees · Shrubs & flowers · Foliage & indoor · Edibles · Ground & climbers).
- **Country filter + search** — pick a country to see plants commonly grown in home gardens
  there (plus worldwide staples), or type to search the whole library.
- **Canopy toggle** draws each plant's mature spread so you can space things properly.
- **Light-mismatch warnings** flag any plant whose needs don't match its zone.
- **Move / remove** placed plants by dragging; **export / import** your plan as JSON.
- **Works on mobile** — the layout stacks on small screens, and since drag doesn't work on
  touch, you can **tap a plant then tap a cell** to place it (tap a placed plant to move it,
  or the ✕ to remove it). Drag-and-drop still works on desktop.
- **Auto-saves** to your browser — pick up where you left off.

## Why zones + light + size?
Light is the biggest constraint in a garden, and plants need room for their *mature* size,
not the small thing you buy. Planning per zone, to real dimensions, with light matched up
front, is what turns a pile of plants into a layout that actually works. The full method —
layering, canopy spacing, root safety near pipes, and watering groups — lives in
[`skill/SKILL.md`](skill/SKILL.md).

## The skill
[`skill/SKILL.md`](skill/SKILL.md) is a portable skill file for AI assistants that support
skills. Point your assistant at it (or install it) and ask it to "plan my garden" — it will
gather your zones, light, and dimensions and design a zone-by-zone planting plan using the
same principles, optionally driving this HTML planner.

## Customising the plant library
The plant list is intentionally generic. To add region-specific species, edit the `PLANTS`
array near the top of the `<script>` in `index.html`. Each entry is:

```js
{k:"unique_key", n:"Display name", e:"🌺", c:"Category", l:"full|partial|shade", s:spreadFeet, col:"#hexcolour", co:["India","USA","WW"]}
```

`co` is the list of countries where the plant is a popular home-garden choice; use `"WW"`
for worldwide staples that should appear under every country filter.

## Tech
A single static `index.html` — vanilla HTML/CSS/JS, no dependencies, no build step. Host it
anywhere (GitHub Pages works great) or run it locally.

## License
MIT — see [LICENSE](LICENSE).
