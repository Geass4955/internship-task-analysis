# Marketing Campaign Effectiveness Analysis

Evaluating the effectiveness of marketing campaigns using data cleaning, feature engineering,
exploratory data analysis, and visualization — with the goal of identifying which campaigns
performed best, what drives conversions, and what to do differently next time.

## Dataset

**Marketing Campaign Performance Dataset** (Kaggle) — 200,000 marketing campaigns run by 5
companies across 5 channels and 5 campaign types during 2021.

| Column | Description |
|---|---|
| `Campaign_ID` | Unique campaign identifier |
| `Company` | Company running the campaign |
| `Campaign_Type` | Email, Influencer, Display, Search, Social Media |
| `Target_Audience` | Demographic targeted |
| `Duration` | Campaign length ("30 days" etc.) |
| `Channel_Used` | Platform the campaign ran on |
| `Conversion_Rate` | Share of engaged users who converted |
| `Acquisition_Cost` | Total campaign spend |
| `ROI` | Return on investment |
| `Location` | City targeted |
| `Language` | Campaign language |
| `Clicks` / `Impressions` | Raw traffic counts |
| `Engagement_Score` | 1-10 engagement rating |
| `Customer_Segment` | Audience segment |
| `Date` | Date the campaign ran |



## What the Notebook Does

1. **Dataset Overview** — load the data, check structure, dtypes, and summary statistics.
2. **Data Cleaning** — fix `Acquisition_Cost` (currency string → float), `Duration` (text →
   int days), and `Date` (text → datetime); check `Acquisition_Cost` and `Conversion_Rate` for
   outliers with boxplots and the IQR rule.
3. **Data Transformation** — engineer `CTR`, `Estimated_Conversions`, and `CPA`; one-hot encode
   all categorical columns and Min-Max scale the numeric ones into a separate modeling-ready
   table.
4. **Univariate Analysis** — distribution of campaign types, channels, audiences, segments,
   conversion rate, ROI, CTR, and engagement score.
5. **Bivariate Analysis** — conversion rate and ROI by channel, campaign type, and location;
   CPA by channel; performance over time; top and bottom performing campaigns.
6. **Multivariate Analysis** — correlation heatmap, a Channel × Campaign Type performance
   heatmap, and a sampled pairplot of the core metrics.
7. **Business Insights** — the best-performing channel, campaign type, and combination of the
   two, plus practical recommendations for future campaigns.
8. **Documentation & Summary** — a written recap of the whole pipeline and its findings.

## Key Tools

- **Pandas** — loading, cleaning, and aggregating the data
- **NumPy** — numeric operations (IQR bounds, safe division for CPA)
- **Matplotlib / Seaborn** — every chart in the notebook
- **scikit-learn** — one-hot encoding is via `pandas.get_dummies`; `MinMaxScaler` is used for
  numeric scaling in the transformation step

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook Marketing_Campaign_Effectiveness_Analysis.ipynb
```

## Author

Avinash Yadav
