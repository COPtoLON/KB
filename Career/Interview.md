## Data structures
- "How do you make a class immutable?"
An immutable object, is an OOP object, that doesn't change.\
In most languages, the basic types are immutables, numbers, strings, booleans, etc.\
But one can most generally make an object immutable by making it impossible to change the internal variables, once they are set.

- "What is an array? What is the difference between list and array?"\
Arrays, are one-after-one memory objects, which can only hold one type of data(int, string, bool...) - fast but singular\
Lists, are combinations of memory position and data, so it can be anything. - slow but dynamic\

- "What is a hashmap?"\
A hashmap is essentially a python dictionary, a structure like { \[Name, Value\], \[Name, Value\] }

- "How does garbage collection work in Python?"\
1. By reference counting\
2. By trying to eliminate cyclical references 

- "What does the Yield command do in python?"\
The yield function in Python creates a generator function that can generate values on the fly and maintain its state between iterations.\
This is in contrast to the return function, which returns all results at once and stops holding onto its state

- "What is a generator function?"\
A generator function is a function used to obtain the results from a generator object.\
A generator object can be used to handle large data sets or data streams.

- "What is a decorator function?"\
A decorator function is a function that can be wrapped around another, to do such things as:\
Timing, logging or authentifications

- "How do you read a file in python?"\
You use the read command or the open command, from there you will have to properly interpret the file\
either with .readlines() or something else

- "What is a smart pointer?"
A smart pointer is a variable, that automatically deletes itself, when it is no longer needed\
like an integer, that is no longer needed for a calculation\

- "How is float stored in python?"
A Python float is stored as a 64-bit IEEE 754 double-precision value, \
which provides a balance between performance and precision but can introduce small rounding errors for certain decimal values.


## How would you improve your code?
- "What can be done better for the home work task?"
- "Can you explain why you code like this?"
- "What is efficiency of selected algorithms"

- "What is the command to search for a certain pattern?"
- "What is a good refactoring?"
- "How do you make sure the refractor did a good job?"


## Finance
- "What is a future?"
- "What is an option?"

## Second interview
Exchange level stock market data processing
Order book

## Third interview
*Leetcode style questions*
Dictionary based processing?
Graph Path Traversal
Text/Graph Algorithms

# Along the way

1. Risk Management & Quantitative Finance
Since the role is specifically in Risk, you can expect in-depth questions about:

Risk Measures and Methodologies

“Explain Value at Risk (VaR) vs. Conditional VaR (Expected Shortfall). How would you calculate each?”
“What is the difference between parametric VaR, historical simulation, and Monte Carlo VaR? When would you use each?”
“What kind of stress tests or scenario analyses have you implemented before? How would you design one for a multi-asset portfolio?”
“How do you handle tail risk or extreme events in systematic strategies?”
“How do you measure and monitor liquidity risk in systematic trading?”
Systematic Trading & Portfolio Construction

“What kinds of signals or factors might go into a systematic strategy? How does risk overlay with these factors?”
“How do you size positions in a risk-aware manner? (Concept of risk budgeting, volatility targeting, etc.)”
“Explain how you’d rebalance a portfolio daily to adhere to risk constraints (max drawdown, max volatility, etc.).”
Derivatives & Greeks (if relevant to the desk)

“How do you calculate Greeks (Delta, Gamma, Vega) for options? How do these feed into a risk system?”
“Describe how you might stress-test an options portfolio.”
2. Programming & Software Engineering
AHL hires strong developers, often with Python (and sometimes C++/Java) backgrounds. Expect general coding, design, and performance questions, such as:

Coding & Data Structures

They may give you a short coding exercise on-site or a discussion prompt:
“Implement a function to process large time-series data sets in Python, focusing on memory efficiency.”
“Design a system to compute rolling risk metrics (like VaR) for a large set of instruments in an online (streaming) fashion.”
Discussion of complexity analysis, concurrency (if real-time or intraday risk computations are needed).
Software Design & Architecture

