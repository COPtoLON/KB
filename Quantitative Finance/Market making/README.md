Market makers in real-world trading environments typically use models that balance expected profitability (from capturing the bid-ask spread) against inventory risk, volatility, and transaction costs. While these models can get very sophisticated in practice, they often share a few common elements: (1) an internal measure of fair value, (2) a way to dynamically set or adjust bid-ask quotes, and (3) an inventory control mechanism that mitigates large directional exposures. Below is an overview of some well-known modeling approaches used by professional market makers and high-frequency trading (HFT) firms.


### IMC
https://github.com/topics/prosperity \
<br>
https://dteather.com/blogs/imc-prosperity-2/#overall-results \
https://github.com/gabsens/IMC-Prosperity-2-Manual/blob/master/Round5.ipynb \
https://github.com/jmerle/imc-prosperity\
https://github.com/jmerle/imc-prosperity-2 \
https://github.com/pe049395/IMC-Prosperity-2024 \
https://github.com/nicolassinott/IMC_Prosperity \
https://github.com/ericcccsliu/imc-prosperity-2 \
https://github.com/MichalOkon/imc_prosperity
https://github.com/academiq-ai/imc-prosperity/blob/main/Trader.py
https://github.com/aniruddha-saha/imc-prosperity-2024b
https://github.com/benbates30/IMC-Prosperity
https://github.com/MichalOkon/imc_prosperity
https://github.com/Harshal73/Prosperity




### Other market making
https://github.com/sidnand/Reinforcement-Learning-for-Market-Making \
https://github.com/nelso0/barbotine-arbitrage-bot \
https://github.com/vladkukolenko/Solana-AMM-Sniping-Bot \
https://github.com/keanekwa/Optiver-Ready-Trader-Go \
https://github.com/pe049395/Market-Making \
https://github.com/pe049395/IMC-Prosperity-2024 \
https://github.com/1leolem1/Implied-PDF-from-crypto-option-prices \
https://github.com/williamdevena/RL_for_Market_making_in_Sports_Trading \
https://github.com/ats-sys/ats \
https://github.com/nirajdsouza/market-making-strategy-simulation \

### Kaggle - Jane Street
https://www.kaggle.com/code/xuchenjames/top-7-js-nnx5-xgbx5-weighted-blend-lb-0-0078 \
https://www.kaggle.com/code/wanmeijianchi/js-rmf-ensemble-xgb-nn-tabm-ridge \
https://github.com/Nicholas-Ho/Jane-Street-Prediction-Kaggle \
https://github.com/TomasDavidYe/kaggle-jane-street-market-prediction \
https://github.com/evgeniavolkova/kagglejanestreet \
https://github.com/scaomath/kaggle-jane-street \
https://github.com/codefluence/jane_street \
https://github.com/MingjieWang0606/Kaggle-Jane-Street-AE-MLP-xgb-TOP1 \
https://github.com/kvyuan/JaneSteetETC \
https://github.com/scaomath/kaggle-jane-street \
https://www.kaggle.com/code/wanmeijianchi/js-rmf-ensemble-xgb-nn-tabm-ridge \
https://www.kaggle.com/code/kumarandatascientist/reach-top-5-0-0083-update-lb-186th-position \
https://www.kaggle.com/code/engadamalmohammedi/0-0084-js-24-xgb-nn-ridge-tabm \
https://www.kaggle.com/code/eivolkova/public-lb-6th \
https://www.kaggle.com/models/guillaumecollin12/torchlstm7/PyTorch/default \
https://www.kaggle.com/models/xuanleekaggle/jane-street-5-and-7_/Other/default \
https://www.kaggle.com/code/yuanzhezhou/jane-street-baseline-lgb-xgb-and-catboost \
https://www.kaggle.com/code/yuanzhezhou/baseline-lgb-xgb-and-catboost \
https://github.com/khangluong2004/ReadyTraderGoAutotrader
https://github.com/martin-he543/optiver-ready-trader-go-2023
https://github.com/Haoran-Jie/ReadyTraderGo_CrazyThursday
https://github.com/keanekwa/Optiver-Ready-Trader-Go
https://github.com/nocrizwang/ready-trader-go
https://github.com/mglush/ready-trader-go-2023
https://github.com/russellstanley/optiver-trading
https://github.com/nicolassinott/Optiver_Ready_Trader_Go
https://github.com/gsmyridis/ReadyTraderGo
https://github.com/Haoran-Jie/ReadyTraderGo_CrazyThursday
### Competition leaderboards
https://www.kaggle.com/competitions/optiver-realized-volatility-prediction/leaderboard \
https://www.kaggle.com/competitions/optiver-trading-at-the-close/leaderboard \
https://www.kaggle.com/competitions/halite/leaderboard \
https://www.kaggle.com/competitions/jane-street-market-prediction/leaderboard \
https://www.kaggle.com/competitions/g-research-crypto-forecasting/leaderboard \
https://www.kaggle.com/competitions/ubiquant-market-prediction/leaderboard 

