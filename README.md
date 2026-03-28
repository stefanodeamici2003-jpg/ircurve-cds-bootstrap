# IR & Credit Curve Bootstrap

Full interest rate and credit curve construction from market instruments, with bootstrapping methods, pricing engines, and Monte Carlo credit simulation.

## Methods Implemented

**Interest Rate Curve**: Bootstrap from deposits, STIR futures, and interest rate swaps (Euribor 3M). Piecewise linear discount factor interpolation with forward rate consistency.

**Credit Curves**: CDS survival probability bootstrapping using three methodologies: flat accrual assumption, continuous accrual, and the Jarrow-Turnbull approach. Hazard rate extraction from market-quoted CDS spreads.

**Pricing**: Asset Swap Spread computation linking bond yields to swap curves. Monte Carlo credit simulation with piecewise-constant intensity model and statistical validation of estimated parameters.

## Key Results

- Bootstrapped discount curves consistent with market instruments
- CDS survival probabilities across maturity tenors with method comparison
- Hazard rate curves with confidence intervals from Monte Carlo estimation
- Asset Swap Spreads bridging fixed income and derivative markets

## How to Run

All code is in MATLAB. Navigate to the project folder and run the desired main sections.
