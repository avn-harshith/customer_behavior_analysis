# Customer Shopping Behavior Analysis

An end-to-end data analytics project exploring customer purchasing patterns, product preferences, subscription behavior, discounts, and revenue using **Python, PostgreSQL, and Power BI**.

## Overview

Retail businesses need to understand who their customers are, what drives spending, and how customer loyalty and promotions relate to purchasing behavior. This project analyzes transaction data to answer these questions and turn the findings into practical business recommendations.

The workflow covers data loading, exploratory data analysis (EDA), data cleaning, SQL analysis, dashboard development, and final reporting.

## Dataset

- **Records:** 3,900 purchases
- **Columns:** 18
- **Domain:** Retail / Customer Shopping Behavior
- **Key information:** Customer demographics, product category and item, purchase amount, subscription status, discounts and promotions, previous purchases, review ratings, and shipping type.
- **Missing data:** 37 values in the review-rating column.

*Place the dataset in the `dataset/` folder. Check the original dataset's license and terms before sharing it publicly.*

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data preparation and analysis |
| Pandas | Loading, cleaning, and transforming data |
| NumPy | Numerical operations |
| Matplotlib / Seaborn | Exploratory visualizations, if used |
| PostgreSQL | SQL-based business analysis |
| SQLAlchemy | Connecting Python to PostgreSQL |
| Power BI | Interactive dashboard and KPI visualization |
| Gamma | Creating the project presentation |
| Jupyter Notebook / VS Code | Development environment |
| Git & GitHub | Version control and project portfolio |

## Project Workflow

### 1. Data Loading and EDA
- Loaded the dataset into Python with Pandas.
- Reviewed the data structure and summary statistics using `df.info()` and `df.describe()`.
- Examined numerical and categorical columns to understand customer and purchase characteristics.

### 2. Data Cleaning and Preparation
- Identified missing review ratings and filled them using the median rating for each product category.
- Standardized column names using `snake_case`.
- Created an `age_group` feature by grouping customer ages.
- Created a `purchase_frequency_days` feature from purchase-frequency information.
- Checked the overlap between `discount_applied` and `promo_code_used`, then removed the redundant `promo_code_used` column as documented in the analysis.
- Loaded the cleaned DataFrame into PostgreSQL for further analysis.

### 3. SQL Analysis
Wrote 10 SQL queries in PostgreSQL to investigate business questions, including:

- How does revenue differ by gender?
- Which customers used discounts but still spent above the average purchase amount?
- Which products have the highest average review ratings?
- How do average purchase amounts compare for Standard and Express shipping?
- Do subscribers and non-subscribers have different average spending?
- Which products have the highest discount rates?
- How are customers distributed across New, Returning, and Loyal segments?
- Which products are most frequently purchased within each category?
- How many repeat buyers are subscribers?
- Which age groups contribute the most revenue?

### 4. Power BI Dashboard
Built an interactive dashboard with key metrics and visual summaries.

**Headline KPIs**
- Total customers/purchases displayed: **3.9K**
- Average purchase amount: **$59.76**
- Average review rating: **3.75**

**Dashboard features**
- Subscription status breakdown
- Revenue and purchase comparisons by product category
- Revenue comparisons by age group
- Slicers for subscription status, gender, category, and shipping type

The dashboard lets users explore customer and purchase patterns through interactive filters.

### 5. Report and Presentation
- Prepared a report describing the dataset, cleaning process, SQL analysis, results, dashboard, and business recommendations.
- Created a presentation using Gamma to communicate the problem, workflow, findings, and recommendations concisely.

## Key Results

The analysis produced the following findings:

- **Revenue by gender:** Male customers generated **$157,890**, while female customers generated **$75,191** in the analyzed data.
- **Subscription spending:** Subscribers spent an average of **$59.49**, compared with **$59.87** for non-subscribers.
- **Age group revenue:** Young Adults contributed the highest reported revenue at **$62,143**; Seniors contributed **$55,763**.
- **Customer segments:** **3,116** customers were classified as Loyal, **701** as Returning, and **83** as New.
- **Shipping:** Average purchase amount was **$60.48** for Express shipping and **$58.46** for Standard shipping.
- **Product ratings:** Gloves had the highest reported average rating (**3.86**), followed by Sandals (**3.84**) and Boots (**3.82**).
- **Discount dependence:** Hats had the highest reported discount rate (**50%**), followed by Sneakers (**49.66%**) and Coats (**49.07%**).

### Business Recommendations

- Test meaningful subscriber benefits, such as free shipping or exclusive offers, to improve subscription value.
- Introduce loyalty rewards to encourage repeat purchases and strengthen retention.
- Review discount frequency and profit margins for products with high discount rates.
- Use the strong revenue contribution from Young Adults to inform targeted marketing experiments.
- Highlight well-rated and popular products in promotional campaigns.

*These are descriptive findings from the supplied project report; they do not by themselves establish causation.*

## Project Structure

```text
customer-shopping-behavior-analysis/
├── dataset/
│   ├── raw_data.csv
│   └── cleaned_data.csv
├── notebooks/
│   └── exploratory_data_analysis.ipynb
├── sql/
│   └── analysis_queries.sql
├── dashboard/
│   ├── customer_behavior_dashboard.pbix
│   └── dashboard.png
├── reports/
│   └── customer_shopping_behavior_report.pdf
├── presentation/
│   └── customer_shopping_behavior_presentation.pdf
├── requirements.txt
└── README.md
```

Update the filenames to match the files included in your repository. Add a dashboard screenshot at `dashboard/dashboard.png` if you want it to appear in this README.

## How to Run

### Prerequisites
- Python 3.x
- Jupyter Notebook or VS Code
- PostgreSQL
- Power BI Desktop

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

### 2. Install Python dependencies

If you have a `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Otherwise, install the core packages:

```bash
pip install pandas numpy sqlalchemy psycopg2-binary jupyter matplotlib seaborn
```

### 3. Prepare the dataset

Place the source CSV in the `dataset/` directory and open the notebook in `notebooks/`. Run the notebook cells in order to inspect, clean, and transform the data.

### 4. Configure PostgreSQL

- Create a PostgreSQL database for the project.
- Configure your connection settings locally.
- Run the notebook/database-loading steps to import the cleaned DataFrame.
- Execute the SQL scripts in the `sql/` directory.

Do not commit database passwords or other secrets to GitHub. Use environment variables or a local configuration file excluded through `.gitignore`.

### 5. Open the Power BI dashboard

Open the `.pbix` file in Power BI Desktop. If prompted, update the data-source settings and refresh the data.

### 6. Review the deliverables

Open the report in `reports/` and the presentation in `presentation/` to review the complete analysis and conclusions.

## Deliverables

- Python notebook for EDA and data preparation
- PostgreSQL SQL queries
- Interactive Power BI dashboard
- Project report
- Gamma presentation

## Author

**A. V. N. Harshith**

Data Analytics Portfolio Project

- GitHub: `https://github.com/<your-username>`
- LinkedIn: `<your-linkedin-profile>`

---

If you found this project useful, feel free to star the repository.
