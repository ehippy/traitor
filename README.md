# Traitors' Gambit

A single, random, FFT-style tactics battle in one file. No build, no dependencies.

## Run

```
open index.html
```

(or `python3 -m http.server` + http://localhost:8000)

## How to play

Every load rolls a **new random battlefield** (terrain, elevation, unit rosters, names)
and pits your company of 4 against 4 enemy officers. Win by wiping the enemy out;
lose by losing everyone.

1. **Click one of your units** (blue tokens, bottom-left). Green tiles = movement.
2. **Click a green tile** to move (water costs 2; rocks are impassable).
3. **Choose a command** in the panel:
   - **Attack / Cast** — orange pulsing rings mark valid targets. Hover for damage estimate.
   - **Guard** — halve the next blow this round.
   - **Prayer** (healers) — spend MP to restore HP.
   - **Wait** — end the unit's turn.
4. Every one of your units may act each round. When done, press **End Round** (or `E`).
   The enemy side then acts on its own.
5. **R** or *New Battle* rerolls an entirely fresh field at any time.

## The rules that matter

| Rule | Effect |
|---|---|
| High ground | +20% attack per step of elevation above the target |
| Forest | +15% defense while standing on it |
| Water | walkable, costs 2 movement |
| Hills / rocks | impassable |
| Evasion | chance scaling that softens physical damage |
| Magic | ignores armor, only opposed by evasion |
| Crits | 8% for 1.5× damage |

Fog of war: you see the field around your units; enemy tokens beyond that are hidden
or shown as `?` silhouettes.

## Contents

- `index.html` — the entire game (map generation, pathfinding, AI, rendering, UI).