### Winners - samples
https://kkameleon.xyz/sample_work.html
https://github.com/yberreby






# 1. Avellaneda–Stoikov (AS) Model

## Key Ideas

### Risk Aversion and Inventory Control
- The model incorporates a parameter (𝛾) for risk aversion. As your net position (inventory) grows, the model automatically adjusts your bid and ask prices to reduce exposure and the risk of adverse moves.
### Dynamic Spread Setting
- Quotes are updated continuously based on market volatility and inventory levels. The spread widens when inventory is large or volatility is high, and narrows otherwise.
### Poisson (or Exponential) Arrival Models
- The model frequently assumes that incoming market orders arrive randomly (e.g., via Poisson processes), which helps estimate the probability of filling on either side of the spread.

## Why It’s Popular
The Avellaneda–Stoikov framework is one of the earliest academic “optimal market making” models well-suited for limit order book markets.
It explicitly combines risk management (controlling inventory) with optimal quoting decisions in a fairly tractable mathematical form.

# 2. Extensions of Avellaneda–Stoikov
Several researchers have extended the AS model to account for more realistic market microstructure features:

### Order Book Depth / Queue Position
- Extensions consider the size of the posted quotes and how far they are in the queue, because fill probability depends on how many orders are ahead of you.
- Some queue-based models (e.g., based on Markov or fluid approximations) try to estimate the chance of execution for different quote placements.
### Stochastic Volatility or Price Dynamics
- Rather than assuming a simple Brownian motion for the underlying price, advanced versions incorporate stochastic volatility, jumps, or correlated factors.
### Discrete-Time vs. Continuous-Time
- Real systems often implement quoting logic at discrete intervals (milliseconds to seconds) rather than a purely continuous process.

# 3. Cartea & Jaimungal Framework
## Key Contributions
### Risk and Execution Cost
- Similar to AS, but puts additional focus on measuring execution costs (e.g., fees, slippage, the cost of hedging or crossing the spread).
### Market Impact Modeling
- In certain versions, the model acknowledges that large trades or persistent quoting behavior can move prices or alter arrival rates.
## Practical Uses
- Many HFT and prop-trading firms adapt Cartea & Jaimungal (and coauthors’) ideas, as they offer a flexible continuous-time approach and a robust method for deriving closed-form or semi-closed-form controls for quoting strategies.

# 4. Queue-Based and Limit Order Book Models
## Motivation
- In real electronic markets, your fill probability depends heavily on where your order sits in the limit order queue. Being first in queue can be more valuable (higher chance of execution) than being last.
## Key Features
- Queue Dynamics: Models approximate how orders arrive and cancel in the order book.
- Priority Positioning: Some approaches treat the order book as a discrete set of “levels,” analyzing the probability of getting filled if you move your quotes in or out by one tick.
- Optimal Tick Placement: Decide whether to quote at the best bid/ask, one tick away, or deeper in the book to balance fill probability and profitability.

# 5. Reinforcement Learning and Machine Learning Approaches

## Growing Trend
- Many real-world HFT firms complement (or replace) classical stochastic control methods with machine learning (ML) or reinforcement learning (RL).
- Why? These models can adapt to non-stationary markets and learn complex patterns not well captured by simpler assumptions.
## Typical Pipeline
- State Representation: Observations about the current order book state, inventory, volatility regime, time of day, etc.
- Actions: Adjusting bid and ask quotes, or deciding not to post at all.
- Rewards: Often tied to realized PnL, inventory penalties, and fill rates.
## Challenges
- High-dimensionality, need for large datasets, risk of overfitting, and the requirement for very low-latency decisions.

# 6. Other Real-World Considerations

## Adaptive Parameters
- Risk aversion (𝛾), volatility estimates, and fill probabilities are not fixed; they must be re-estimated or adapted in near-real time based on incoming data.

# 7. Summary
Most professional market makers—whether in equities, futures, FX, or crypto—use stochastic control or reinforcement learning approaches inspired by (and building upon) academic models like Avellaneda–Stoikov. They incorporate:
- Dynamic Inventory Control: Adjusting quotes in response to changing inventory.
- Realistic Microstructure: Modeling how quotes get filled (queue position, fill rates).
- Adaptive Risk Aversion: Widening spreads or reducing size in volatile conditions.
- High-Frequency Implementation: Needing robust, latency-sensitive technology.

The final “secret sauce” typically comes from fitting model parameters to real order flow, calibrating fill probabilities, hedging costs, and adjusting strategies for short-term patterns. Over time, these models are continually refined in response to new data, market regime changes, and technological innovations in HFT.
