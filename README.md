## SUMMER


❗ Why Most Cointegration-Based Strategies Fail
In this notebook, I rigorously explore Johansen cointegration using ETFs like SPY, QQQ, XLK.
I initially detect in-sample stationarity using ADF and 'co' specification in VECM.

However, out-of-sample behavior reveals a strong trend, minimal reversion, and near-zero trading opportunities.

🔍 Despite textbook cointegration:

The spread drifted beyond 2σ without reverting

The estimated half-life was unrealistic (1 day), contradicting actual behavior

ADF falsely confirmed stationarity

💡 What I Learned
Even when statistical tests say “yes,” the market may say “no.”

Visual diagnostics (spread plot, histogram) are more honest than p-values.

Stationarity needs validation across both train and test sets.

# Since mean reverting was failing with strong signs of trend. I went ahead and tried an trend following algorithm on residuals

🧪 Strategy Comparison: 5-Year vs 3-Year Training Window (Walk-Forward)
We tested our residual trend-following strategy using two walk-forward configurations, to evaluate how training window length affects performance consistency over macro cycles.

Config	Train Window	Walk-Forward Start	Total Test Range	Market Regimes
A	5 Years	2020	2015–2025	Post-QE, COVID crash, Fed tightening, AI trend
B	3 Years	2013	2010–2025	Full cycle: QE → taper → ZIRP → inflation shock

🔍 Observations:
Config A (5y) performs very well in persistent trends (COVID rebound, 2023 AI rally), with Sharpe > 1.0 in multiple years and CAGRs over 40%.

Config B (3y) highlights instability across full-cycle testing: several years suffer losses or flat returns despite trend-following logic.

Shorter training windows increase adaptability but amplify noise and reduce structural stability of the cointegration vector.

Performance is regime-sensitive, not universal. The strategy wins in directional spread moves, but fails in sideways or whipsaw markets.

📈 Cumulative Return Comparison (Normalized)

This chart visualizes cumulative returns from both training setups over 2013–2025.
![trend_strategy_comparison](https://github.com/user-attachments/assets/82cc1bf2-a3b2-4e25-80a6-66cde7d240f8)


✅ Conclusion:
This strategy exhibits alpha in trend-dominated regimes but lacks robustness in neutral or noisy periods.
Going forward, it should be:

Paired with a regime filter or volatility gate

Modified to include rolling beta calibration

Deployed selectively in directional environments

Overall seems to be generating alpha over long term