“How would you design a scalable risk engine capable of handling thousands of instruments with frequent intraday updates?”
“Discuss a pipeline for ingesting market data, calculating risk metrics, and storing results. What are the bottlenecks and how do you optimize them?”
“How do you handle concurrency or parallelization when running Monte Carlo simulations on a large portfolio?”
Performance & Optimization

“How would you profile a Python-based risk system? What tools and techniques would you use?”
“Discuss vectorization, use of NumPy, or just-in-time compilation (e.g., Numba) to speed up numerical computations.”
“Explain memory management differences between Python vs. C++. When might you choose one over the other for a production environment?”
3. Mathematics & Statistics
AHL is heavily quantitative, so you should expect some math, stats, and probability questions:

Probability & Statistics

“If returns are (supposedly) normally distributed, what does that imply for extreme tails? Do you believe market returns are truly normal?”
“Explain the Law of Large Numbers and the Central Limit Theorem in the context of bootstrapping or Monte Carlo.”
“What is autocorrelation, and why might it matter in time-series analysis?”
Time-Series Analysis

“How do you test for stationarity in a time series? Which tests do you use (ADF, KPSS)?”
“Explain volatility clustering. How might GARCH or EGARCH models be used in risk forecasting?”
Monte Carlo Methods

“How do you set up a Monte Carlo simulation to estimate portfolio VaR? Which variance reduction techniques could you use?”
“Discuss antithetic variates or importance sampling. When do they help?”
4. Practical Risk System Scenarios
Especially for a Risk Quant Dev, you might get scenario-based questions that test both your risk knowledge and coding approach:

Intraday Risk Updates

“We have a large number of strategies trading multiple asset classes globally. We need near real-time risk metrics (e.g., aggregated PnL, VaR). How would you architect this system? What’s your approach to database/storage (relational vs. columnar vs. time-series DB)?”
Stress Testing

“We want to run daily stress scenarios (e.g., 2008 financial crisis, dot-com crash, COVID shock) across all portfolios. How do we generate the shocks and apply them to various instruments efficiently?”
Latency vs. Accuracy

“At what point do you accept approximate risk calculations or partial updates for the sake of speed? How do you decide the trade-off between speed and accuracy?”

Programming Fundamentals & Software Engineering

Data Structures and Algorithms:
Expect standard questions about arrays, linked lists, trees, graphs, heaps, etc.
Algorithmic complexity (Big-O notation), sorting, searching, and hashing.
Common coding challenges (e.g., “implement LRU cache”, “detect cycle in a linked list”).
Design and Architecture:
How to structure large-scale systems, common design patterns, SOLID principles.
Discussion of memory management, threading, concurrency, synchronization.
Language-Specific Details:
If the role uses C++, be ready for questions about templates, RAII, pointers vs. references, STL internals.
If Python is heavily used, be ready for questions about list vs. tuple, Python memory model, GIL (Global Interpreter Lock), and idiomatic Python.
Debugging/Performance:
Profiling code, understanding CPU/GPU optimization, vectorization, low-latency considerations.
How to debug in a multi-threaded environment.
Mathematics & Statistics (Quantitative Aptitude)

Probability & Statistics:
Common distributions (normal, log-normal, Poisson, etc.) and how/when they’re applied in finance.
Expectation, variance, conditional probability, independence vs. correlation, etc.
Random processes (e.g. Brownian motion if relevant to pricing, Markov chains, etc.).
Linear Algebra:
Matrix operations and decompositions (LU, QR, eigenvalues/eigenvectors).
How linear algebra underpins many pricing and risk models.
Calculus & Differential Equations (depending on the role):
Might see questions about PDEs (e.g., Black–Scholes PDE).
Gradient-based optimization, partial derivatives, etc.
Finance & Domain Knowledge

