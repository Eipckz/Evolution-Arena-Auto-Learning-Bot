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

## Multi-chat research pass

Four separate ChatGPT Pro research chats were submitted in the signed-in workspace:

- **Evolutionary Game Research Memo** — fitness design, elite selection, mutation, crossover, noisy evaluation, and deceptive fitness.
- **Research NEAT Guidance** — topology mutation, historical markings, speciation, crossover, and scope control for a 16-agent demo.
- **Research Memo Architecture** — browser animation loops, 16 simultaneous canvases, deterministic evaluation, ranking, and telemetry.
- **Research Memo Writeup** — lessons from the two YouTube examples, limitations of demonstrations, and an implementation checklist.

The implementation applies the shared recommendations that are directly relevant at this scale: keep evaluation explicit, preserve elites, mutate offspring, show live ranking, and separate the visual simulation loop from generation transitions. Full NEAT topology evolution is intentionally documented as future scope rather than being implied by the fixed-vector prototype.
