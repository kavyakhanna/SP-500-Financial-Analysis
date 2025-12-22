# SP 500 Financial Analysis

## 1. Research Question

What are you investigating, and why does it matter?
1. This project investigates whether certain sectors within the S&P 500 — specifically Telecommunication — differ significantly in average operational profitability (EBITDA) and overall financial performance. The goal is to determine if telecommunication companies truly outperform other companies in terms of how efficiently they generate profits from their operations.

2. This project helps us understand how different business sectors perform financially. By using methods like bootstrapping and permutation tests, we can go beyond basic summaries and measure how confident we are in the results. These insights can help investors and analysts make smarter, data-driven decisions and demonstrate how statistical testing can be applied to real-world financial data.

## 2. Hypothesis

State your null and alternative hypotheses clearly and succinctly.

1. Null Hypothesis: There is no difference in the EBITDA mean for telecommunication companies and the mean EBITDA for non-telecommunication companies.
2. Alternative Hypothesis: There is a difference in the EBITDA mean for telecommunication companies and the mean EBITDA for non-telecommunication companies.

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
Price/Earnings (P/E) – A valuation measure comparing price to earnings
Dividend Yield – Annual dividends as a percentage of price
Earnings/Share (EPS) – Company profit per share
52 Week Low / 52 Week High – Lowest and highest stock prices in the past year
Market Cap – Company size (price × shares outstanding)
EBITDA – Earnings before interest, taxes, depreciation, and amortisation
Price/Sales and Price/Book – Additional valuation ratios
SEC Filings – Link to official U.S. Securities and Exchange Commission documents
Market Cap – Total market capitalisation (size indicator)

* Any filtering, cleaning, or transformation steps
1. Dropped Price/Book column 
2. Handle missing values for Price/Earnings with the median 
3. Change the format for float with 2 decimal places for better readability

## 4. Methods

Summarize how you analyzed the data:

* The test statistic for your permutation test : Difference in mean EBITDA (Telecom - non-telecom)
* How you simulated or resampled under the null hypothesis : By randomly shuffling the groups telecom and non-telecom and recalculating the difference in median 10,000 tiimes. 
* The metric(s) for which you created bootstrap confidence intervals: I used the bootstrap to estimate uncertainty for the difference in median Price‑to‑Earnings (P/E) ratios between the top‑20 non‑telecom companies (by market cap) and the rest of the non‑telecom companies. By resampling each group with replacement and computing the median difference 10,000 times obtained a 95% confidence interval. 
* Why the CLT does not apply to at least one metric : The CLT doesn’t apply because the sample size (top 20 firms) is small, the P/E ratios are highly skewed with outliers, and the metric used is the median, which doesn’t follow a normal distribution. Therefore, bootstrapping was used instead of the CLT to estimate uncertainty.

## 5. Results

Present your main findings:

* Key summary statistics and visualizations: The Telecommunication Services sector showed the highest median EBITDA among all S&P 500 sectors. Visualizations confirmed strong profitability for Telecom, while the Financial sector showed negative median EBITDA.
* Observed test statistic and p-value (if applicable): The observed difference in mean EBITDA between Telecommunication and Non-Telecommunication companies was approximately 30 billion USD, with a p-value ≈ 0.00003. This indicates that Telecom companies are significantly more profitable than other sectors.
* Bootstrap confidence intervals for relevant metrics: For the median P/E ratio difference between the top-20 non-telecom firms and the rest, the 95 % bootstrap confidence interval included 0, suggesting no significant difference in valuation between the biggest and smaller non-telecom companies.

## 6. Uncertainty Estimation

Discuss your resampling results:

* How many resamples you used: Both the permutation test and the bootstrap analysis used 10,000 resamples
* What the bootstrap or randomization distributions looked like: The permutation distribution of mean EBITDA differences centred around zero, representing no difference. But the observed difference lay far in the tail of the distribution, indicating the statistically significant effect. While the bootstrap distribution of median P/E differences was roughly symmetric and centered near zero, suggesting no difference between the top-20 and remaining non-telecom companies.
* How you interpret the interval estimates : The 95% bootstrap confidence interval includes zero which means difference is not stastically significant. Whereas the permutation test for mean EBITDA showed a stastically result confirming that telecom companies profit more than non-telecom.

## 7. Limitations

Briefly note any limitations in data, assumptions, or methods, including sources of bias or missing data : 
The dataset represents a single snapshot of S&P 500 companies, which may not capture year-to-year financial variability. Another limitation would be the presence of extreme outliers which can skew the data and overall results. The analysis assumes that missing values imputed or dropped do not bias the results, but this cannot be fully guaranteed.

## 8. References

List all datasets, tools, libraries, or papers you cited.
Dataset : Kaggle Dataset 
Tools & libraries : Python 3.11, Pandas, NumPy, Matplotlib
Statistical Methods: Bootstrapping and Permutation Testing for non-parametric inference
Course Reference: SEIS 631 – Data Preparation & Analysis (University of St. Thomas, Fall 2025)


