# School

By Shirley (Xinyi) Du

A school of a few hundred fish that moves as one, even though no fish is in charge. Every fish follows the same short list of rules and only reacts to the neighbors right around it. The streams, swirls and waves of panic are not programmed anywhere; they emerge.

**Live site:** https://shirleyduu.github.io/Fish-School/

## The rules, in plain language

Each fish can only see about two body lengths around itself, and not directly behind it.

1. **Keep your space.** If a neighbor gets too close, move away from it.
2. **Match your own kind.** Turn toward the direction the fish of your species around you are swimming.
3. **Stay with your own kind.** Drift toward the middle of the fish of your species you can see.
4. **Flee the shark.** If the shark is near, swim away from it and become afraid.
5. **Fear is contagious.** If a neighbor is afraid, you become a little afraid too. Afraid fish swim faster, keep more distance and stop caring about the group.
6. **Shelter by the whale.** If the mother whale is near, swim alongside her and match her pace. Her calm spreads to neighbors, and fear fades faster around her.

Rules 1–3 are Craig Reynolds' boids (1987). Rules 4–6 add two feelings, fear and trust, that pass from fish to fish like a rumor. Because fear only jumps one neighbor at a time, a scare travels outward through the school as a wave, much faster than the shark itself can move.

## Interaction

| Action | What happens |
| --- | --- |
| Click the water | A burst of bubbles: nearby fish are pushed away and get a jolt of fear |
| Shark button (`S`) | A great white makes fast passes through the water, bending toward fish ahead of it, then swims off and comes back; press again and it leaves |
| Mother Whale button (`M`) | A humpback cruises across, again and again, and the fish gather alongside her |
| Drag the shark or the whale | Steer them yourself |
| Style button (`C`) | Switch illustration style: Lagoon, Shoal, Ink |
| Rules button (`R`) | Show the rules on screen |
| `H` | Hide all controls |

## How to read the picture

- Four species share the water: slender mackerel, small sprats, deeper-bodied jacks and round bream. Because fish only align and group with their own kind, the school sorts itself into separate streams, yet a scare still spreads across all of them.
- A scare shows up as a wave of sudden speed and spreading-out that travels through the school.
- The mother whale is drawn at roughly real scale next to the fish, swimming deeper so the school passes over her. She never turns around: she rises and sinks in long curves, swims off one side and comes back in from the other.
- Small, faded fish are farther away; large, dark fish are closer. Bigger fish also keep more personal space.

## Techniques combined

- **Autonomous agents / flocking** (Nature of Code, ch. 5): seek, flee and separation steering forces.
- **Contagion as a cellular-automaton-like rule** (Nature of Code, ch. 7): each fish's fear and trust are updated from its neighbors' previous values, so states spread locally through the group.
- **Fractional Brownian motion** (Book of Shaders, ch. 13): the light bands in the water sway and swell using layered noise.
- **Smooth value noise** (Book of Shaders, ch. 10–11): each fish, the shark and the whale wander slightly using their own noise stream, so no two move identically.
- **Spatial grid**: fish only check the cells next to them, so hundreds of fish run smoothly.

The flat illustration style is drawn entirely in code with canvas paths. The humpback and the great white follow real proportions: the shark is about a third of the whale's length, and both dwarf the school.

## Run locally

It is a single `index.html` with no build step. Open it in a browser, or serve the folder:

```
python3 -m http.server
```

## Credits

Made by Shirley (Xinyi) Du with Claude for a generative systems class. References: Daniel Shiffman, *The Nature of Code*; Patricio Gonzalez Vivo and Jen Lowe, *The Book of Shaders*; Craig Reynolds, "Flocks, Herds, and Schools: A Distributed Behavioral Model" (1987).
