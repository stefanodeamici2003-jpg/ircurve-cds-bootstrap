# IR & Credit Curve Bootstrap

Full interest rate and credit curve construction from market instruments, with bootstrapping methods, pricing engines, and Monte Carlo credit simulation.

## Methods Implemented

**Interest Rate Curve**: Bootstrap from deposits, STIR futures, and interest rate swaps (Euribor 3M). Piecewise linear discount factor interpolation with forward rate consistency.

**Credit Curves**: CDS survival probability bootstrapping using three methodologies: flat accrual assumption, continuous accrual, and the Jarrow-Turnbull approach. Hazard rate extraction from market-quoted CDS spreads.

**Pricing**: Asset Swap Spread computation linking bond yields to swap curves. Monte Carlo credit simulation with piecewise-constant intensity model and statistical validation of estimated parameters.

## Key Results

**IR Discount Curve** — Bootstrapped on 15 Feb 2008 from 3 deposits, 7 STIR futures,
and 50 swap pillars out to 50Y. The resulting zero curve is monotonically increasing,
consistent with the upward-sloping Euribor term structure observed at that date.

**Asset Swap Spread** — Computed for a bond (issue 31/03/2007, maturity 31/03/2012,
coupon 4.6%, clean price 101.5%). The spread quantifies the excess yield over Euribor
implied by the market price, bridging fixed income and derivative valuation.

**CDS Survival Probabilities** — Bootstrapped on a 1Y–7Y tenor grid (settlement
19 Feb 2008, recovery 40%). The three methods (no accrual, with accrual,
Jarrow-Turnbull) yield consistent survival probabilities, with accrual correction
producing slightly lower hazard rates at longer tenors. Jarrow-Turnbull provides
a closed-form flat intensity baseline for comparison.

**Monte Carlo Credit Simulation** — 10⁵ scenarios with a piecewise-constant
intensity model (λ₁ = 0.0004, λ₂ = 0.0010, θ = 5Y). Empirical and fitted survival
curves are in close agreement, with 95% confidence intervals confirming statistical
consistency of the estimated hazard rates.

**NPV of Cash Flows** — Discounted present value of a 20Y monthly cash flow stream
(AAGR 5%) computed for two initial amounts (1,500 and 6,000), using the bootstrapped
IR curve with linear zero-rate interpolation.

## How to Run

All code is in MATLAB. Navigate to the project folder and run the desired main sections.
