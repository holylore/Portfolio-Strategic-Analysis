# Portfolio Strategic Analysis - Core-Satellite Framework

This project features a comprehensive financial modeling system designed to monitor and analyze a Core-Satellite investment strategy. The objective was to build a scalable architecture that integrates raw transaction data into a professional-grade analytical suite.

<img width="1855" height="742" alt="Screenshot 2026-04-19 095904" src="https://github.com/user-attachments/assets/67d32e0a-f491-4a94-8623-cbb9a96817b3" />

# Technical Methodology (The Excel Engine)
The core of the analysis was developed using advanced Microsoft Excel functions to ensure data accuracy and model stability:

Dynamic Data Sourcing: Automated retrieval of historical price series for both assets and global benchmarks (S&P 500, MSCI World) through the STOCKHISTORY function.

Weighted Performance Modeling: Engineered a return calculation framework using a combination of SUMPRODUCT and TRANSPOSE to dynamically weight portfolio performance against individual asset allocations.

Risk and Volatility Metrics: Volatility was derived using STDEV.P on daily returns and subsequently annualized based on active trading days. IFERROR handling was implemented to maintain model integrity across assets with inconsistent data histories.

Diversification Analysis: A Pearson Correlation Matrix was generated to identify interdependence between "Satellite" positions and "Core" holdings.

<img width="1866" height="747" alt="Screenshot 2026-04-19 095842" src="https://github.com/user-attachments/assets/8ca33c5c-80ba-4350-bfeb-b74a78f102a9" />

# Scalability and Dynamic Logic
The model is built as a relational system rather than a static spreadsheet. The connection between the Movements Table (Transactions) and the Insights Table (Aggregated Data) is governed by a dynamic array formula:

=UNIQUE(FILTER(MovementsTable.[Stocks.]; SUMIFS(MovementsTable.[Quantity.]; MovementsTable.[Stocks.]; MovementsTable.[Stocks.])>0))

Functional Logic: This formula ensures the dashboard automatically reflects only active positions where the quantity is greater than zero.

Operational Scalability: The system is designed to be future-proof. Adding new trades or assets to the ledger updates the entire analytical pipeline—from Excel summaries to Tableau visualizations—without requiring manual formula revisions.

Data Protocol: While the logic is automated, the model follows a manual refresh protocol to allow for controlled reporting cycles.

# Visual Intelligence and Validation
To provide stakeholder-ready insights, the processed data is integrated into an interactive Tableau suite:

Risk-Adjusted Efficiency: A scatter plot mapping the Sharpe Ratio against Volatility to identify the most efficient capital allocators.

Benchmark Comparison: A time-series analysis tracking the portfolio's growth trajectory against market leaders.

<img width="1884" height="970" alt="Screenshot 2026-04-19 095732" src="https://github.com/user-attachments/assets/398df22a-a7db-41a0-9e75-27c63e829786" />

# Validation via Kaggle:

The project methodology and workflow were shared on Kaggle to facilitate peer review and validate the technical approach within the data science community.

# Project links:

https://www.kaggle.com/code/lorenzopardini/strategic-portfolio-analysis-risk-management
https://public.tableau.com/app/profile/lorenzo.pardini/vizzes
