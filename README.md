## Portfolio Optimization using Multi-Factor Models and Riskfolio

This repository contains Python scripts for portfolio optimization using multi-factor models and the Riskfolio library. The scripts demonstrate how to construct and evaluate portfolios based on factors like quality, momentum, size, value, and volatility.

### Overview

Portfolio optimization is essential for investors aiming to maximize returns while managing risk effectively. This project focuses on implementing various strategies to select assets based on their rankings across different factors and subsequently optimizing portfolio weights using Riskfolio techniques.

### Key Components

- **Data Sources:**
  - **Composition of Index (IBX):** Defines the constituents of the index used for portfolio construction.
  - **Closing Prices of Assets:** Historical closing prices used to calculate returns and evaluate portfolio performance.
  - **Reference Indices:** Data on benchmark indices (e.g., Ibovespa, SELIC) for comparison purposes.
  - **Factor Data:**
    - **ROIC (Return on Invested Capital):** Quality factor based on financial performance metrics.
    - **Momentum (12-month):** Momentum factor based on historical price performance.
    - **Market Value:** Size factor based on market capitalization of companies.
    - **Price-to-Book Ratio (P/B):** Value factor based on price relative to book value.
    - **Volatility (12-month):** Risk factor based on historical price volatility.

- **Portfolio Selection Functions:**
  - **`SelPort1(param_1a, param_1b)`:** Selects assets based on a single factor within specified ranking limits.
  - **`SelPort2Par(param_1, param_2)`:** Selects assets based on two factors and their respective ranking limits.
  - **`SelPort4Par(param_1, param_2, param_3, param_4)`:** Selects assets based on four factors and their respective ranking limits.

- **Portfolio Evaluation:**
  - **`EvalPort(portfolio, closing_prices)`:** Evaluates portfolio performance, providing cumulative returns, periodic returns, drawdowns, annualized return, and volatility.
  - **`EvalRef(reference_data, index)`:** Evaluates benchmark index performance using similar metrics.

- **Riskfolio Optimization:**
  - **`calc_riskfolio_opt(ranked, optimization_option)`:** Implements Riskfolio techniques (Risk Parity, Minimum Variance, Maximum Decorrelation) to optimize portfolio weights based on historical returns and covariance.

### Usage

1. **Setup:**
   - Clone the repository and ensure Python environment with necessary dependencies (listed in `requirements.txt`).
   - Place required Excel files (`Dados-Comp-IBRX.xlsx`, `Dados-Fechamento.xlsx`, etc.) in the project directory.

2. **Execution:**
   - Modify parameters (`data_inicial`, `data_final`, `colunas`, `step_port`, `step_eval`) as needed for your analysis.
   - Use functions like `SelPort1`, `SelPort2Par`, or `SelPort4Par` to select assets based on your desired factors and ranking criteria.
   - Evaluate selected portfolios using `EvalPort` and compare against reference indices using `EvalRef`.
   - Optimize portfolio weights using `calc_riskfolio_opt` with options like 'RP' (Risk Parity), 'GMV' (Global Minimum Variance), or 'MDP' (Maximum Decorrelation).

3. **Sharpe Ratio Calculation:**
   - Use the Sharpe Ratio to assess risk-adjusted returns of portfolios evaluated through `EvalPort` function.

### Contribution

Contributions are welcome! If you find issues or have improvements, please open an issue or submit a pull request.

### License

This project is licensed under the MIT License. See the LICENSE file for more details.

### Acknowledgments

- This project utilizes concepts from modern portfolio theory and Riskfolio library for efficient portfolio management.
- Special thanks to the developers of Riskfolio for providing tools to optimize and manage investment portfolios.
