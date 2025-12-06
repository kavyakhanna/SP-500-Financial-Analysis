# SP 500 Financial Analysis

## 1. Research Question

What are you investigating, and why does it matter?
1.This project investigates whether certain sectors within the S&P 500 — specifically Telecommunication — differ significantly in average operational profitability (EBITDA) and overall financial performance. The goal is to determine if Telecommunication companies truly outperform other companies in terms of how efficiently they generate profits from their operations.

2. This project helps us understand how different business sectors perform financially. By using methods like bootstrapping and permutation tests, we can go beyond basic summaries and measure how confident we are in the results. These insights can help investors and analysts make smarter, data-driven decisions and demonstrate how statistical testing can be applied to real-world financial data.

## 2. Hypothesis

State your null and alternative hypotheses clearly and succinctly.

1. Null Hypothesis: There is no difference in EBIDTA mean for telecommunication companies and mean EBIDTA for companies in all sectors.
2. Alternative Hypothesis: There is a difference in EBIDTA mean for telecommunication companies and mean EBIDTA for companies in all sectors.

## 3. Data Description

Describe your data source(s):

* Where it comes from (URL, API, dataset name)
1.Source: Kaggle Dataset https://www.kaggle.com/datasets/paytonfisher/sp-500-companies-with-financial-information/data

2.file name: Financials.csv 

3.Description:
The dataset compiles financial statement information for companies included in the S&P 500 index. Each row represents a company-year observation, containing various financial performance indicators.

* What each observation represents (unit of analysis)
Each observation represents one S&P 500 company and its associated financial data (e.g., price, earnings, market cap, and sector)

* Number of observations and key variables
Observation: 505 rows and 14 columns
The key variables include:
Symbol – Stock ticker symbol (e.g., AAPL, MSFT)
Name – Company name
Sector – Industry classification (e.g., Technology, Financials, Healthcare)
Price – Current stock price
Price/Earnings (P/E) – Valuation measure comparing price to earnings
Dividend Yield – Annual dividends as a percentage of price
Earnings/Share (EPS) – Company profit per share
52 Week Low / 52 Week High – Lowest and highest stock prices in the past year
Market Cap – Company size (price × shares outstanding)
EBITDA – Earnings before interest, taxes, depreciation, and amortization
Price/Sales and Price/Book – Additional valuation ratios
SEC Filings – Link to official U.S. Securities and Exchange Commission documents
Price/Earnings (P/E) – Valuation multiple
Market Cap – Total market capitalization (size indicator)

* Any filtering, cleaning, or transformation steps
1. Dropped Price/Book column 
2. Handle missing values for Price/Earning with median 
3. change the format for float with 2 decimal places for better readilibility

## 4. Methods

Summarize how you analyzed the data:

* The test statistic for your permutation test : Mean
* How you simulated or resampled under the null hypothesis :
* The metric(s) for which you created bootstrap confidence intervals
* Why the CLT does not apply to at least one metric

## 5. Results

Present your main findings:

* Key summary statistics and visualizations
* Observed test statistic and p-value (if applicable)
* Bootstrap confidence intervals for relevant metrics

## 6. Uncertainty Estimation

Discuss your resampling results:

* How many resamples you used
* What the bootstrap or randomization distributions looked like
* How you interpret the interval estimates

## 7. Limitations

Briefly note any limitations in data, assumptions, or methods, including sources of bias or missing data.

## 8. References

List all datasets, tools, libraries, or papers you cited.

---

**Reminder:** Your README should be clear enough that someone unfamiliar with your work could understand what you studied, how you analyzed it, and what you found.

