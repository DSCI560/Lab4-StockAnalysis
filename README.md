# Lab4-StockAnalysis
## Real-Time Stock Price Analysis and Trading Model

**Team:** Group 12  
**Stock Analyzed:** NVIDIA (NVDA)  
**Analysis Period:** January 2023 - February 2026  
**Initial Capital:** $100,000

---

## Table of Contents
1. [Overview](#overview)
2. [System Requirements](#system-requirements)
3. [Project Structure](#project-structure)
6. [Implemented Algorithms](#implemented-algorithms)
7. [Performance Metrics](#performance-metrics)
9. [Results](#results)

---

## Overview

This project implements a comprehensive algorithmic trading system that:
- Collects real-time stock price data for NVIDIA (NVDA)
- Implements three different trading strategies
- Simulates trading with realistic commission and slippage
- Calculates and compares performance metrics
- Visualizes portfolio performance over time

The system is designed to determine which trading strategy yields the highest profit compared to a simple buy-and-hold strategy.

---

## System Requirements

### Required Software:
- Python 
- Jupyter Notebook

### Required Python Libraries:
```
numpy >= 1.19.0
pandas >= 1.1.0
matplotlib >= 3.3.0
yfinance >= 0.1.63 (optional, falls back to synthetic data)
```

---
Install from the requirements file:
```bash
pip install -r requirements.txt
```

### Step 4: Verify Installation
```bash
python -c "import numpy, pandas, matplotlib; print('All libraries installed successfully')"
```


## Project Structure

### Notebook Organization

```
1. Setup and Data Collection
   ├── Environment imports
   ├── Library imports with fallback
   ├── Configuration parameters
   └── Data loading/generation

2. Data Exploration
   ├── Dataset information
   ├── Statistical summary
   └── Price visualization

3. Algorithm Implementation
   ├── Moving Average Strategy
   ├── MACD Strategy
   ├── RSI Calculation
   └── Hybrid Strategy

4. Mock Trading Environment
   ├── TradingSimulator Class
   ├── Commission and slippage modeling
   └── Backtest execution

5. Performance Analysis
   ├── Metric calculations
   ├── Trade statistics
   └── Comparative visualization

6. Results and Conclusions
   └── Performance summary
```

---

## Implemented Algorithms

### 1. Moving Average (MA) Strategy
**Type:** Trend-following  
**Parameters:**
- Short-term MA: 20 days
- Long-term MA: 50 days

**Signals:**
- **Buy:** When short MA crosses above long MA (Golden Cross)
- **Sell:** When short MA crosses below long MA (Death Cross)

**Rationale:** Identifies trend changes and momentum shifts

### 2. MACD (Moving Average Convergence Divergence)
**Type:** Momentum indicator  
**Parameters:**
- Fast EMA: 12 days
- Slow EMA: 26 days
- Signal Line: 9-day EMA of MACD

**Signals:**
- **Buy:** When MACD crosses above the signal line
- **Sell:** When MACD crosses below the signal line

**Rationale:** Captures momentum changes and trend strength

### 3. Hybrid Strategy (MA + MACD)
**Type:** Combined approach  
**Logic:** Requires confirmation from both indicators

**Signals:**
- **Buy:** Both MA and MACD generate buy signals
- **Sell:** Either MA or MACD generates a sell signal

**Rationale:** Reduces false signals by requiring confirmation

---

## Performance Metrics

### Primary Metrics Calculated:

1. **Total Portfolio Value**
   - Final value of cash + holdings
   
2. **Total Return**
   ```
   Return = (Final Value - Initial Capital) / Initial Capital × 100%
   ```

3. **Annualized Return**
   ```
   Annualized Return = [(Final Value / Initial Capital)^(365/days) - 1] × 100%
   ```

4. **Sharpe Ratio** (Risk-adjusted return)
   ```
   Sharpe Ratio = (Portfolio Return - Risk-Free Rate) / Portfolio Volatility
   ```
   - Higher is better (>1.0 is good, >2.0 is excellent)

### Trade-Level Metrics:

5. **Win Rate**
   ```
   Win Rate = (Number of Profitable Trades / Total Trades) × 100%
   ```

6. **Average Win/Loss**
   - Average profit on winning trades
   - Average loss on losing trades

7. **Trade Expectancy**
   ```
   Expectancy = (Average Win × Win Rate) - (Average Loss × Loss Rate)
   ```

---
---
