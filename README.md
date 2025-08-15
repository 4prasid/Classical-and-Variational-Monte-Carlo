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

- Sample from Boltzmann distribution $$P(s) \\propto exp(-\\beta E(s))$$ for a classical system (e.g., Ising spins).

- Algorithm (Metropolis-Hastings):

  - Propose a local change (e.g., flip a spin).

  - Compute $$\\Delta E$$ .

  - Accept with probability $$min(1, exp(-\\beta \\Delta E))$$ .

  - After equilibration, accumulate observables like Energy $$(E)$$, Magnetization $$(M)$$, Specific Heat $$(C_v)$$, Susceptibility $$(\\chi)$$ and estimate uncertainties.

## Variational Monte Carlo (VMC)
VMC is a quantum Monte Carlo method used to approximate the ground state of a quantum system. The general algorithm involves:

- Variational principle: For any normalized trial $$\Psi_T(\alpha)$$, $$E(\alpha)= \frac{<\Psi_T|H|\Psi_T>}{<\Psi_T|\Psi_T>} \geq E_0$$ .
- Sample configurations R from $$|\Psi_T(R; \alpha)|^2$$ via Metropolis.
- For a given configuration of particles, the local energy, $$E_L$$, is calculated as:
$$E_L = \frac{H\Psi_T}{\Psi_T}$$.
- Estimate $$E(\alpha) = <E_L>$$ and Var($$E_L$$); minimize $$E(\alpha)$$ over $$\alpha$$ (and possibly $$\beta$$, ...).
- Typical Trial Wavefunctions:
  - Harmonic oscillator: Gaussian with parameter $$\alpha$$.
  - Interacting particles: Gaussian orbitals times a Jastrow correlation factor with parameters $$(\alpha, \beta)$$.
 
## Educational Notes
- Why Metropolis works: It enforces detailed balance with respect to the target distribution via acceptance probability min(1, $$\frac{p(new)}{p(old)}$$).

- Why VMC is powerful: It converts high-dimensional integrals for ⟨H⟩ into Monte Carlo averages over $$|\Psi_T|^2$$, making ground-state estimation tractable for suitable ansätze.

- Practical tip: Tune the proposal step size to achieve a balanced acceptance rate; too small leads to slow exploration, too large to many rejections.


## Known Limitations
- Basic optimizers: Current setup may rely on parameter scans rather than advanced gradient-based or SR optimization.
- Finite-size effects in CMC: results depend on L; critical behavior requires care.
- Autocorrelation handling is simple; for high precision, implement blocking/jackknife in depth.

## Contributing
- Open issues for bugs, feature requests, or clarifications.

- Submit pull requests with:

  - Clear description of changes.
  - Tests or example runs (if applicable).
  - Updated docs/README sections.
 
## Getting Help
- For conceptual questions: open an issue describing the system, parameters, and observed behavior.

- For implementation issues: include Python version, dependencies, command used, and a minimal reproducible example.


