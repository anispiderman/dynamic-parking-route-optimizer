# Dynamic Parking Route Optimizer

An AI planning experiment that compares dynamic A* search and tabular Q-learning for parking decisions in a changing city environment.

The simulator generates a staggered road grid with variable travel times, garage prices, capacity, and occupancy. An agent must select and reach a suitable garage while balancing driving time, parking cost, and walking distance to the destination.

## Approaches

### Dynamic A*

Uses Manhattan distance as an admissible heuristic on the generated grid. The agent selects a candidate garage from a weighted cost estimate and recalculates its route when simulated traffic raises the remaining travel time beyond a configured threshold.

### Q-learning

Learns state-to-neighbour action values with an epsilon-greedy policy. Rewards account for travel time, progress toward the destination, parking price, walking distance, and garage availability.

The notebook includes repeated seeded trials that compare aggregate outcomes for both approaches. A DQN extension was explored but not completed and is deliberately excluded from the implementation and results.

## Run

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab notebooks/parking-route-optimization.ipynb
```

Run cells from top to bottom. The comparison cell performs 50 scenarios with 2,000 Q-learning episodes per scenario and can take time to finish.

## Limitations

- The city is a synthetic staggered grid, not a real road network.
- The objective combines differently scaled quantities with fixed weights.
- Traffic changes are simulated rather than learned from real data.
- Garage choice and reward shaping are experimental.
- Results do not establish real-world routing performance.

## Project paper

I wrote an IEEE-format paper explaining the problem, algorithms, experiment design, results, and limitations. 
## About this project

I built this as an artificial-intelligence class group project. The repository focuses on the completed dynamic A* and tabular Q-learning comparison; a DQN extension was explored but was not completed, so it is not included in the implementation or results.
