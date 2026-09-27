# A programmable bot game — players write the bots, and the bots play

Players write code for their bots, upload it, and the bots play on their own in one shared world. My
server runs every player's bot once a second, each sealed in its own sandbox, so a broken or hostile
bot can't hurt the game. It's built for 24 programming languages; Python, JavaScript and TypeScript
run live today.

Designed and built solo over ~10 months by Andreas Sjögren. I make every design decision and review every change; AI coding agents write code under checks I set up.

Backend .NET engineer. A write-up of my ongoing passion project, which I intend to finish; no buildable source ([why](#why-there-is-no-source-here)).

![The world as a bot sees it: eroded terrain, a fog-of-war clearing around the colony, a hatchery, and a procedurally-legged drone](media/04-tuned.png)

## What I built

- **A server that runs everyone's code, every second.** A bot that runs past 200 ms is cut off; it
  loses its turn, never the game.
- **Fast enough for a crowd.** Each bot answers in 1–5 ms, down from 50–100 ms.
- **No peeking through the fog of war.** Hidden enemy units are never sent to a player.
- **A 3D world to watch.** A Unity client with procedural terrain and creatures, and a browser view
  with nothing to install.
- **Four game engines tried, one kept.** Godot, Unity 2D and Unreal came before the Unity 3D world
  you see here.

<table><tr>
<td width="33%"><img src="media/evo-1-godot-hex.webp" alt="The first world: a 2D hexagonal map in Godot"><br><sub>Nov 2025 — Godot, 2D hexagons</sub></td>
<td width="33%"><img src="media/evo-4-unity3d-terrain.webp" alt="Eroded 3D terrain in the Unity editor"><br><sub>May 2026 — Unity 3D terrain</sub></td>
<td width="33%"><img src="media/evo-6-colony-clearing.webp" alt="A colony's lit clearing in dark terrain"><br><sub>Jun 2026 — a colony's clearing</sub></td>
</tr></table>

## By the numbers

| | |
|---|---|
| Languages the sandbox is built for | 24, with 3 live today |
| Automated tests | 1,850 passing |
| Server code | ~80,000 lines of C# |
| Built | solo, ~10 months, 379 commits |

## Explore

- **[The game and its world](docs/the-game-and-its-world.md)** — how it looks, and how it got that
  look.
- **[Running strangers' code safely](docs/running-strangers-code-safely.md)** — untrusted bots every
  second, without breaking the game or seeing too much.
- **[What happens every second](docs/what-happens-every-second.md)** — the loop that turns every bot's
  orders into one fair result.
- [Player API reference](https://edes0.github.io/programmable-bot-game/player-api/) (live)

## Stack

.NET 10 · ASP.NET Core · EF Core · MediatR · Docker · WebSockets / SignalR · xUnit ·
BenchmarkDotNet · Unity 6 (URP, HLSL) · GitHub Actions

## Why there is no source here

Keeping the source private is a decision, not an omission. The engine is a game I intend to keep
building and eventually run, and publishing it would mean publishing a working server that anyone
could stand up as their own. So this repository carries the parts that survive being read rather than
executed: architecture, protocols, decisions, measurements, and short excerpts of the real code —
quoted with the path they came from, so you can see what the code actually looks like without
receiving a copy of it.

Names in the code excerpts are changed from the private repository; the code is otherwise as written.

If you are evaluating me and want to read more of it, ask — [sjogrenandreas@live.se](mailto:sjogrenandreas@live.se).

## Licence

Prose, diagrams and images: CC BY-NC-ND 4.0. Code excerpts: all rights reserved, reproduced here
for illustration only. See [LICENSE.md](LICENSE.md).

---

**Andreas Sjögren** — [sjogrenandreas@live.se](mailto:sjogrenandreas@live.se) · [github.com/Edes0](https://github.com/Edes0)
