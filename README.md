# 5440-project-Portfolio-Optimization-Using-Multi-Factor-Models-and-Arbitrage-Pricing-Theory
Portfolio Optimization Using Multi-Factor Models and Arbitrage Pricing Theory
1. Introduction
Portfolio optimization is critical in financial risk management and investment strategy through balancing returns and risks effectively. Our project aimed to develop a systematic portfolio optimization framework by using Arbitrage Pricing Theory (APT) and multi-factor modeling. During the project, we will use historical data from a pickle file and explore the model with factors like style factors, industry-specific factors and residual factors 
2. Data and Methodology
2.1 Data Sources and Preprocessing
A timeframe from 2003 to 2010 was utilized in the data to enhance computational efficiency. During the preprocessing process, outliers were addressed by using Winsorization, so that we could limit the extreme values to the 5th and 95th percentiles. The process of data cleaning better ensured the accuracy of our model.
2.2 Factor Model Framework
The following equation represents the multi-factor model:
R_t = X_t f_t + ε_t,  ε_t ∼ N(0, D)
Where:
- R_t represents excess returns.
- X_t is the factor exposure matrix.
- f_t denotes latent factor returns.
- ε_t captures idiosyncratic risk.
This framework enables the decomposition of returns into systematic (factor-driven) and unsystematic components.
2.3 Risk Factor Selection
Factors were classified into style (such as Beta, Size, Momentum, Value, Leverage, and Liquidity.) and industry-specific factors (such as Aerospace, Banks, and Software etc.) based on the example given to us. Factor covariance matrices were computed and were assumed to have diagonal structures to reduce computational complexity.
2.4 Alpha Factor Estimation
Residual returns (Y) were modeled as:
Y = Ret − X X⁺ Ret
where X⁺ is the pseudoinverse of X. Candidate alpha factors were evaluated using lasso regression, with hyperparameters tuned via cross-validation to minimize mean squared error.
2.5 Portfolio Optimization
Optimal portfolio weights (w) were computed using the Woodbury matrix inversion lemma:
w = 1/λ (D⁻¹ + X F Xᵀ)⁻¹ α
where λ represents the risk-aversion parameter, F is the factor covariance matrix, and α is the vector of factor returns.
2.6 Backtesting
Portfolios were backtested to evaluate performance metrics, including cumulative profit, market value positions, and risk decomposition.
3. Results
3.1 Model Performance
•	Best regularization parameter (α): 5.34 × 10⁻⁶
Train Mean Squared Error (MSE): 0.00043686054169732373
Test Mean Squared Error (MSE): 0.00042766687145383915
3.2 Portfolio Performance
Cumulative Profit: Consistent growth was observed across the backtest period.
Market Positioning: Long and short market values demonstrated effective allocation strategies responsive to risk factor signals.
3.3 Risk Analysis
Daily portfolio risks were well-diversified, with idiosyncratic risk accounting for a small percentage of total risk.
Risk exposure plots confirmed the robustness of the optimization framework.
4. Discussion
The results affirm the effectiveness of APT in portfolio optimization. The integration of lasso regression for factor selection provided a systematic approach to identifying predictive alpha factors, reducing overfitting and enhancing generalization. Backtesting demonstrated the model's ability to generate consistent returns while maintaining risk within acceptable thresholds.
5. Conclusion
This study successfully applied multi-factor modeling and APT principles to portfolio optimization. The findings underscore the value of integrating advanced regression techniques and risk modeling into investment decision-making. Future research could further refine these methods to accommodate dynamic market conditions.
