# Classical-and-Variational-Monte-Carlo (CMC and VMC)

Author - Prasid

# Project Overview
This repository showcases simple, instructive implementations of Classical Monte Carlo (CMC) and Variational Monte Carlo (VMC) methods applied to physics problems. The examples highlight key concepts such as random sampling, Metropolis–Hastings algorithms, and statistical estimation.

The included code demonstrates:

- Applications in classical statistical mechanics (e.g., Ising-like systems).

- Quantum ground-state estimation using the variational principle.

These implementations aim to provide clear, educational insight into core Monte Carlo techniques and their use in both classical and quantum contexts

# Description
The goal of this repository is to demonstrate the core principles and practical applications of Monte Carlo methods in physics. The project is divided into two main parts:

- Classical Monte Carlo: Focusing on classical systems and statistical mechanics.

- Variational Monte Carlo: Tackling quantum mechanical problems to find approximate ground state energies.

Key Concepts:
- Monte Carlo Integration: A numerical method that uses random sampling to compute integrals, especially useful in high-dimensional spaces and complex integrals.

- Metropolis Algorithm: A cornerstone of Monte Carlo simulations, this algorithm generates a sequence of random samples from a probability distribution.

- Variational Principle: In quantum mechanics, this principle states that the expectation value of the Hamiltonian for any trial wavefunction is always greater than or equal to the true ground state energy.

# Features

- Classical Monte Carlo:

  - Metropolis-Hastings for lattice/spin systems

  - Estimation of thermodynamic observables: energy, magnetization, heat capacity, susceptibility

  - Equilibration and sampling workflows (burn-in, decorrelation, block/statistical error)

- Variational Monte Carlo:
  - Trial wavefunctions with tunable parameters.
  - Local energy estimator $$E_L = \frac{H\Psi_T}{\Psi_T}$$ .
  - Metropolis sampling proportional to $$|\\Psi_T|^2$$ .
  - Variational optimization of parameters (grid search, basic gradient-free schemes).

# Implemented Methods

## Classical Monte Carlo (CMC)
This section applies Monte Carlo methods to classical systems. A common example often used to illustrate these methods is the 2D Ising Model, which simulates ferromagnetism. The simulation typically involves:

1. Generating random numbers to propose changes to the system's state.

2. Using the Metropolis-Hastings algorithm to accept or reject these changes based on the system's energy.

3. Calculating thermodynamic quantities like energy, magnetization, and specific heat.

## Variational Monte Carlo (VMC)
VMC is a quantum Monte Carlo method used to approximate the ground state of a quantum system. The general algorithm involves:

1. **Defining a Trial Wavefunction**: A parameterized trial wavefunction, $$\Psi_T(\alpha) $$ is chosen. The parameter $$\alpha$$ is what will be "varied" to find the best approximation.

2. **Calculating the Local Energy**: For a given configuration of particles, the local energy, $$E_L$$, is calculated as:
$$E_L = \frac{H\Psi_T}{\Psi_T}$$

3. **Monte Carlo Sampling**: The Metropolis algorithm is used to sample configurations of the system according to the probability distribution $$|\Psi_T|^2$$.

4. **Optimization**: The expectation value of the Hamiltonian is calculated and minimized by adjusting the variational parameters $$(\alpha)$$ in the trial wavefunction. 
