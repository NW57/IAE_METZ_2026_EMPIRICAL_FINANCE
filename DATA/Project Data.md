## **Wealth Management Engineering**
### Development of a Python Tool for Strategic Portfolio Optimization
WELSCH Nathan & TARILLON-KIEFFER Liam

## **Sommaire**

1. Introduction

2. Theory : Modern Portfolio Theory (MPT)

3. Investment Policy Statement (IPS)

- 3.1 - Investor Profile

- 3.2 - Investment Objectives

- 3.3 - Investment Horizon

- 3.4 - Risk Tolerance

- 3.5 - Allocation Constraints

- 3.6 - Investment Universe

- 3.7 - Benchmark

- 3.8 - Allocation Methodology

4. specifications

5. Python modelling

## **1. Introduction**

Portfolio management occupies a central position in modern finance. It aims to reconcile expected returns with risk management, all while meeting clearly defined investment objectives. In this project, we seek to construct an optimized portfolio of listed assets to maximize risk-adjusted performance while strictly adhering to the constraints defined in the Investment Policy Statement (IPS).

The project is structured around the following problem statement:

How can the implementation of a portfolio optimization model in Python translate the constraints of an Investment Policy Statement into an efficient, robust allocation that maximizes risk-adjusted performance within an uncertain market environment?

To answer this question, we will adopt a structured multi-step approach. First, we will present the theoretical framework underpinning portfolio optimization, expanding on the foundations of Modern Portfolio Theory (MPT) and its implications for diversification and the efficient frontier.

Second, we will define the Investment Policy Statement and derive an operational framework, which will serve as our guide for the Python modeling phase.

The third step consists of developing the model in Python. This will include the extraction and processing of financial data, asset selection, the determination of optimal weights, and Monte Carlo simulations designed to visualize potential portfolio value trajectories and assess resilience against extreme market shocks. Additionally, the integration of Machine Learning models will allow for adaptive allocation adjustments based on evolving market conditions.

Finally, we will analyze the results by comparing the optimized portfolio against a passive benchmark and an equally-weighted portfolio. This will enable us to evaluate the added value of the chosen quantitative approach and propose an allocation consistent with the investor's requirements.

In the context of this project, the use of Python is essential, justified by its ability to efficiently process large financial datasets, estimate returns and covariance matrices, and solve complex constrained optimization problems. It also allows for the simulation of various market scenarios and the integration of machine learning models. This approach strengthens the methodological robustness of the portfolio management process and contributes to better informed decision-making.

## **2. Theoric frame : Modern Portfolio Theory (MPT)**

Among the foundations of modern finance, Modern Portfolio Theory (MPT), developed by Harry Markowitz (1952), remains an essential reference. It is based on the idea that the risk-return profile must be analyzed at the level of the portfolio as a whole, rather than for individual assets in isolation. Consequently, portfolio risk depends not only on the individual volatility of assets but also on the correlations between them. Thus, diversification reduces total risk through the offsetting effects of imperfectly correlated assets.

Within this framework, the expected return of a portfolio is the weighted average of the assets' expected returns, while its variance depends on both individual variances and cross-covariances. Mean-variance optimization then consists of determining, for a given level of return, the asset combination that minimizes variance—or conversely, for a given level of risk, the one that maximizes return.

The set of optimal portfolios resulting from this process forms the efficient frontier, which represents the allocations offering the best risk-return trade-off. Any portfolio located below this frontier is considered sub-optimal, as an alternative combination exists that offers a higher return for the same level of risk, or lower risk for an equivalent return.

To take this further, the Capital Market Line (CML) represents the line connecting the risk-free asset to the tangency portfolio—the specific portfolio on the efficient frontier that offers the maximum Sharpe ratio. This tangency portfolio is the optimal combination of risky assets and serves as the benchmark for the final allocation: it achieves the highest possible return for every level of accepted risk.

This theoretical framework provides a rigorous foundation for the construction of the portfolio under study. It justifies the use of a quantitative approach based on constrained optimization and highlights the essential role of diversification and correlations in risk management. It will serve as the conceptual basis for the implementation of the optimization model in Python and will guide the interpretation of the results.

## **3. Investment Policy Statement (IPS)**

The Investment Policy Statement (IPS) establishes the formal framework that defines the objectives and constraints guiding portfolio construction. It translates the investor's preferences into operational requirements that provide the structure for quantitative optimization.

### 3.1 - Investor Profile

The client is a high-net-worth and financially informed investor seeking long-term capital appreciation while maintaining controlled exposure to equity market risk. An initial capital of €1,000,000 is available for allocation.

The investor favors a diversified portfolio primarily composed of large-cap equities, complemented by gold as a defensive asset intended to mitigate systemic risk during periods of market stress.

Short-term liquidity needs are limited. The investor is therefore willing to accept significant exposure to equity markets in pursuit of long-term growth. Bonds, derivatives, and crypto-assets are explicitly excluded from the investment universe.

### 3.2 - Investment Objectives

The primary objective is to maximize the portfolio’s risk-adjusted performance, targeting an annual return of approximately 6%, exceeding the risk-free rate (French 10-year government bond yield, set at 3.447% as of 06/02/2026), while ensuring sustainable and stable value creation over the long term.

### 3.3 - Investment Horizon

The strategic investment horizon is set between 10 and 15 years. The portfolio will be rebalanced annually in order to maintain alignment with the target allocation and to preserve the intended risk profile. Given the long-term perspective, short-term volatility is acceptable within predefined limits.

### 3.4 - Risk Tolerance

Although the investor accepts a relatively high level of equity risk, the portfolio must remain consistent with clearly defined quantitative risk constraints. These constraints ensure that the search for performance does not lead to excessive exposure.

