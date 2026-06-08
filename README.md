# Cointegration-Based Pairs Trading Backtest

Python backtest for a cointegration-based pairs trading strategy inspired by Brunetti and De Luca's research paper, *Pre-selection in cointegration-based pairs trading*.

## Project Overview

This project implements a statistical arbitrage pairs trading strategy using cointegration. The strategy identifies pairs of assets with a long-run relationship, trades temporary spread deviations, and evaluates performance using metrics and an equity curve.

## Strategy Logic

1. Use a rolling formation window.
2. Rank candidate stock pairs using a pre-selection metric.
3. Test ranked pairs for cointegration.
4. Select cointegrated pairs for trading.
5. Estimate the spread between two assets.
6. Open long/short trades when the spread moves outside a threshold.
7. Close trades when the spread mean-reverts.
8. Generate monthly returns, metrics, and an equity curve.

## Trading Rule

```text
spread_t = log(P1_t) - (alpha + beta * log(P2_t))
```

## Entry

```text
spread_t > +2 sigma: short asset 1, long asset 2
spread_t < -2 sigma: long asset 1, short asset 2
```

## Exit

```text
close when the spread returns inside the +/- 2 sigma band
```

## Outputs

```text
outputs/metrics.txt
outputs/equity_history.csv
outputs/equity_curve.svg
```

## Disclaimer

This project is for educational and research purposes only. It is not financial advice.
