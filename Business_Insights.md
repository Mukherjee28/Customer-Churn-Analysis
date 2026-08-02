# 📊 Project Report, Business Insights And Observations

## Project Overview
This project analyzes customer churn by integrating customer demographics, subscription details, and customer support records. The objective is to identify the major factors contributing to customer churn, quantify the financial impact, and provide actionable recommendations to improve customer retention.
The analysis follows a complete data analytics workflow consisting of:
- Data Extraction from SQLite
- Data Cleaning & Preprocessing
- Data Integration
- Exploratory Data Analysis (EDA)
- KPI Calculation
- Business Insight Generation
- Interactive Power BI Dashboard

# 🎯 Business Objective
The primary business objectives of this project are to:
- Measure the overall customer churn rate.
- Identify customer segments with the highest churn.
- Quantify revenue and Customer Lifetime Value (CLTV) lost due to churn.
- Analyze the impact of subscription plans, contract types, customer complaints, and geographical locations on churn.
- Provide data-driven recommendations to improve customer retention and business profitability.

# 📂 Dataset Summary
The analysis combines three relational datasets.
| Dataset | Description |
|----------|-------------|
| Customer | Customer demographic information |
| Subscription | Subscription details and revenue information |
| Support | Customer complaints and support interactions |

### Final Dataset
| Metric | Value |
|--------|------:|
| Total Customers | 21 |
| Total Columns | 21 |
| Final Dataset | 21 Rows × 21 Columns |

# 🧹 Data Cleaning & Preprocessing

## Customer Table
The following preprocessing steps were performed:
- Renamed **Name** to **Customer Name**
- Removed unnecessary columns:
  - Interests
  - Pincode
- Converted Date of Birth to datetime format.
- Standardized Gender values:
  - Men → Male
  - Women → Female
- Filled missing Country values using State information.

## Subscription Table
Performed the following preprocessing:
- Converted Subscription Start Date into datetime format.
- Converted Renewal Date into datetime format.
- Converted Cancellation Date into datetime format.

Created a new feature:
| Churn Flag | Meaning |
|------------|----------|
| 1 | Cancelled Subscription |
| 0 | Active Subscription |

## Customer Support Table
The following steps were completed:
- Removed unnecessary columns.
- Converted Complaint Date into datetime.
- Calculated Complaint Count for each customer.

# 🔗 Data Integration
The cleaned tables were merged using **Customer ID**.
The final analytical dataset contains customer demographics, subscription information, revenue metrics, support history, and churn indicators in a single table for analysis.

# 📈 Business KPIs
## 1. Customer Churn Rate
**Result**
```
28.57%
```
### Business Insight
Nearly **3 out of every 10 customers** have cancelled their subscriptions.
This indicates that customer retention should be a major business priority.

## 2. Customer Retention Rate
**Result**
```
71.43%
```
### Business Insight
More than **70% of customers remain active**, indicating a stable customer base while still leaving room for retention improvements.

## 3. Churn by Subscription Plan
| Plan Type | Churn Rate |
|-----------|-----------:|
| Basic | **60.00%** |
| Standard | **22.22%** |
| Premium | **14.29%** |
### Business Insight
- Basic plan customers are significantly more likely to cancel.
- Premium customers demonstrate the highest loyalty.
- Improving the value proposition of the Basic plan could substantially reduce churn.

## 4. State-wise Churn Analysis
| State | Churn Rate |
|--------|-----------:|
| Karnataka | **100%** |
| Meghalaya | **66.67%** |
| Delhi | **25%** |
| Maharashtra | **0%** |
| Rajasthan | **0%** |
| Telangana | **0%** |
| Nagaland | **0%** |
| Kathmandu | **0%** |
### Business Insight
Karnataka experienced the highest customer churn, indicating the need to investigate regional factors such as pricing, service quality, or competition.

## 5. Churn by Subscription Source
| Subscription Source | Churn Rate |
|--------------------|-----------:|
| Referral | **83.33%** |
| Paid | **16.67%** |
| Organic | **0%** |
### Business Insight
Referral-acquired customers showed the highest churn, suggesting the referral program or onboarding experience may need improvement.

## 6. Average Revenue Per User (ARPU)
**Result**
```
18.85
```
### Business Insight
Each active customer contributes an average monthly revenue of **18.85**.
Increasing customer retention directly improves recurring revenue.

## 7. Average Customer Tenure
**Result**
```
1508 Days
```
### Business Insight
Customers stay with the company for approximately **4 years**, demonstrating strong long-term customer relationships despite the observed churn.

## 8. Revenue at Risk
**Result**
```
73.94
```
### Business Insight
The company is currently at risk of losing **73.94** units of recurring monthly revenue because of churned customers.
Reducing churn will directly improve recurring business income.

## 9. Escalation Rate
**Result**
```
19.05%
```
### Business Insight
Nearly **one in every five customers** required issue escalation, indicating opportunities to improve customer service quality.

