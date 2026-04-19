# Job Scheduling with Genetic Algorithm

A Python implementation of a **Genetic Algorithm (GA)** applied to the **Job Shop Scheduling Problem** — a classic combinatorial optimization problem common in industry (e.g., server farms, manufacturing plants, packet routing).

## Problem Overview

In job shop scheduling, **J jobs** are scheduled across **M machines**. Each job has a fixed number of sequential operations (**N**). The goal is to find an ordering of jobs that minimizes the overall completion time, known as the **makespan**.

Scheduling is performed at the **job level**: once a job ordering is determined, it is applied consistently across all machines. The scheduler maximizes parallelism across machines while minimizing idle time.

## Approach

The GA pipeline consists of:
- **Population generation** — random initial chromosomes (job orderings)
- **Fitness evaluation** — compute the makespan for each chromosome
- **Selection** — select fitter chromosomes for reproduction
- **Crossover** — combine parent chromosomes to produce offspring
- **Mutation** — introduce random variation to maintain diversity

## Scenarios Implemented

| Scenario | Jobs | Operations/Job | Op Time Range | Machines | Optimal Makespan |
|----------|------|----------------|---------------|----------|-----------------|
| R3       | Fixed (Table 1) | — | — | — | 30 |
| R4       | 10 (random) | 3 | [5, 50] | 5 | — |
| R5       | 10 (random) | 5 | [5, 50] | 3 | — |

## Notebooks

- `job_scheduling_ga.ipynb` — Main implementation
- `ga_jobshop_r3_r5_from_scratch.ipynb` — R3 and R5 scenarios built from scratch
- `job-scheduling.ipynb` — Exploratory work
- `playground.ipynb` — Experiments and scratch space

## Project Structure

```
.
├── job_scheduling_ga.ipynb
├── ga_jobshop_r3_r5_from_scratch.ipynb
├── job-scheduling.ipynb
├── playground.ipynb
└── description/
    ├── project-description.md
    └── project-tutorial.md
```