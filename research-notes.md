# Research notes

Research pass pending action-time confirmation before submitting prompts in the signed-in ChatGPT Pro browser workspace. Planned independent chats:

1. Evolution strategies and genetic algorithms for game-playing agents.
2. Neuroevolution / NEAT-style mutation and fitness design.
3. Multi-agent simulation architecture and browser visualization.
4. YouTube sources on reinforcement learning and evolutionary game bots.

Claims will be added with source titles, URLs, and a note distinguishing synthesis from independently verified evidence.

## YouTube source scan (public search results)

- [A.I. Evolves to Play Hit the Ball | Neural Network + Genetic Algorithm](https://www.youtube.com/watch?v=4q8QIxY_TKU) — Normalized Nerd. Relevant design pattern: evaluate a population on a concrete game score, retain strong policies, and mutate neural-network parameters between generations.
- [Neuroevolution of Augmenting Topologies (NEAT)](https://www.youtube.com/watch?v=b3D8jPmcw-g) — Connor Shorten. Relevant design pattern: evolve both network parameters and, in a fuller implementation, network structure; use historical markings/speciation to preserve useful innovation.

### Applied to this prototype

The current browser implementation uses a fixed-size policy vector for simplicity, parallel episodes, explicit fitness, elite retention, and mutation. It does not claim to implement full NEAT: topology mutation, crossover, and speciation remain possible next iterations. These notes are a synthesis of the visible YouTube titles/descriptions and should be independently checked against primary papers before treating them as a formal implementation specification.

## Card-game research pass

The rules and strategy scan identified the intended game family as Spider Solitaire / a Spider-like patience variant. The useful mechanics are descending tableau builds, same-suit runs as the movable unit, valuable empty columns, and automatic removal of complete King-to-Ace same-suit runs. The project intentionally uses a one-deck four-run variant rather than claiming to reproduce every rule of standard two-deck Spider.

YouTube examples reviewed in the signed-in browser workflow include:

- [How to Play Spider Solitaire (1 Suit): Rules, Setup and 5 Winning Habits](https://www.youtube.com/watch?v=aY6KnCnZ8Vc) — PlaySolitaire; useful overview of runs, empty columns, stock timing, and progression from one to four suits.
- [Spider Solitaire 2 Suits: Rules, Strategy and 5 Habits](https://www.youtube.com/watch?v=E9SGbAON0zI) — PlaySolitaire; useful explanation of why same-suit building matters as suit count increases.
- [Spider Solitaire F Strategy/Tips](https://www.youtube.com/watch?v=rf_Dqt_jsr0) — The Hidden Levels; strategy framing around revealing and organizing locked cards.

The browser ChatGPT account was not available for a fresh multi-chat submission in this turn because the visible session required a new login. The earlier approved research chats remain part of the project history; this card-game-specific pass is grounded in the visible YouTube results and public rules sources.

## Multi-chat research pass

Four separate ChatGPT Pro research chats were submitted in the signed-in workspace:

- **Evolutionary Game Research Memo** — fitness design, elite selection, mutation, crossover, noisy evaluation, and deceptive fitness.
- **Research NEAT Guidance** — topology mutation, historical markings, speciation, crossover, and scope control for a 16-agent demo.
- **Research Memo Architecture** — browser animation loops, 16 simultaneous canvases, deterministic evaluation, ranking, and telemetry.
- **Research Memo Writeup** — lessons from the two YouTube examples, limitations of demonstrations, and an implementation checklist.

The implementation applies the shared recommendations that are directly relevant at this scale: keep evaluation explicit, preserve elites, mutate offspring, show live ranking, and separate the visual simulation loop from generation transitions. Full NEAT topology evolution is intentionally documented as future scope rather than being implied by the fixed-vector prototype.
