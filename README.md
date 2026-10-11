# Brick Ninja

A side-scrolling ninja game built from bricks. Game idea by Everett.

A wandering ninja comes to the village of Ishimura, where the Shadow Master has cut the Sun Lantern into eight shards and handed them to his eight guardians. Fight through eight worlds, beat each boss, and bring the light home. The story is told Kurosawa-style: black-and-white storms, hard wipes between shots, taiko drums, and an ending that turns the whole village back to color.

**Play:** https://samuelling.github.io/Brick-Ninja/

The whole game is one file, `index.html`, with no build step. It runs on phones (touch buttons) and computers (keyboard).

## Controls

| Action | Touch | Keyboard |
| --- | --- | --- |
| Move | ◀ ▶ | ← → or A D |
| Jump / double jump | JUMP | Space, ↑ or W |
| Climb | Hold toward a wall | Hold toward a wall |
| Wall jump | JUMP while clinging | Space while clinging |
| Sword | Sword button | Z or J |
| Ninja stars | Star button (hold to keep throwing) | X or K |
| Bow | Bow button (hold to power up) | C or L |
| Pause | II | P or Esc |
| Music on/off | Title or pause screen | M |

A fully charged arrow goes through up to three enemies and sticks in walls, where you can stand on it. Golden bricks give triple stars for a while.

## Worlds

| # | World | Terrain | Boss |
| --- | --- | --- | --- |
| 1 | Sunset Temple | Pagodas and stone pillars | Stone Shogun: stomps and throws bricks |
| 2 | Bamboo Grove | Climbable bamboo everywhere | Bamboo Mantis: flashes red, then dashes |
| 3 | Frozen Peak | Slippery ice, snowball throwers | Frost Yeti: rolling snowballs, icicle ground-pound |
| 4 | Lava Volcano | Lava pits with leaping fireballs | Lava Dragon: fire breath and dives; hit the head |
| 5 | Coral Reef | Underwater, every jump is a swim stroke | King Kraken: tentacles burst from the sand |
| 6 | Desert Ruins | Moving platforms over wide gaps | Scorpion King: stinger and burrowing ambush |
| 7 | Cloud Castle | Cloud ground and springy cushions | Storm Eagle: dive bombs and lightning strikes |
| 8 | Shadow Fortress | Dark, with spikes and shuriken throwers | Shadow Master: teleports, dashes, and splits into clones |

Every world is open from the start. Cleared worlds and the story progress are saved in the browser.

## Making changes

Open `index.html` in a browser to play locally. Levels are defined in the `LEVELS` array, boss behavior in `BOSS`, and the story scenes in `makeIntro()`, `chapterScene()` and `makeEnding()`. All art is drawn in code on a canvas, and all music and sound effects are synthesized with the Web Audio API, so there are no asset files.
