# Monte Carlo Option Pricing and Delta Hedging under Stochastic Volatility

## Overview

This project investigates how stochastic volatility affects European option pricing and the performance of Black-Scholes delta hedging.

While the Black-Scholes framework assumes constant volatility, financial markets exhibit time-varying volatility, volatility clustering, and volatility smiles. To explore the consequences of these effects, this project compares option prices and hedge performance across three models:

* Black-Scholes
* A discrete-time stochastic volatility (SV) model
* The Heston stochastic volatility model

Asset price paths are simulated using Monte Carlo methods, European call options are priced across a range of strikes, and a Black-Scholes delta hedge is applied to evaluate hedging effectiveness under model misspecification.

---

## Objectives

The project aims to:

* Simulate asset price paths under stochastic volatility dynamics
* Compare European call option prices across multiple models
* Estimate volatility from simulated data
* Implement discrete-time Black-Scholes delta hedging
* Analyse hedging profit-and-loss (PnL) distributions
* Investigate the impact of stochastic volatility on pricing and risk management

---

## Models Implemented

### Black-Scholes

The Black-Scholes model assumes:

* Constant volatility
* Lognormally distributed asset prices
* Continuous trading
* Frictionless markets

European call prices are calculated using the closed-form Black-Scholes formula.

### Stochastic Volatility Model

A latent log-volatility process evolves according to a mean-reverting autoregressive structure:

* Volatility changes over time
* Volatility is stochastic rather than constant
* Asset returns depend on the current volatility state

This allows volatility clustering and changing market uncertainty to emerge naturally.

### Heston Model

The Heston model extends Black-Scholes by allowing variance itself to follow a stochastic process.

Key features:

* Mean-reverting variance
* Correlation between price and volatility shocks
* Volatility smile effects
* Widely used in quantitative finance and derivatives modelling

---

## Methodology

# 1. Monte Carlo Simulation

For each model:

1. Generate simulated asset price paths
2. Compute terminal asset prices
3. Evaluate European call option payoffs
4. Estimate option values using Monte Carlo averages

# 2. Volatility Estimation

Annualised volatility is estimated from simulated log returns and used as the volatility input for Black-Scholes pricing and hedging.

# 3. Delta Hedging

A discrete-time Black-Scholes delta hedge is constructed:

* Initial option premium is received
* A delta-neutral stock position is established
* The hedge is rebalanced daily
* Portfolio value is tracked until maturity

The final hedging error is measured as:

PnL = Hedging Portfolio Value − Option Payoff

# 4. Strike Surface Comparison

European call prices are compared across a range of strike prices to examine how stochastic volatility affects the option price surface.

---

## Results

The project produces:

* Option prices across multiple strikes
* Delta hedging PnL distributions
* Hedging error statistics
* Comparisons between Black-Scholes, stochastic volatility, and Heston models

Example output metrics include:

* Mean hedging PnL
* Standard deviation of hedging PnL
* 5% worst-case hedging outcome
* Option price differences across strikes

---

## Technologies Used

* Python
* NumPy
* SciPy
* Monte Carlo Simulation
* Quantitative Finance
* Stochastic Processes
* Derivatives Pricing
* Financial Mathematics

---

## Educational Purpose

This project was developed as a self-directed exploration of computational finance, stochastic processes, derivative pricing, and risk management. Its purpose is to investigate how differing volatility assumptions affect both option valuation and hedging performance.
