# Portfolio Strategic Analysis - Core-Satellite Framework

This project features a comprehensive financial modeling system designed to monitor and analyze a Core-Satellite investment strategy. The objective was to build a scalable architecture that integrates raw transaction data into a professional-grade analytical suite.

<img width="1896" height="812" alt="Screenshot 2026-03-25 154717" src="https://github.com/user-attachments/assets/da1fb59c-ed47-4422-915a-8e0de78a44b4" />

# Technical Methodology (The Excel Engine)
The core of the analysis was developed using advanced Microsoft Excel functions to ensure data accuracy and model stability:

Dynamic Data Sourcing: Automated retrieval of historical price series for both assets and global benchmarks (S&P 500, MSCI World) through the STOCKHISTORY function.

Weighted Performance Modeling: Engineered a return calculation framework using a combination of SUMPRODUCT and TRANSPOSE to dynamically weight portfolio performance against individual asset allocations.

Risk and Volatility Metrics: Volatility was derived using STDEV.P on daily returns and subsequently annualized based on active trading days. IFERROR handling was implemented to maintain model integrity across assets with inconsistent data histories.

Diversification Analysis: A Pearson Correlation Matrix was generated to identify interdependence between "Satellite" positions and "Core" holdings.

<img width="1897" height="772" alt="Screenshot 2026-03-25 150441" src="https://github.com/user-attachments/assets/a2eda05f-9401-4482-a16b-6b6af4150fbe" />

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

<img width="1813" height="895" alt="Screenshot 2026-03-26 100858" src="https://github.com/user-attachments/assets/302bb007-7f0a-4b92-9eef-0aa145fbe70c" />

# Validation via Kaggle:

The project methodology and workflow were shared on Kaggle to facilitate peer review and validate the technical approach within the data science community.

# Project links:

https://www.kaggle.com/code/lorenzopardini/strategic-portfolio-analysis-risk-management
https://public.tableau.com/views/TableauViz_17745153676280/holyloresPortfolio_?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
