# Classical-and-Variational-Monte-Carlo

Author - Prasid

# Classical and Variational Monte Carlo
This project explores the application of Classical and Variational Monte Carlo (VMC) methods to various physical systems. It provides implementations and examples of these powerful simulation techniques.

# Description
The goal of this repository is to demonstrate the core principles and practical applications of Monte Carlo methods in physics. The project is divided into two main parts:

- Classical Monte Carlo: Focusing on classical systems and statistical mechanics.

- Variational Monte Carlo: Tackling quantum mechanical problems to find approximate ground state energies.

Key Concepts:
- Monte Carlo Integration: A numerical method that uses random sampling to compute integrals, especially useful in high-dimensional spaces, and complexe integrals.

- Metropolis Algorithm: A cornerstone of Monte Carlo simulations, this algorithm generates a sequence of random samples from a probability distribution.

- Variational Principle: In quantum mechanics, this principle states that the expectation value of the Hamiltonian for any trial wavefunction is always greater than or equal to the true ground state energy.

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
