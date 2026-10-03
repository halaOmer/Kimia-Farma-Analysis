# Bank Customer Churn Analysis – Power BI

## 📌 Project Overview

This project analyzes customer churn for a banking dataset using **Power BI**.

The objective is to understand which customer characteristics are associated with churn, identify differences in customer behavior across countries, and discover meaningful customer segments.

The project follows a practical analytics workflow from data preparation and KPI development to visualization, segmentation, and business insights.

## 🎯 Business Questions

The analysis focuses on four questions:

1. What attributes are more common among churners than non-churners?
2. Can churn be predicted using the variables in the data?
3. Is there a difference between German, French, and Spanish customers in terms of account behavior?
4. What types of segments exist within the bank's customers?

## 📊 Dataset

The dataset contains **10,000 bank customers** with information including:

- Credit Score
- Geography
- Gender
- Age
- Tenure
- Balance
- Number of Products
- Credit Card Ownership
- Active Membership Status
- Estimated Salary
- Churn / Exit Status

### Target Variable

`Exited`

- `0` = Non-Churner
- `1` = Churner

Overall churn rate: **20.37%**.

## 🛠️ Tools & Technologies

- Power BI Desktop
- Power Query
- DAX
- Exploratory Data Analysis
- Data visualization
- Customer segmentation
- Predictive analysis

## 🔄 Project Workflow

### 1. Data Preparation

The data was imported into Power BI and prepared by checking:

- Data types
- Missing values
- Duplicate records
- Categorical variables
- Numerical variables
- Target-variable consistency

A customer-status field was created:

```text
Exited = 1 → Churner
Exited = 0 → Non-Churner
```

### 2. KPI Development

Main KPIs include:

| KPI | Description |
|---|---|
| Total Customers | Total number of customers |
| Churned Customers | Number of customers who exited |
| Non-Churned Customers | Number of customers who remained |
| Churn Rate | Percentage of customers who exited |
| Average Age | Average customer age |
| Average Balance | Average account balance |
| Average Credit Score | Average credit score |
| Average Products | Average number of products per customer |
| Active Customer Rate | Percentage of active customers |

### Example DAX Measures

```DAX
Total Customers =
COUNTROWS('Bank_Churn')
```

```DAX
Churned Customers =
CALCULATE(
    [Total Customers],
    'Bank_Churn'[Exited] = 1
)
```

```DAX
Non-Churned Customers =
CALCULATE(
    [Total Customers],
    'Bank_Churn'[Exited] = 0
)
```

```DAX
Churn Rate =
DIVIDE(
    [Churned Customers],
    [Total Customers],
    0
)
```

## 🔎 Analysis Performed

### 1. Churner vs Non-Churner Analysis

Customer characteristics were compared between churners and non-churners, including:

- Age
- Gender
- Geography
- Activity status
- Number of products
- Balance
- Credit score
- Credit card ownership
- Tenure
- Estimated salary

Important patterns include:

- Churners are older on average.
- Inactive customers have a higher churn rate than active customers.
- German customers have a substantially higher churn rate than French and Spanish customers.
- Number of products is strongly associated with churn behavior.
- Churners have a higher average balance than non-churners.

### 2. Demographic Analysis

The analysis covers:

- Age groups
- Gender
- Geography
- Customer activity

Age groups:

```text
18–24
25–34
35–44
45–54
55–64
65+
```

### 3. Geographic Analysis

Customers were compared across France, Germany, and Spain.

Key metrics:

- Customer count
- Churn rate
- Average balance
- Average products
- Activity rate
- Gender distribution

| Country | Churn Rate |
|---|---:|
| France | 16.15% |
| Germany | 32.44% |
| Spain | 16.67% |

### 4. Customer Segmentation

Customer segments were explored using combinations of:

- Geography
- Gender
- Age group
- Activity status
- Number of products

Examples:

```text
Geography × Gender
Age Group × Activity Status
Number of Products × Activity Status
```

## 📈 Power BI Dashboard

### Page 1 — Churn Overview

- Total Customers
- Churned Customers
- Non-Churned Customers
- Churn Rate
- Churn Rate by Age Group
- Churn Rate by Gender
- Churn Rate by Activity Status
- Churn Rate by Number of Products

### Page 2 — Geography & Customer Behavior

- Churn Rate by Country
- Customer Distribution by Country
- Average Balance by Country
- Average Products by Country
- Activity by Country
- Churn Rate by Country and Gender

### Page 3 — Customer Segmentation

- Geography × Gender
- Age × Activity
- Product × Activity
- Customer count by segment
- Churn rate by segment
- Average balance by segment

## 💡 Key Insights

### Age
Older customer groups show considerably higher churn rates than younger groups.

### Activity
Inactive members have a higher churn rate than active members.

### Geography
Germany has a much higher churn rate than France and Spain in this dataset.

### Number of Products
Customers with different numbers of products show substantially different churn behavior.

### Customer Segments
Combining geography, gender, age, activity, and product ownership reveals groups with noticeably different churn patterns.

## 📌 Predictive Analysis

The available variables can be used to build a churn prediction model.

Potential predictive features include:

- Age
- Number of Products
- Balance
- Estimated Salary
- Credit Score
- Activity Status
- Geography
- Gender
- Tenure
- Credit Card Ownership

A machine-learning extension can be implemented using Python and integrated with the Power BI analysis.

> Association between a variable and churn does not by itself prove that the variable causes customers to leave.

## 📁 Suggested Repository Structure

```text
Bank-Customer-Churn-Analysis/
│
├── README.md
├── data/
│   ├── Bank_Churn.csv
│   └── Bank_Churn_Data_Dictionary.csv
├── powerbi/
│   └── Bank_Customer_Churn.pbix
├── screenshots/
│   ├── churn-overview.png
│   ├── geography-analysis.png
│   └── customer-segmentation.png
└── documentation/
    └── insights.md
```

## 📚 Data Source

**Source:** Kaggle  
**License:** Public Domain

## 🚀 Future Improvements

- Build a machine-learning churn prediction model
- Add customer-level churn probability
- Create churn-risk classifications
- Perform feature-importance analysis
- Add advanced segmentation techniques
- Connect the dashboard to regularly updated data
- Develop retention-focused business recommendations

## 👤 Project Purpose

This project was created as a **data analytics portfolio project** to demonstrate practical skills in:

- Data cleaning
- Power Query
- Data modeling
- DAX
- KPI development
- Exploratory data analysis
- Customer segmentation
- Data visualization
- Business insight generation
- Power BI dashboard development
