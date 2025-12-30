# NEXUS-RL: Attention-Based Deep Reinforcement Learning for Portfolio Management in India

This repository contains the implementation and research findings of Nexus-RL, an advanced deep reinforcement learning framework adapted for the Indian equity market.

## Abstract
Nexus-RL seeks to adapt and evaluate the AlphaStock hierarchical reinforcement learning framework within the Indian market environment[: 4]. The research demonstrates how advanced architectures can be reparameterized to handle emerging-market characteristics, providing higher risk-adjusted returns and improved drawdown resilience[: 5, 10].



## Methodology
[_start]The Nexus-RL pipeline consists of four primary stages[: 166]:
1. [_start]**Data Preparation**: Daily price and volume data from the Nifty 100 (2010–2024) are cleaned and standardized using Z-score normalization[: 199, 200, 208].
2. **Model Architecture**:
    * [_start]**LSTM-HA**: Encodes historical stock trajectories to capture short-term and long-range dependencies[: 229, 230].
    * [_start]**CAAN (Cross-Asset Attention Network)**: Quantifies interactions among stocks to produce relative "winner scores"[: 234, 235, 236].
    * [_start]**Portfolio Generator**: Implements a long-only strategy suitable for Indian market restrictions, selecting the top 10 ranked stocks[: 242, 243].
3. [_start]**RL Training**: The network is trained using policy-gradient reinforcement learning to maximize the annualized Sharpe ratio[: 250, 253].
4. [_start]**Out-of-Sample Backtesting**: A strict walk-forward simulation is performed on data from January 1, 2020, to January 1, 2024, accounting for a 0.1% transaction cost[: 262, 264].



## Key Features
* **Emerging Market Adaptation**: Specifically designed to handle the structural noise and high volatility typical of developing economies.
* **Feature Parsimony**: Achieves robust results using only three technical features: Price Rising Rate (PR), Trade Volume (TV), and Volatility (VOL).
* **Interpretability**: Utilizes sensitivity analysis (saliency maps) to provide post-hoc explanations for asset and feature importance.

## Experimental Results
Nexus-RL was evaluated against the Buy-and-Hold benchmark and international DRL baselines (EIIE, DDR, DeepTrader, FinRL).

| Metric | Indian Market Performance |
| :--- | :--- |
| Annualized Percentage Rate (APR) | 13.60%  |
| Annualized Volatility (AVOL) | 13.57% |
| Annualized Sharpe Ratio (ASR) | 1.0023 |
| Maximum Drawdown (MDD) | -9.79%  |
| Calmar Ratio (CR) | 1.3893 |



## Key Contributions
* First study to apply attention-based reinforcement learning strategies to the Nifty 100 universe[: 292].
* Empirical proof that cross-sectional attention signals provide significant informational power in the changing Indian market microstructure[: 80, 81].
* Verification that "Buy Winners" components remain viable in long-only emerging market portfolios[: 298].

## Limitations and Future Work
* Current results are limited by daily-frequency data and simplified transaction-cost assumptions[: 15].
* Future research aims to incorporate multi-modal data sources such as news sentiment, macroeconomic events, and ESG signals[: 510, 514].
