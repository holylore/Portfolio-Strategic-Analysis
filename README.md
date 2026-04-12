# Portfolio Strategic Analysis - Core-Satellite Framework

This project features a comprehensive financial modeling system designed to monitor and analyze a Core-Satellite investment strategy. The objective was to build a scalable architecture that integrates raw transaction data into a professional-grade analytical suite.

<img width="1857" height="783" alt="Screenshot 2026-04-10 182648" src="https://github.com/user-attachments/assets/59c427ab-3845-4f28-b3b8-8936a52a2c3f" />

# Technical Methodology (The Excel Engine)
The core of the analysis was developed using advanced Microsoft Excel functions to ensure data accuracy and model stability:

Dynamic Data Sourcing: Automated retrieval of historical price series for both assets and global benchmarks (S&P 500, MSCI World) through the STOCKHISTORY function.

Weighted Performance Modeling: Engineered a return calculation framework using a combination of SUMPRODUCT and TRANSPOSE to dynamically weight portfolio performance against individual asset allocations.

Risk and Volatility Metrics: Volatility was derived using STDEV.P on daily returns and subsequently annualized based on active trading days. IFERROR handling was implemented to maintain model integrity across assets with inconsistent data histories.

Diversification Analysis: A Pearson Correlation Matrix was generated to identify interdependence between "Satellite" positions and "Core" holdings.

<img width="1887" height="773" alt="Screenshot 2026-04-12 185721" src="https://github.com/user-attachments/assets/6b2901de-1342-47f8-90a3-2596565cbd9a" />

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

<img width="1765" height="855" alt="Screenshot 2026-04-10 182741" src="https://github.com/user-attachments/assets/203bf5c5-092e-4088-8205-c91b43e98717" />

# Validation via Kaggle:

The project methodology and workflow were shared on Kaggle to facilitate peer review and validate the technical approach within the data science community.

# Project links:

https://www.kaggle.com/code/lorenzopardini/strategic-portfolio-analysis-risk-management
https://public.tableau.com/app/profile/lorenzo.pardini/vizzes
