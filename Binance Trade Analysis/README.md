
# Binance Trade Report :
### DATA SET LINK : https://drive.google.com/file/d/1E3T8i1akfm6NnT42AWEE6U1t7uvwreYK/view?usp=drive_link
## 1. Introduction 
This report presents an analysis of Binance trade data to evaluate trading performance across different accounts. The study focuses on calculating financial metrics, ranking accounts based on performance, and identifying the top 20 accounts using a weighted scoring system.

## 2. Data Exploration and Cleaning
### 2.1 Data Loading
The dataset includes trading history for multiple accounts, with fields such as:
•	Port_IDs (Account ID)
•	Trade details (symbol, side, price, fee, quantity, realized profit, etc.)
•	Timestamps (converted to datetime format)
### 2.2 Data Cleaning
•	Converted timestamps from milliseconds to datetime format.
•	Handled missing values by filling or dropping as necessary.
•	Converted JSON-like trade history into structured tabular format.
### 3. Feature Engineering
To evaluate account performance, we computed the following metrics:
### 3.1 Key Metrics Computed
    •	PnL (Profit and Loss): Sum of realized profit for each account.
    •	Total Investment: Sum of invested amounts.
    •	ROI (Return on Investment): PnLTotal Investment\frac{PnL}{Total\ Investment}
    •	Win Rate: Win PositionsTotal Positions×100\frac{Win\ Positions}{Total\ Positions} \times 100
    •	Sharpe Ratio: Mean PnLStandard Deviation of PnL\frac{Mean\ PnL}{Standard\ Deviation\ of\ PnL}
    •	MDD (Maximum Drawdown): Maximum loss from peak to trough in cumulative returns.

### 3.2 Normalization of Metrics
To ensure fair ranking, metrics were normalized using Min-Max scaling: Xnormalized=X−XminXmax−XminX_{normalized} = \frac{X - X_{min}}{X_{max} - X_{min}}
### 4. Ranking Algorithm
A weighted scoring system was used to rank accounts:
### 4.1 Weight Assignment
Weights were assigned to each metric based on importance:
Metric	Weight
ROI	30%
Sharpe Ratio	25%
Win Rate	20%
MDD	15%
PnL	10%
### 4.2 Computation of Final Score
Final Score=∑(Metricnormalized×Weight)Final\ Score = \sum (Metric_{normalized} \times Weight)
### 4.3 Ranking Accounts
•	Accounts were ranked in descending order based on the final score.
•	The top 20 accounts were extracted.
### 5. Results and Findings
•	The highest-ranked accounts showed a balance of high ROI, positive PnL, and consistent win rates.
•	Some accounts had high profits but poor Sharpe Ratios, indicating inconsistent returns.
•	Accounts with significant drawdowns (MDD) were penalized in rankings.
### 6. Conclusion
This analysis provides a structured approach to evaluating trading performance. The weighted ranking method ensures a balanced assessment, considering both risk and return factors. Further improvements can include:

    •	Incorporating additional risk-adjusted metrics.
    •	Enhancing weight selection using statistical methods.
    •	Visualizing trends for deeper insights.
________________________________________


