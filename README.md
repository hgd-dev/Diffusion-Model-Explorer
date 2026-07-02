# Participation Diffusion Dynamics Model Explorer

**Diffusion Model Explorer** is an interactive browser simulator for modeling how participation spreads, stabilizes, or collapses in a high-school club. It accompanies the paper *Participation Diffusion Dynamics in Influence-Driven Networks* and turns the paper’s agent-based diffusion model into a visual, explorable system.

The simulator runs entirely in the browser as a single HTML file. There are no dependencies, no build step, and no server required.

***Link:***
[Diffusion Model Explorer](https://hgd-dev.github.io/Diffusion-Model-Explorer/)

## Features

* **Forward prediction mode**
  Configure a club’s network, events, visibility, capacity, and mentoring structure, then simulate how participation evolves across a semester.

* **Single-network sample runs**
  Press **Run sample** to generate one randomized social network and watch the club grow, plateau, or collapse week by week.

* **Monte Carlo ensemble simulations**
  Press **Run simulation** to run many randomized trials and view average weekly outcomes, uncertainty bands, survival probability, and final turnout ranges.

* **Reverse planning mode**
  Set a target end-of-term attendance level, budget constraints, and intervention limits. The planner searches for a lightest-touch strategy that reaches the target.

* **Plan testing**
  After a reverse-mode plan is generated, test it using either one randomized sample or a full ensemble simulation.

* **Interactive network visualization**
  Each core network node represents a simulated student. Color shows motivation, the loyalty arc shows accumulated commitment, and hover readouts show individual motivation, loyalty, fatigue, attendance, and status.

* **Public-body visualization layer**
  The surrounding faint dots represent the wider student body outside the modeled core network. Drawn-in public members show broader reach from events and acquaintance pathways without changing the underlying behavioral equations.

## Running locally

Download or clone the repository, then open:

```text
participation_diffusion_model_explorer.html
```

in any modern browser.

No installation is required.

## GitHub Pages deployment

The simulator is also available at:

```text
https://hgd-dev.github.io/Diffusion-Model-Explorer/
```

## How to use the simulator

### Forward · Predict

Use this mode to explore how a club behaves under different initial conditions and interventions.

Main controls include:

* **Students / network size** — number of simulated core network students.
* **Regime** — collapse-prone or stabilizing dynamics.
* **Friend-group size** — how students cluster into communities.
* **Close ties per student** — within-group influence connections.
* **Bridge ties per student** — cross-group influence connections.
* **Extra acquaintance ties** — additional weak long-range ties.
* **Public population** — size of the wider visual student body around the core network.
* **Events** — week and intensity of enthusiasm pulses.
* **Visibility** — promotion / expressive reach.
* **Capacity** — effective room or format capacity.
* **Scaffolding** — early mentoring support across selected weeks.
* **Trials** — number of randomized runs used in ensemble simulation.

Use **Run sample** to animate one randomized network.

Use **Run simulation** to average many randomized networks and view the expected weekly outcome.

### Reverse · Plan

Use this mode to ask:

> What is the lightest intervention plan that reaches a desired attendance target?

Set:

* target steady attendance,
* weeks available,
* regime,
* maximum number of events,
* maximum event intensity,
* maximum visibility,
* room capacity ceiling,
* whether mentoring is allowed.

Then press **Find a plan**.

If a feasible plan is found, you can test it with:

* **Run sample plan** — one randomized animated realization.
* **Run simulation plan** — aggregate average across randomized networks.

## Reading the visualization

* **Node color** represents motivation on a plasma scale from low to high.
* **Outer ring** marks a core simulated network student.
* **Amber arc** around a node represents loyalty.
* **Small faint public dots** represent the wider student body outside the simulated core network.
* **Lavender public dots** represent students drawn in through events or acquaintances.
* **Central hub** represents the club; its size and glow scale with turnout.
* **Chart line** shows attendance over time.
* **Orange uncertainty band** appears in ensemble mode and shows the middle 50% of trial outcomes.
* **Timeline slider** lets you inspect either one sampled run or the average ensemble state week by week.

## Model relationship

The simulator implements the behavioral equations from *Participation Diffusion Dynamics in Influence-Driven Networks* as an interactive companion.

The following are visualization or interface layers rather than changes to the model:

* the public-body dots surrounding the core network,
* the sample-vs-ensemble interface,
* the averaged timeline display,
* hover readouts and visual encodings,
* the reverse-mode button workflow.

The close-tie and bridge-tie controls affect the randomized graph ensemble. They change how the social network is sampled, not the core behavioral update equations.

## Files

```text
.
├── index.html
├── participation_diffusion_model_explorer.html
├── README.md
├── Paper/
│   ├── Participation Diffusion Dynamics in Influence-Driven Networks - H. Dong.pdf
│   ├── Participation Diffusion Dynamics in Influence-Driven Networks - H. Dong.tex
├── Supplements/
│   ├── Color Readout Supplement - H. Dong.pdf
│   └── Color Readout Supplement - H. Dong.tex
└── LICENSE
```

## Citation

Based on:

```text
Hudson Dong. Participation Diffusion Dynamics in Influence-Driven Networks.
```

## License

* **MIT License**

## Notes

This simulator is intended for qualitative exploration of diffusion regimes, not calibrated empirical forecasting. The outputs should be interpreted as structural tendencies of the model under randomized social-network conditions.