## 10. Average Complaints Per Customer
**Result**
```
0.43
```
### Business Insight
Although complaint frequency is relatively low, customers with complaints are more likely to churn, highlighting the importance of proactive customer support.

## 11. Correlation Between Escalation and Churn
**Correlation Value**
```
0.77
```
### Business Insight
There is a **strong positive correlation** between support escalations and customer churn.
Customers experiencing unresolved issues are significantly more likely to cancel their subscriptions.

# 🎯 Customer Risk Segmentation
Customers were segmented based on their churn scores.
| Risk Category | Description |
|---------------|-------------|
| 🟢 Low Risk | Low probability of churn |
| 🟡 Medium Risk | Moderate probability of churn |
| 🔴 High Risk | High probability of churn |
### Business Value
This segmentation enables the business to prioritize high-risk customers for proactive retention campaigns before cancellation occurs.

# 📊 Exploratory Data Analysis (EDA)
The notebook includes multiple exploratory analyses to identify trends and relationships within the data.

## Monthly Churn Trend
### Purpose
- Identify months with increased customer churn.
- Detect seasonal churn behaviour.

## Churn by Subscription Plan
### Observation
Basic plan customers consistently experience the highest churn compared to Standard and Premium plans.

## State-wise Churn Distribution
### Observation
The geographical analysis reveals Karnataka as the highest-churn region, suggesting location-specific business challenges.

## Correlation Heatmap
The correlation matrix was generated to evaluate relationships between numerical variables including:
- Monthly Charges
- Customer Lifetime Value (CLTV)
- Churn Score
- Churn Flag
- Escalations

### Insight
Escalations show one of the strongest positive relationships with customer churn.

## Pair Plot
Pairwise visualizations were created to analyze distributions and relationships among numerical variables.

### Purpose
- Identify trends
- Detect outliers
- Observe customer segmentation patterns

## Facet Analysis
Facet plots were used to compare customer behaviour across:
- Subscription Plans
- Gender
- Churn Risk Categories

### Purpose
Visualize behavioural differences among customer groups.

# 📋 Pivot Table Analysis
## Pivot Table 1
### Customer Churn Rate by Plan
| Plan | Churn Rate |
|-------|-----------:|
| Basic | **60%** |
| Premium | **14.29%** |
| Standard | **22.22%** |

## Pivot Table 2
### Plan Performance Summary
| Plan | Customers | Revenue | Churn Rate |
|------|----------:|---------:|-----------:|
| Basic | 5 | 52.95 | 60% |
| Standard | 9 | 123.91 | 22.22% |
| Premium | 7 | 218.93 | 14.29% |

### Business Insight
Although the Premium plan contributes the highest revenue, it experiences the lowest churn, making it the most profitable customer segment.

# 📊 Power BI Dashboard Summary
The Power BI dashboard provides interactive visualizations for monitoring customer churn.
### Dashboard KPIs
- Customer Churn Rate
- Revenue at Risk
- Customer Lifetime Value (CLTV) Lost
- Average Churn Score

### Dashboard Visualizations
- Customer Churn by Plan Type
- Revenue at Risk by Contract Type
- Complaints by Churn Status
- State-wise Churn Distribution

### Interactive Filters
- Plan Type
- Gender
- Contract Type

# 💡 Key Business Findings
- Overall customer churn rate is **28.57%**.
- Customer retention rate stands at **71.43%**.
- Basic subscription customers experience the highest churn (**60%**).
- Karnataka records the highest customer churn among all states.
- Referral customers churn significantly more than organically acquired customers.
- Average customer tenure exceeds **1,500 days**, indicating strong long-term customer relationships.
- Monthly recurring revenue worth **73.94** is currently at risk.
- Premium subscribers contribute the highest revenue while maintaining the lowest churn.
- Customer escalations show a strong positive correlation (**0.77**) with churn.

# 🚀 Business Recommendations

## Improve Basic Subscription Plan
Enhance pricing, features, or loyalty benefits to reduce churn among Basic plan customers.

## Strengthen Customer Support
Reduce escalations by improving response times and resolving customer issues proactively.

## Focus on High-Risk Customers
Use churn scores to identify customers likely to cancel and launch targeted retention campaigns.

## Investigate High-Churn Regions
Conduct detailed analysis in Karnataka to identify regional challenges affecting customer retention.

## Improve Referral Customer Experience
Review referral incentives and onboarding processes to improve the quality and retention of referred customers.

## Increase Premium Plan Adoption
Encourage customers to upgrade to Premium plans through promotional offers and additional benefits.

# 📌 Conclusion

This project demonstrates a complete end-to-end customer churn analysis workflow using SQL, Python, and Power BI. By integrating multiple business datasets, cleaning and transforming the data, performing exploratory analysis, and building an interactive dashboard, the project provides actionable insights into customer behaviour, revenue impact, and churn drivers.

The findings enable businesses to make informed, data-driven decisions that improve customer retention, minimize revenue loss, and maximize long-term customer value.
