---
name: garden-planner
description: >
  Help anyone plan a home garden from scratch. Use whenever someone wants to design,
  lay out, or plan a garden, yard, balcony, terrace, or plot — choosing what to plant
  where based on light, space, and growth. Gathers each area's lighting and dimensions,
  applies layering / canopy-spacing / root-safety / watering-grouping principles, and
  produces a zone-by-zone planting layout (optionally via the included drag-and-drop
  HTML planner). Triggers include: "plan my garden", "design my yard", "what should I
  plant where", "lay out my beds", "help me with my balcony/terrace garden", "garden
  layout", "planting plan", "which plants for shade/sun", "space my plants".
---

# Garden Planner

A reusable method for turning a bare plot into a concrete, zone-by-zone planting plan.
The output is a layout that says **what** goes **where**, sized to real space and matched
to real light — not a generic plant list.

## When to use
Any request to design or lay out a garden, yard, bed, balcony, terrace, or plot, or to
decide what to plant in a given spot. Works for a single windowsill or a whole property.

## The method

### 1. Map the space into zones
Walk the plot and split it into **zones** — distinct areas that behave differently. A zone
is usually defined by a boundary (wall, path, fence) or by a change in light. For each zone
capture three things:
- **Name** (e.g. "front bed", "side path", "north strip", "balcony rail").
- **Light**: `full` (6+ hrs direct sun), `partial` (dappled / few hours), or `indoor`/`shade`.
  Light is the single biggest constraint — get it right before anything else.
- **Dimensions** in feet: **length × width**. Keep a 1-ft grid in mind; it makes spacing concrete.

Also note fixed features that aren't plantable: house footprint, paving, driveway, stairs,
water features, AC units, and any **underground services** (drain/water/electrical lines).

### 2. Match plants to each zone's light
Never fight the light. Sun-lovers (most flowering shrubs, roses, fruiting vegetables, fruit
trees) need `full`. Foliage, ferns, peace lily, anthurium, most "indoor" plants want `partial`
or `shade`. Putting a sun plant in shade gives a leggy non-flowering plant; a shade plant in
full sun scorches. When in doubt, group by light first, aesthetics second.

### 3. Layer for depth (short → tall)
A garden reads as "designed" when it has vertical layers, especially in a narrow bed:
- **Canopy / structure**: trees, tall palms, large shrubs at the back / centre.
- **Mid layer**: flowering shrubs, ornamental grasses.
- **Colour layer**: perennials and bedding flowers in front.
- **Edge / ground**: groundcover, low annuals, trailing spillers at the front lip.
Tall palms and high-canopy trees can be **underplanted** — only their trunk takes floor space —
while low spreading trees and shrubs compete in the same layer and need horizontal room.

### 4. Space by mature (mid-size) canopy, not nursery size
Plants are bought small and look sparse, tempting over-planting. Space each plant for its
**mid-size canopy diameter** so it doesn't crowd in 2–3 years. Rule of thumb: centre-to-centre
distance ≈ (canopy A radius + canopy B radius). The HTML planner's canopy toggle visualises this.

### 5. Keep roots safe
- Know the depth of any underground pipes. Most shrubs, foliage, herbs, groundcovers and
  vegetables root in the top 1–2 ft and are safe anywhere.
- **Aggressive / deep roots** (ficus/rubber, large trees, bamboo, mango/sapota-type taproots)
  should be kept in **pots or grow-bags**, or offset well away from pipe runs (2–3 ft to the
  side, never directly over), optionally with a vertical root barrier.
- Container specimens (feature pots, bonsai) live off the ground grid — place them on the plan
  as movable pots, not in-ground.

### 6. Group by watering need
Plants on the same irrigation line should want similar water. A practical split:
- **Thirsty** (daily / alternate-day): most flowers, ferns, leafy vegetables, banana.
- **Dry** (weekly, light): bougainvillea-type climbers, succulents, snake plant, ZZ, jade.
- **Deep-soak** (weekly, slow): established fruit trees.
Never share an emitter between a thirsty plant and a drought-lover.

### 7. Produce the layout
Deliver a per-zone plan listing each plant and its grid position, plus counts. Call out any
light mismatches and crowding. If the person has plants already in the ground, **lock those
positions** and design the rest around them.

## The interactive planner (`index.html`)
A single self-contained HTML file (no install, works offline in any browser). The user:
1. Adds each **zone** with a name, light setting, and length × width in feet.
2. Drags **plants** from the palette onto the zone grids (1 cell = 1 ft).
3. Toggles **canopy spread** to check spacing, and the planner **flags any plant whose light
   need doesn't match its zone**.
4. Drags placed plants to move them, drops on the 🗑 to remove, and **exports/imports** the
   plan as JSON. Everything is saved in the browser automatically.

To help someone with it: hand them `index.html`, or walk them through defining zones from a
photo/description, then suggest plant placements following the principles above. The plant
library is generic and grouped by category (Trees, Shrubs & flowers, Foliage & indoor,
Edibles, Ground & climbers); extend the `PLANTS` array in the file for region-specific species.

## Output checklist
- [ ] Every zone has a light setting and real dimensions.
- [ ] Each plant suits its zone's light (no mismatches, or they're flagged).
- [ ] Layers present (structure / mid / colour / edge) where the bed is deep enough.
- [ ] Spacing respects mature canopy (no overlaps unless intentional groundcover).
- [ ] Aggressive roots are potted or offset from underground services.
- [ ] Plants on a shared watering line have compatible water needs.
- [ ] Existing/planted material is kept in place; new plants designed around it.
