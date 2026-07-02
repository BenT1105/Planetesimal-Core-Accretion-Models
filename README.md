# Planetesimal Core Accretion Models

A Python model for simulating planetesimal-driven core accretion in protoplanetary disks.

## Overview

This code models the growth of planetary embryos through planetesimal accretion while simultaneously evolving the dynamical state of the surrounding planetesimal population.

The current implementation includes:

- A comparison between the planetesimal growth timescales of **Rafikov (2011)** and **Fortier et al. (2013)**.
- Planetesimal eccentricity and inclination evolution following **Fortier et al. (2013)** and **Kaufmann & Alibert (2023)**.
- A simple static protoplanetary disk model.
- Pebble accretion onset, transition, and isolation mass limits from **Lorek & Johansen (2022)**.
- Streaming instability birth masses for embryos and planetesimals from **Johnston et al. (2026)**.
- Planetesimal core accretion following **Fortier et al. (2013)**.
- Built-in plotting functions for visualizing simulation results.

The embryo mass together with the planetesimal eccentricity and inclination are evolved by numerically integrating the coupled ordinary differential equations over **3 Myr** using `scipy.integrate.solve_ivp` with the **RK45** integrator and a maximum timestep of **10 years**. Planetesimals are initialized at the numerical equilibrium eccentricity and inclination obtained using `scipy.optimize.root`, while embryos begin at the streaming instability birth mass.

## Features

- Models planetesimal dynamical evolution including:
  - Gas drag
  - Embryo–planetesimal viscous stirring
  - Planetesimal–planetesimal viscous stirring
  - Turbulent density fluctuations

- Evolves the time-dependent:
  - Embryo mass
  - Planetesimal eccentricity
  - Planetesimal inclination

- Initializes embryos at the streaming instability birth mass and planetesimals at their equilibrium eccentricity and inclination.

- Disk properties can be specified, including:
  - Disk mass
  - Dust-to-gas ratio
  - Temperature profile
  - Turbulence strength
  - Planetesimal density
  - Stellar temperature
  - Stellar mass

- Numerical integration using `scipy.integrate.solve_ivp` (RK45).

- Equilibrium eccentricity and inclination solved with `scipy.optimize.root`.

- Visualization functions for embryo growth, eccentricity, inclination, velocity dispersion, and accretion rates.

## Requirements

- Python 3.10+
- NumPy
- SciPy
- Matplotlib
- h5py
