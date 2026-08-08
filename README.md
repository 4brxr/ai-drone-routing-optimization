# AI-Driven Drone Routing & Competitive Optimisation

An artificial intelligence project exploring constrained multi-drone routing using biologically inspired optimisation, adversarial search, and game-theoretic decision making.

## Project Overview

The project models a Capacitated Vehicle Routing Problem with Time Windows (CVRPTW) for a fleet of drones operating under battery, service-time, and delivery-window constraints.

The same routing instance and evaluation function are used across multiple AI approaches so their behaviour can be compared consistently.

## Technologies

Python, NumPy, Matplotlib, Genetic Algorithms, Ant Colony Optimisation, Negamax, Alpha-Beta Pruning, Game Theory

## Problem Setup

- 20 delivery requests
- 4 drones
- 100-unit battery budget per drone
- Operating horizon: 08:00–19:00
- Delivery time-window constraints
- Shared payoff function covering distance, service, lateness, and unserved requests

## AI Methods

### Genetic Algorithm

Implemented a population-based optimisation approach using permutation-based route representations, crossover, mutation, selection, and feasibility-aware route decoding.

### Ant Colony Optimisation

Implemented pheromone-based route construction using distance and time-window visibility, pheromone updates, evaporation, and feasibility filtering.

### Adversarial Search

Implemented Negamax with alpha-beta pruning for competitive request selection between two fleets.

Urgency-based move ordering reduced explored nodes from **405 to 291**, a reduction of approximately **28%**, in the recorded depth-4 experiment.

The backed-up search value also improved from **3.11 to 15.03** in that experiment.

### Game Theory

Extended the routing problem using:

- 2×2 strategic payoff matrices
- Best-response analysis
- Nash equilibrium analysis
- Pareto analysis
- Repeated-game strategies

## Experimental Results

For the main GA/ACO experiment:

| Method | Payoff | Total Distance | Late Minutes | Requests Served |
|---|---:|---:|---:|---:|
| Genetic Algorithm | -244.50 | 376.7 | 35.6 | 18/20 |
| Ant Colony Optimisation | -212.38 | 362.4 | 0.0 | 18/20 |

ACO produced the stronger result in the main comparison, serving the same number of requests with shorter total distance and no late minutes.

## Key Takeaways

- Compared biologically inspired optimisation methods on the same constrained routing problem.
- Evaluated exploration/exploitation trade-offs through GA and ACO experiments.
- Demonstrated the effect of move ordering on alpha-beta search efficiency.
- Connected routing optimisation with adversarial decision making and game theory.

## Project File

`drone_routing_optimization.ipynb` contains the complete implementation, experiments, visualisations, and analysis.

## Note

This repository presents the project as a technical portfolio case study. The notebook has been cleaned of student-identification and marking information while preserving the original implementation and recorded results.
