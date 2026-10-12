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

## Adaptive difficulty

The title and pause screens have a slider for the win rate the game should aim for, from 50% (tougher) to 95% (gentler). A weighted up-down staircase (Kaernbach, 1991) then tunes one difficulty level, D from 0 to 1, to hold you at that rate:

- **Trials:** beating an enemy, knocking another sixth off a boss's health, passing a racer or spinning one out counts as a success. Getting hit, falling, crashing, being zapped or being passed counts as a failure.
- **Update rule:** after a success, D rises by step × (1 − p); after a failure, it falls by step × p, where p is the target. The level settles where your success rate equals p. The step starts at 0.12, shrinks by 15% at each reversal, and stops at 0.03 so it keeps tracking as worlds change.
- **What D controls:** a shared clock for enemies, their projectiles, boss attacks, hazard warnings and moving traps (0.55× to 1.45× speed). It also sets how long you stay safe after a hit (2.4 s down to 1.0 s), boss health (0.6× to 1.4×), and the pace of the race rivals.

The pause screen plots the last 60 fights as a staircase: green dots are wins, red are hits, rings mark reversals, and the dashed line is the threshold estimate (the mean level over the last 40 fights, since averaging reversal points is biased when the up and down steps differ). Against a simulated player with a logistic psychometric function, the observed win rate converged to within about 1 point of targets from 60% to 95%. The staircase state is saved in the browser and can be reset from the pause screen.

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
