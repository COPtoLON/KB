Market makers in real-world trading environments typically use models that balance expected profitability (from capturing the bid-ask spread) against inventory risk, volatility, and transaction costs. While these models can get very sophisticated in practice, they often share a few common elements: (1) an internal measure of fair value, (2) a way to dynamically set or adjust bid-ask quotes, and (3) an inventory control mechanism that mitigates large directional exposures. Below is an overview of some well-known modeling approaches used by professional market makers and high-frequency trading (HFT) firms.

1. Avellaneda–Stoikov (AS) Model
Key Ideas
Risk Aversion and Inventory Control
The model incorporates a parameter (
𝛾
γ) for risk aversion. As your net position (inventory) grows, the model automatically adjusts your bid and ask prices to reduce exposure and the risk of adverse moves.
Dynamic Spread Setting
Quotes are updated continuously based on market volatility and inventory levels. The spread widens when inventory is large or volatility is high, and narrows otherwise.
Poisson (or Exponential) Arrival Models
The model frequently assumes that incoming market orders arrive randomly (e.g., via Poisson processes), which helps estimate the probability of filling on either side of the spread.
Why It’s Popular
The Avellaneda–Stoikov framework is one of the earliest academic “optimal market making” models well-suited for limit order book markets.
It explicitly combines risk management (controlling inventory) with optimal quoting decisions in a fairly tractable mathematical form.
2. Extensions of Avellaneda–Stoikov
Several researchers have extended the AS model to account for more realistic market microstructure features:

Order Book Depth / Queue Position

Extensions consider the size of the posted quotes and how far they are in the queue, because fill probability depends on how many orders are ahead of you.
Some queue-based models (e.g., based on Markov or fluid approximations) try to estimate the chance of execution for different quote placements.
Stochastic Volatility or Price Dynamics

Rather than assuming a simple Brownian motion for the underlying price, advanced versions incorporate stochastic volatility, jumps, or correlated factors.
Discrete-Time vs. Continuous-Time

Real systems often implement quoting logic at discrete intervals (milliseconds to seconds) rather than a purely continuous process.
3. Cartea & Jaimungal Framework
Key Contributions
Risk and Execution Cost
Similar to AS, but puts additional focus on measuring execution costs (e.g., fees, slippage, the cost of hedging or crossing the spread).
Market Impact Modeling
In certain versions, the model acknowledges that large trades or persistent quoting behavior can move prices or alter arrival rates.
Practical Uses
Many HFT and prop-trading firms adapt Cartea & Jaimungal (and coauthors’) ideas, as they offer a flexible continuous-time approach and a robust method for deriving closed-form or semi-closed-form controls for quoting strategies.
4. Queue-Based and Limit Order Book Models
Motivation
In real electronic markets, your fill probability depends heavily on where your order sits in the limit order queue. Being first in queue can be more valuable (higher chance of execution) than being last.
Key Features
Queue Dynamics: Models approximate how orders arrive and cancel in the order book.
Priority Positioning: Some approaches treat the order book as a discrete set of “levels,” analyzing the probability of getting filled if you move your quotes in or out by one tick.
Optimal Tick Placement: Decide whether to quote at the best bid/ask, one tick away, or deeper in the book to balance fill probability and profitability.
5. Reinforcement Learning and Machine Learning Approaches
Growing Trend
Many real-world HFT firms complement (or replace) classical stochastic control methods with machine learning (ML) or reinforcement learning (RL).
Why? These models can adapt to non-stationary markets and learn complex patterns not well captured by simpler assumptions.
Typical Pipeline
State Representation: Observations about the current order book state, inventory, volatility regime, time of day, etc.
Actions: Adjusting bid and ask quotes, or deciding not to post at all.
Rewards: Often tied to realized PnL, inventory penalties, and fill rates.
Challenges
High-dimensionality, need for large datasets, risk of overfitting, and the requirement for very low-latency decisions.
6. Other Real-World Considerations
Regulatory & Exchange Fees

Exchanges often impose fee structures or liquidity rebates. Models must incorporate these micro-costs to evaluate true profitability.
Latency and Colocation

Market makers invest in fast connections and server colocation, ensuring minimal delay in quote updates. The best models can be undermined by too much latency or slow execution.
Cross-Asset or Multi-Market Inventory

Real firms often make markets in correlated instruments (e.g., equity vs. futures), requiring advanced cross-hedging or multi-dimensional inventory control.
Human Oversight & Monitoring

Even with automated models, professional market makers monitor real-time PnL, risk dashboards, and market conditions, ready to intervene or override the system if anomalies occur.
Adaptive Parameters

Risk aversion (
𝛾
γ), volatility estimates, and fill probabilities are not fixed; they must be re-estimated or adapted in near-real time based on incoming data.
7. Summary
Most professional market makers—whether in equities, futures, FX, or crypto—use stochastic control or reinforcement learning approaches inspired by (and building upon) academic models like Avellaneda–Stoikov. They incorporate:

Dynamic Inventory Control: Adjusting quotes in response to changing inventory.
Realistic Microstructure: Modeling how quotes get filled (queue position, fill rates).
Adaptive Risk Aversion: Widening spreads or reducing size in volatile conditions.
High-Frequency Implementation: Needing robust, latency-sensitive technology.
The final “secret sauce” typically comes from fitting model parameters to real order flow, calibrating fill probabilities, hedging costs, and adjusting strategies for short-term patterns. Over time, these models are continually refined in response to new data, market regime changes, and technological innovations in HFT.