The portfolio must comply with the following risk constraints:

>Maximum annualized volatility: 15%

>Maximum tolerable Drawdown: -25%

>Value-at-Risk (95% confidence level): below 10%

### 3.5 - Allocation Constraints

The portfolio construction is subject to strict allocation rules:

>No short selling

>Minimum weight per asset: 0%

>Maximum weight per asset: 30%

>Number of assets: between 10 and 15

>Fully invested portfolio: total weights must sum to 100%

These constraints ensure diversification while preventing excessive concentration in any single asset.

### 3.6 - Investment Universe

The eligible investment universe is restricted to:

>Large-cap equities from the United States, Europe, and emerging markets

>Gold exposure through exchange-traded funds (ETFs)

Fixed income instruments, derivatives, and crypto-assets are excluded in order to maintain strategic consistency with the investor’s profile and preferences.

### 3.7 - Benchmark

The portfolio will be compared against a passive benchmark consisting of:

>80% global equities (MSCI World index)

>20% gold (ETF)

The benchmark will be rebalanced annually to ensure comparability.

### 3.8 - Allocation Methodology

The optimal portfolio allocation will be determined using a constrained Markowitz mean-variance optimization model, integrating all risk, allocation, and diversification constraints outlined in this IPS.

## **4.Specifications**

Here is the translation into professional, finance-oriented English. I have maintained the technical terminology (Modern Portfolio Theory, risk metrics, etc.) suitable for an investment report or a technical documentation context.

Based on the strategic objectives and constraints formalized in the Investment Policy Statement (IPS), we have established an operational framework designed to guide the model’s implementation in Python. This document serves as the quantitative and technical translation of the investor’s requirements.

The core objective is to construct an optimized portfolio that maximizes the Sharpe Ratio—representing risk-adjusted performance—while strictly adhering to the previously defined risk and allocation constraints.

Risk Constraints: Maximum volatility of 15%, maximum drawdown limited to -25%, and Value-at-Risk (95% VaR) below 10%.

Allocation Constraints: Long-only (no short selling), individual asset weights between 0% and 30%, a total of 10 to 15 assets, and a fully invested portfolio.

Investment Universe: US, European, and Emerging Market large-cap equities extracted from the MSCI World Index, as well as gold via ETFs. Fixed income, derivatives, and crypto-assets are excluded.

Benchmark and Validation: Performance comparison against an equally-weighted (EW) portfolio and a benchmark consisting of 80% MSCI World / 20% Gold, rebalanced annually.

Methodology: Markowitz Mean-Variance Optimization (MVO), Monte Carlo simulations to test resilience, and the integration of Machine Learning models to dynamically adjust weights based on evolving market conditions.

This operational framework translates theoretical requirements and client objectives into concrete technical constraints, serving as the blueprint for all subsequent portfolio modeling and optimization within Python.


## **1. Python Modelling**

### 1. Database Construction and Preparation

The development of the Python model begins with the importation of necessary libraries. Specialized modules for financial data collection, such as yfinance and pandas_datareader, are used to extract historical market series. The pandas and numpy libraries are employed for data processing and manipulation, while matplotlib is used for graphical representations. Finally, modules from scipy facilitate both the constrained optimization procedures and the statistical tests required to analyze return distributions.

Adjusted closing prices for the large-cap equities within the investment universe, as well as an ETF backed by gold, are downloaded over a five-year period via Yahoo Finance. This database serves as the empirical foundation of the study.

Preliminary cleaning is performed to ensure the robustness of the results. Assets lacking a sufficiently complete history (at least 80% data availability) are excluded from the sample. The remaining time series are aligned on common dates to ensure computational consistency. From the adjusted prices, daily logarithmic returns are calculated and subsequently annualized to ensure the indicators are comparable on an annual basis.

Each asset is assigned an annualized Sharpe ratio, calculated in consideration of the risk-free rate. This metric identifies assets with the best historical trade-offs. The fifteen equities with the highest Sharpe ratios are selected and combined with gold, chosen for its low correlation with equity markets and its traditional role as a safe-haven asset. This step ensures an initial quantitative screening.

Graphical visualizations are generated to illustrate the relative performance of the selected assets, as well as price trajectories and return series. These representations provide a visual understanding of the assets' historical dynamics and their behavior during volatile periods.

### 2. Quantitative Modeling and Constrained Optimization

Once the investment universe is defined, the optimization model is formalized. Specific functions are developed to calculate the portfolio's expected return, volatility, and Sharpe ratio, as well as advanced risk metrics such as Value-at-Risk (VaR) and Maximum Drawdown.

The constraints derived from the Investment Policy Statement are then mathematically formalized and integrated into the optimization process. These include a long-only constraint (no short selling), individual weights between 0% and 30%, a fully invested constraint (sum of weights equals 100%), and explicit limits on volatility, VaR, and maximum drawdown.

Optimization is performed using the SLSQP (Sequential Least Squares Programming) algorithm, which is particularly well-suited for non-linear constrained problems. Simultaneously, random portfolios are simulated to plot the Efficient Frontier and identify the tangency portfolio that maximizes risk-adjusted performance. This step situates the optimal solution within the theoretical framework of Modern Portfolio Theory.

### 3. Performance Evaluation and Robustness Analysis

A backtesting phase is then conducted to compare the optimized portfolio's performance against an equally-weighted portfolio (composed of the same assets) and a strategic benchmark (80% global equities / 20% gold). This comparison evaluates the actual added value of the chosen optimization approach.

To test the portfolio's robustness against adverse market conditions, a Bootstrap Monte Carlo simulation is performed. Ten thousand return trajectories are generated by resampling historical data, allowing for the analysis of potential performance distributions and exposure to tail-risk scenarios.