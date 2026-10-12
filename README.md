# Brick Ninja

A side-scrolling ninja game built from bricks. Game idea by Everett.

A wandering ninja comes to the village of Ishimura, where the Shadow Master has cut the Sun Lantern into nine shards and handed them to his nine guardians. Fight and race through nine worlds, beat each guardian, and bring the light home. The story is told Kurosawa-style: black-and-white storms, hard wipes between shots, taiko drums, and an ending that turns the whole village back to color.

**Play:** https://samuelling.github.io/Brick-Ninja/

The whole game is one file, `index.html`, with no build step. It runs on phones (touch buttons) and computers (keyboard and mouse).

## Controls

| Action | Touch | Keyboard / mouse |
| --- | --- | --- |
| Move | ◀ ▶ | ← → or A D |
| Jump / double jump | JUMP | Space |
| Climb | Hold toward a wall | Hold toward a wall |
| Wall jump | JUMP while clinging | Space while clinging |
| Stomp | Land on an enemy | Land on an enemy |
| Sword | Sword button | Z or J |
| Ninja stars | Star button, or touch where you want them to go | X or K, or click where you want them to go |
| Aim | Touch and hold the game | Hold ↑ or ↓ (with ← → for diagonals) while throwing |
| Bow | Bow button (hold to power up) | C or L |
| Pause | II | P or Esc |
| Music on/off | Title or pause screen | M |

Landing on a bad guy smashes it and bounces you off in a spinning sword slash that hits anything nearby. Landing on a boss knocks off two points of health. A fully charged arrow goes through up to three enemies and sticks in walls, where you can stand on it. Golden bricks give triple stars for a while.

**In the race:** ◀ ▶ steer and the kart speeds up by itself. JUMP hops over trouble, stars spin out the karts ahead, and the sword or bow button uses turbo. Studs on the road refill the turbo meter.

## Worlds

New mechanics build up as the game goes on.

| # | World | What's new | Guardian | Music style |
| --- | --- | --- | --- | --- |
| 1 | Sunset Temple | The basics | Stone Shogun | NES ninja action |
| 2 | Bamboo Grove | Cracked platforms that crumble, climbable bamboo | Bamboo Mantis | Ambient bells |
| 3 | Frozen Peak | Slippery ice, falling icicles, crumbling ice | Frost Yeti | Heroic NES |
| 4 | Lava Volcano | Stone elevators over lava pits | Lava Dragon (rests low after each dive) | Power metal |
| 5 | Coral Reef | Swimming, currents, bouncy jellyfish | King Kraken | Ambient bells |
| 6 | Desert Ruins | Moving platforms, quicksand | Scorpion King | NES ninja action |
| 7 | Thunder Road | A third-person kart race | Raijin the Thunder Rider | Power metal |
| 8 | Cloud Castle | Springs, wind gusts, turning platform wheels | Storm Eagle | Heroic NES |
| 9 | Shadow Fortress | Darkness, spikes, crushers, elevators | Shadow Master | Power metal |

All the music is original and synthesized in the browser. Every world is open from the start. Cleared worlds and the story progress are saved in the browser.

## Making changes

Open `index.html` in a browser to play locally. Worlds are defined in the `LEVELS` array, bosses in `BOSS`, songs in `SONGS`, the race in `initRace()` and `buildTrack()`, and the story scenes in `makeIntro()`, `chapterScene()` and `makeEnding()`. All art is drawn in code on a canvas, so there are no asset files.