Derivatives Pricing and Risk:
Know the Black–Scholes formula, how Greeks (Delta, Gamma, etc.) are computed, or at least the conceptual approach.
Basic knowledge of fixed income (yield curves, duration, convexity), or equities/FX, depending on the desk.
Market Microstructure (for high-frequency or low-latency roles):
Order books, limit order vs. market order, latency considerations, how data feeds work.
Numerical Methods:
Monte Carlo simulation (variance reduction techniques like antithetic variates, control variates).
Finite difference methods for PDEs (if relevant).
System Design & Infrastructure

Low-Latency & High-Performance:
How to architect systems for minimal latencies: lock-free data structures, using CPU caches effectively, network I/O optimizations.
Techniques for scaling horizontally and vertically.
Databases & Data Handling:
Real-time data ingestion, time-series storage (kdb+, Influx, or columnar DB knowledge might be relevant).
ETL pipelines, data normalization, or dealing with large volumes of tick data.
Behavioral & Team-Fit Questions

Even in quant/dev interviews, you’ll often get questions about collaboration style, problem-solving approach, and communication—how you handle disagreements, mistakes, or tight deadlines.
Brain Teasers / Logic & Puzzle Questions

Some quant interviews still use these as a test of logical thinking. Examples might include:
Coin flip or die roll probability puzzles.
Puzzles about expected value (e.g., “How many times do you need to roll a die before hitting a 6?”).
Logical riddles or combinatorial puzzles.
Sample Questions
Below is a set of sample questions in each category to guide your preparation.

1. Programming & Software Engineering
Data Structures:

“Implement a stack using two queues (or a queue using two stacks). Explain the time complexity of each operation.”
“Given a stream of prices, keep track of the maximum value in constant time.”
Algorithms:

“Find the shortest path in a weighted graph. Describe how Dijkstra’s algorithm works and its complexity.”
“Merge two sorted linked lists in-place.”
C++ Specific:

“Explain how templates differ from generics in other languages.”
“What is the difference between new and malloc?”
“What is an rvalue reference, and why is it useful?”
Concurrency:

“Explain how you would design a thread-safe queue.”
“What is a race condition? Give an example.”
“How do you handle synchronization in C++ (or Java/Python)? Pros and cons of different methods.”
2. Math & Statistics
Probability:

“If you toss a fair coin 10 times, what’s the probability of exactly 5 heads?” (Binomial distribution)
“Explain the Law of Large Numbers and Central Limit Theorem.”
“Two fair dice are rolled; what is the probability of getting a sum of 8?”
Finance-related:

“Explain the concept of volatility in options pricing.”
“Derive or outline the Black–Scholes formula. What assumptions go into it?”
“How do you price an interest rate swap or an FX forward?”
3. Numerical Methods & Quantitative Techniques
Monte Carlo:

“How would you speed up a Monte Carlo simulation? What is importance sampling?”
“Explain variance reduction techniques (like antithetic variates).”
PDEs & Black–Scholes:

“Derive the finite difference method for the Black–Scholes PDE.”
“How do you handle boundary conditions in a finite difference approach?”
4. System Design
“Design a real-time market data feed handler that can handle thousands of ticks per second.”
“How would you cache and update pricing data in a high-frequency environment?”
“Discuss how to monitor and log high-volume trading systems for debugging and performance metrics.”
5. Behavioral
“Tell me about a time you had a conflict with a team member and how you resolved it.”
“Describe a challenging bug you encountered in a large codebase. How did you approach fixing it?”
“What aspects of software engineering are you passionate about, and what do you hope to learn in a quant role?”

## Behavioural
- "What do you want to do with your career?"
- "Where do you see yourself ... "
- “Tell me about a time you had a conflict with a team member and how you resolved it.”
- “Describe a challenging bug you encountered in a large codebase. How did you approach fixing it?”
- “What aspects of software engineering are you passionate about, and what do you hope to learn in a quant role?”
- Tell me about a project where you faced significant technical or quantitative challenges. How did you overcome them?”
- “How do you handle disagreements about methodology in a team? For instance, if a researcher insists on a certain approach but you believe another approach is better for production reliability?”
- “Describe how you stay current with new technologies or quantitative techniques. What are you learning now?”
