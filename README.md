# Brick Ninja

A side-scrolling ninja game built from bricks. Game idea by Everett.

A wandering ninja comes to the village of Ishimura, where the Shadow Master has cut the Sun Lantern into twelve shards and handed them to his twelve guardians. Fight, climb, race and ride through twelve worlds, beat each guardian, and bring the light home. The story is told Kurosawa-style: black-and-white storms, hard wipes between shots, taiko drums, and an ending that turns the whole village back to color.

**Play:** https://samuelling.github.io/Brick-Ninja/

The whole game is one file, `index.html`, with no build step. It runs on phones (touch buttons and an 8-way d-pad) and computers (keyboard and mouse). Double-tap and pinch zoom are turned off, so quick taps on the buttons never zoom the page in Safari.

## Controls

| Action | Touch | Keyboard / mouse |
| --- | --- | --- |
| Move | D-pad ◀ ▶ | ← → or A D |
| Jump / double jump | JUMP | Space |
| Climb | Hold toward a wall | Hold toward a wall |
| Wall jump | JUMP while clinging | Space while clinging |
| Stomp | Land on an enemy | Land on an enemy |
| Sword | Sword button | Z or J |
| Ninja stars | Star button, or touch where you want them to go | X or K, or click where you want them to go |
| Aim | Point the d-pad in any of eight directions, or touch and hold the game | Hold ↑ or ↓ (with ← → for diagonals) while throwing |
| Special weapon | Special button (hold to keep firing) | C or L |
| Go through a secret door | D-pad ▲, or tap the door | ↑ |
| Pause | II | P or Esc |
| Music on/off | Title or pause screen | M |

Landing on a bad guy smashes it and bounces you off in a spinning sword slash that hits anything nearby. Landing on a boss knocks off a point of health (once every 1.4 seconds). Golden bricks give triple stars for a while.

**In the race (four laps):** ◀ ▶ steer and the kart speeds up by itself. JUMP hops over trouble, stars spin out the karts ahead, and the sword or special button uses turbo. Studs on the road refill the turbo meter.

## World 9: Dragon Falls

A vertical climb up a waterfall, like the Waterfall stage in Contra. Ledges zig-zag up between two walls too slick to cling to; some crumble, some slide, and guards and birds wait along the way. Drop a long way below your last safe ledge and it counts as a fall. At the top, the Stone Oni floats over the arena: it spits fans of fire, and its two stone fists take aim (watch for the shadow) and slam down. Point the d-pad up to throw stars at its head, or jump from the side ledges and stomp it. Its music is neoclassical metal in the Yngwie mould: sweep-picked arpeggios up and down three octaves, pedal-point riffs, harmonic minor runs and a diminished arpeggio spinning over the dominant, over double-kick drums.

## Playing together online

Up to four ninjas can play the same world at once, each on their own phone, tablet or computer. Tap **Play together**, type a name, and **Make a room**. You get a four-letter code; friends tap **Play together**, type the code and **Join** (or open the link from **Send friends a link**). Anyone in the room can pick a world, and it starts for everyone. A friend who joins mid-world drops straight in.

- Everyone plays the same world with their own ninja, in their own colour, with names over their heads, little arrows pointing to friends who are off the screen, and everyone's hearts in the corner.
- Bad guys go after whichever ninja is closest. The more ninjas, the more bad guys: half again as many for each extra player, and bosses get 60% more health per extra player.
- Opening a secret door is shared, and when anyone walks through one, everyone goes in together, side by side. If you're knocked out in a secret room you wait while your friends finish; the room only fails if everyone is knocked out. Everyone who's inside wins the weapon.
- The difficulty staircase becomes a team staircase: every ninja's wins and hits count toward one shared difficulty level.
- Pausing opens the menu, but the world keeps going for everyone else. Thunder Road is raced on your own.

**How it works.** The game connects to a small relay server on Cloudflare (the same Durable Object server Crush Commando uses), which only passes messages around a room. Everyone runs the whole game. In each world, the earliest joiner who's playing it is the *authority*: its enemies, boss and secret room are the real ones, and it sends a snapshot of them ten times a second. Everyone else steers their copy toward the snapshot and sends their hits to the authority; each player checks their own ninja's bumps. If the authority leaves, the next earliest joiner takes over. To use a different server, add `?server=wss://your-server` to the game's address.

## Secret doors and special weapons

Six worlds hide a secret door: a cracked bit of old wall standing in the background on one stretch of ground. Hit it with the sword, a star, a stomp or a special weapon and it crumbles into a glowing doorway. Press ↑ (or tap the door) to go in.

Inside is a corridor room seen from behind the ninja, like the base stages in Contra. Slide left and right, jump and double jump, throw stars down the hall (they aim at whatever you tap, or at the nearest target in your lane), and swing the sword to knock enemy stars out of the air. Each room has three gates. Lantern turrets on the back wall shield the core; knock them all out, smash the core and the wall falls. Grunts run out of side doors, and from the second gate on, spiked balls roll at your feet. Behind the third gate is the treasure: a weapon you can't get anywhere else.

