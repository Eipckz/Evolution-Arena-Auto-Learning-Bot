# Evolution Arena — Auto-Learning Multi-Game Bot

Evolution Arena is a dependency-free browser demo of population-based learning. Sixteen agents play independent arenas at the same time, receive fitness from target collection and hazard avoidance, and produce a new generation through elite retention and mutation.

## Live demo

Open `index.html` locally, or serve the folder with:

```powershell
python -m http.server 8765 --directory .
```

Then visit <http://127.0.0.1:8765/>.

The GUI shows all 16 arenas, live ranking, generation number, best score, best-ever score, population count, and an event log. The purple trail identifies the current champion.

## Real run

The media below was captured from the hosted application while it was running. It shows the ready state, live agents, and a generation rollover with a recorded best-ever score.

![Evolution Arena live demo](media/evolution-arena-demo.gif)

| Ready state | Running state | Generation 1 |
|---|---|---|
| ![Ready state](media/evolution-arena-ready.png) | ![Running state](media/evolution-arena-running.png) | ![Generation 1](media/evolution-arena-generation-1.png) |

## What it does

- Runs a population of 16 agents and renders multiple games simultaneously.
- Each agent uses a small neural-style policy to steer toward targets and away from hazards.
- Scores are evaluated over episodes; the top four brains become the next generation's elites.
- Remaining agents are mutated copies, creating evolutionary learning across generations.
- The dashboard shows generation, live scores, best-ever score, trails, and a compact event log.

## Learning behavior and limits

The demo uses a fixed-size neural-style policy vector rather than full NEAT. This keeps the project understandable and runnable from a single HTML file. It is an evolutionary learner, not a proof of general intelligence: performance depends on the chosen fitness function, random seed, episode length, and environment.

“Improvement” is measured by the best fitness observed in each generation and the persistent best-ever score. Because evolution is stochastic, a particular run can temporarily regress; elite preservation prevents the best brain from being discarded when the next population is created.

## Controls

- **Start evolution**: continuously run episodes and generations.
- **Pause**: freeze or resume learning.
- **Single generation**: run one full episode manually.
- **Reset**: start a fresh population.

## Research notes

`research-notes.md` is reserved for source-grounded notes from the requested YouTube and multi-chat research pass. The local game is intentionally dependency-free so it can be tested immediately while research is collected.

## Verification checklist

- JavaScript syntax checked with `node --check`.
- Browser smoke test confirmed 16 visible agent canvases and `16 / 16` live population.
- Runtime demo confirmed score ranking updates and generation rollover from 0 to 1 with a best-ever score recorded.
- No package installation or network service is required to run the demo.
