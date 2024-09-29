# Timer Option Pricing and Hedging

**Authors**: Chi-lin Li, Wenlin Tang, Zhixin Zhang, Hongzhen Du  
**Date**: May 3, 2024

## Project Overview

This project focuses on **pricing and hedging timer options**, a novel financial product introduced by Societe Generale in 2007. Unlike standard options, timer options expire based on the accumulated variance of the underlying asset rather than a fixed date. This study explores simulation techniques to price timer options within stochastic volatility models, particularly the Heston and Hull-White models. The project also integrates dynamic delta hedging strategies to manage risk.

### Key Features:
- **Timer Option Mechanism**: The option’s expiration is driven by realized volatility instead of a pre-set date.
- **Stochastic Volatility Models**: Uses the **Heston** and **Hull-White** models to simulate pricing and risk management.
- **Dynamic Delta Hedging**: Provides a method to manage risks and optimize portfolio value in volatile markets.
- **Empirical Studies**: The strategy is applied to **AAPL** and **JPM** stocks to validate its effectiveness in real-world trading scenarios.

## Methodologies

### 1. Timer Option Pricing
- The timer option is executed when the **realized cumulative variance** hits a predefined **variance budget**.
- **Pricing Formula**:
  \[
  C_t = \mathbb{E}_Q \left[ e^{-r(\min(T, \tau_B) - t)} \max(S_{\min(T, \tau)} - K, 0) \right]
  \]
  where \( \tau \) is the stopping time based on variance accumulation.

### 2. Stochastic Volatility Models
- **Heston Model**: Captures mean-reverting volatility, modeled by:
  \[
  dV_t = \kappa(\theta - V_t) dt + \gamma \sqrt{V_t} dW_t^2
  \]
  where \( V_t \) is the variance, \( \kappa \) is the rate of mean reversion, \( \theta \) is the long-run variance, and \( \gamma \) is the volatility of volatility.
  
- **Hull-White Model**: Describes volatility dynamics with a simpler structure:
  \[
  dV_t = \alpha V_t dt + \gamma V_t dW_t^2
  \]
  where \( \alpha \) and \( \gamma \) determine the drift and volatility of the volatility process.

### 3. Dynamic Hedging with Profit and Loss (P&L)
- **Delta Hedging**: Adjusts the hedge ratio dynamically based on time-dependent volatility, ensuring minimal risk exposure.
- **P&L Calculation**: The total P&L at maturity is determined by the hedging strategy, which incorporates the **cash gamma** position.

### 4. Sensitivity Analysis
- Examines how changes in the **variance budget** and **interest rates** affect the option price. The results indicate that higher variance budgets lead to higher option prices due to increased market uncertainty.

## Experimental Results

The timer options and hedging strategies were applied to portfolios consisting of **AAPL** and **JPM** stocks. Key findings include:

- **AAPL Portfolio**: The value of the portfolio showed an upward trend, growing from $1,000,000 to over $1.2 million over 252 trading days, indicating successful hedging.
- **JPM Portfolio**: Similar positive returns were observed using both the Heston and Hull-White models, showcasing the robustness of the hedging strategies.

### Performance Summary:
- **AAPL**: Grew to $1.2 million, reflecting effective hedging and profit maximization.
- **JPM**: Showed consistent performance with positive returns across both stochastic models.

## Conclusion

This study highlights the effectiveness of **timer options** as a financial product that leverages realized volatility to determine expiration. The integration of **stochastic volatility models** and **dynamic delta hedging** offers robust risk management strategies. Future work could explore more complex market factors, refine computational efficiency, and compare with other volatility models to enhance pricing accuracy and scalability.

## Installation

To run the code and simulations for timer option pricing and hedging strategies, install the following dependencies:

```bash
pip install numpy pandas scipy matplotlib statsmodels
```

## Usage

1. **Preprocess Data**: Import historical stock price data and calculate realized volatility.
2. **Run Timer Option Model**: Use the Heston or Hull-White model to price the timer options.
3. **Apply Dynamic Hedging**: Implement delta hedging strategies to manage portfolio risk over time.
4. **Analyze Results**: Perform sensitivity analysis and evaluate portfolio performance using the simulated outcomes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contribution

- Chi-lin Li, Wenlin Tang, Zhixin Zhang, and Hongzhen Du contributed equally to this project.
