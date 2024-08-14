# Lower Omo Basin Model Repository

## Overview

This repository houses a comprehensive collection of resources for modeling and analyzing the water resource system of the Lower Omo basin. It includes:

- A detailed model configuration for the basin
- Results from multiple optimization runs exploring various management strategies
- Simulation outputs demonstrating the system's behavior under different policies

## Repository Structure

The repository is organized as follows:

- `model/`: Contains `config.yaml` for the Lower Omo basin model and auxiliary files.
- `optimization-results/`: Results from 10 different optimization runs.
  - Population size: 128
  - Simulation horizon: 12 years
  - Timestep: 12 hours
  - Number of generations: 625
  - Each run uses a different random seed
- `simulation-results/`: Simulation results using policies from the first optimization run (random seed 1).
  - Best hydropower policy
  - Best irrigation policy
  - Best environment policy
- `optimization.sh`: Script for running the optimization process.
- `simulation.sh`: Script for running the simulation process.

## Instructions

To replicate the results or run your own simulations:

1. **Install HydroWizard**:
   ```
   pip install hydrowizard
   ```

2. **Obtain Model Configuration**:
   - Clone this repository, or
   - Download the `config.yaml` and auxiliary files from the `model/` directory.

3. **Run Optimization**:
   ```
   hw-optimization -c model/config.yaml [options]
   ```

4. **Run Simulation**:
   ```
   hw-simulation -c model/config.yaml [options]
   ```

For detailed command options, refer to the [HydroWizard documentation](https://hydrowizard.readthedocs.io).

## Using the Provided Scripts

This repository includes two shell scripts to simplify the process of running optimizations and simulations:

1. **Optimization**: Use `optimization.sh` to run the optimization process.
   ```
   ./optimization.sh [NUM_GENERATIONS] [SIMULATION_HORIZON] [INTERVAL_DURATION] [RANDOM_SEED]
   ```

2. **Simulation**: Use `simulation.sh` to run simulations.
   ```
   ./simulation.sh [SIMULATION_HORIZON] [INTERVAL_DURATION] [POLICY_SOURCE]
   ```

Both scripts use default values if no arguments are provided. Refer to the script contents for more details.

## HydroWizard Resources

- [PyPI Package](https://pypi.org/project/hydrowizard/)
- [Documentation](https://hydrowizard.readthedocs.io)
- [Source Code](https://github.com/yugdeep/hydrowizard)

