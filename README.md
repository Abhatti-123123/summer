# summer

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
