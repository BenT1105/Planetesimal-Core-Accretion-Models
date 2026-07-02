# Planetesimal Core Accretion Models

A Python model for simulating planetesimal-driven core accretion in protoplanetary disks.

## Overview

This code implements:

- Planetesimal accretion regimes from **Rafikov (2011)**.
- Accretion rates from **Dones & Tremaine (1993)**.
- Eccentricity and inclination evolution following **Fortier et al. (2013)** and **Kaufmann & Alibert (2023)**.

The evolution of the planetesimal eccentricity, inclination, and embryo mass is computed by integrating the coupled ordinary differential equations over **3 Myr** using `scipy.integrate.solve_ivp`. Simulations use the **RK45** integrator with a maximum timestep of **10 years**.

## Features

- Four planetesimal accretion regimes including low and high-dispersion velocity regimes with both weak and strong gravitational focusing.
  
- Planetesimal evolution includes gas drag, viscous stirring by embryo–planetesimal and planetesimal–planetesimal interactions, and density fluctuations driven by disk turbulence.
  
- Time evolution of:
  - Embryo mass
  - Planetesimal eccentricity
  - Planetesimal inclination
    
- Initial conditions for eccetrciticy, embryo mass, and embryo location can be specified for each simulation.

- Disk and planetesimal parameters can be specified including planetesimal size, planetesimal density, turbulance strength, surface density, etc.
  
- Numerical integration with `scipy.integrate.solve_ivp` using the RK45 method to evolve the coupled differential equations over Myr timescales.

- Visualization routines for plotting the evolution of embryo growth, eccentricity, inclination, velocity dispersion, and accretion rates.

## Requirements

- Python 3
- NumPy
- SciPy
- Matplotlib