| World | Weapon | What it does |
| --- | --- | --- |
| Sunset Temple | Spread Stars | Five energy stars in a fan |
| Bamboo Grove | Heat-Seeker Missiles | Homes in on the nearest bad guy and explodes |
| Frozen Peak | Chainsaw | Hold to rev it: the blade shreds anything it touches, cuts enemy shots out of the air and grinds bosses down fast, but only up close (an idea from Everett) |
| Lava Volcano | Dragon Flame | A short-range flamethrower, hold to keep it going |
| Desert Ruins | Laser Gun | An instant beam that goes through everything in a line |
| Cloud Castle | Thunder Chain | Lightning that jumps between up to four enemies |

The weapon goes in the special slot, stays when you leave the room, and is saved in the browser. You hold one at a time: winning another room swaps it out, and you can always go back through a cleared door to win an old one again. Getting knocked out in a room just sends you back to the door with the hearts you went in with. The world picker shows which worlds still hide a door.

## The two craziest worlds

**Moon Palace.** Gravity is a little over half of normal, so every jump is huge and floaty, and the gaps are wide to match. Glowing rings on the ground warn where meteors are about to come down at an angle. At the end, the Mochi Rabbit (a giant moon rabbit with a rice-cake mallet) hops at you, lobs balls of mochi, and when it lands from a big hop it pounds the ground and sends ripples of moon dust rolling both ways: jump them.

**Shadow Express.** You run along the roofs of a speeding train, and the screen scrolls on by itself, pushing you along from the left (a little faster when you're doing well). Jump the gaps between cars, hop the crates and vents, climb the double-decker cars, and don't jump into the crackling live wires strung overhead. Fall between cars and you're put back down on the next roof on screen, a heart lighter. On the locomotive, the Kabuto Gunship (a rotor-winged beetle) drops bombs, fires its twin cannons, and skims low along the roof: jump over it.

## Level design that grows with you

Worlds get longer as the game goes on: about 8,400 wide in Sunset Temple, about 12,000 by the Shadow Fortress (the first versions were around 5,600). A *complexity* score rises from world to world and from the start of each world to its end, and it drives everything below:

- Gaps get wider, and more bad guys stand on each stretch, with more of them throwing things.
- **Set pieces** appear between the plain stretches, more often the further you get. Each one unlocks at a certain complexity:
  - **Stepping stones** over a pit. Later on, more of them crumble and one bobs up and down.
  - **A cliff** too tall to jump, so you climb the wall. Early on there's a ledge halfway up; later there isn't, and guards wait on top.
  - **A gauntlet**: a long run packed with bad guys and birds overhead, and later a thrower watching from a ledge.
  - **Stairs** over a pit to a high ledge with a guard and a prize.
  - **A high road** of platforms over a floor of spikes (or hoppers in gentler worlds).
- Bosses get up to a quarter more health by the last world, and Thunder Road is now four laps.
- Dragon Falls is a taller climb, and its ledges get narrower, wobblier and more likely to crumble the higher you go.

The adaptive difficulty below still tunes the bad guys' speed to your win rate, but pits, cliffs and spikes aren't tuned, so the later worlds really are harder.

## Bosses

Bosses are built to be a real fight:

- They have nearly twice their old health, more again with each extra player online, and up to 40% more by the last world.
- Big hits do half damage to a boss: the sword, stomps, missiles, the laser and the thunder chain all hit a boss for half (at least 1). The chainsaw bites for 1 each time the armour drops, so it's the fastest way to wear a boss down if you dare get that close. After each hit, a boss is armoured for a split second (a fifth of a second, shared between players online), so firing everything at once doesn't melt it.
- A boss can only be stomped once every 1.4 seconds, so you can't bounce on its head forever.
- Bosses speed up as they weaken, up to about 40% faster near the end of the fight.
- Get knocked out in a boss fight (playing alone) and the boss gets all its health back; **Keep going** puts you at the edge of the arena to fight it again.

## Adaptive difficulty

The title and pause screens have a slider for the win rate the game should aim for, from 50% (tougher) to 95% (gentler). A weighted up-down staircase (Kaernbach, 1991) then tunes one difficulty level, D from 0 to 1, to hold you at that rate:

- **Trials:** beating an enemy (secret-room turrets and cores included), knocking another sixth off a boss's health, passing a racer or spinning one out counts as a success. Getting hit, falling, crashing, being zapped or being passed counts as a failure.
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
| 9 | Dragon Falls | A vertical climb up a waterfall | Stone Oni | Neoclassical shred |
| 10 | Moon Palace | Low gravity, meteor showers, very wide gaps | Mochi Rabbit | Bright NES |
| 11 | Shadow Express | The screen scrolls by itself along a speeding train; live wires overhead | Kabuto Gunship | Power metal |
| 12 | Shadow Fortress | Darkness, spikes, crushers, elevators | Shadow Master | Power metal |

All the music is original and synthesized in the browser. Every world is open from the start. Cleared worlds and the story progress are saved in the browser.

## Making changes

Open `index.html` in a browser to play locally. Worlds are defined in the `LEVELS` array (the vertical one is built by `buildVertical()`), bosses in `BOSS`, songs in `SONGS`, the race in `initRace()` and `buildTrack()`, the story scenes in `makeIntro()`, `chapterScene()` and `makeEnding()`, the secret doors and their weapons in `SECRETS` and `WEAPONS`, and the corridor rooms in `roomGate()`, `roomUpdate()` and `roomDraw()`. All art is drawn in code on a canvas, so there are no asset files.
