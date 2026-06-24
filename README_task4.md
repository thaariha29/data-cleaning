# 🧹 Task 4 — Data Cleaning & Reporting Automation

> **Thiranex Internship Portal | Data Analytics Domain**  
> Automate data cleaning and reporting workflows using Python.

---

## 📌 Overview

This project implements a fully **automated data cleaning and reporting pipeline** in Python. It detects and fixes all common real-world data quality issues, then generates a professional visual report and business insights summary — with zero manual intervention.

---

## ✅ Key Features Implemented

| # | Requirement | Status |
|---|---|---|
| 1 | Use Python for automation | ✅ Done |
| 2 | Handle missing values, duplicates, and inconsistent data | ✅ Done |
| 3 | Generate automated reports and visual summaries | ✅ Done |

### Expected Outcomes Covered
- ✅ **Data preprocessing automation** — 8-step cleaning pipeline runs end-to-end
- ✅ **Reporting efficiency** — One command generates cleaned CSV + 9-panel visual dashboard + printed business insights

---

## 🗂️ Project Structure

```
data-cleaning-automation-task4/
│
├── data_cleaning_automation.py      # Main automation script
├── sample_sales_data.csv            # Raw messy input data (205 rows)
├── cleaned_data_sample_output.csv   # Cleaned output (200 rows × 15 cols)
├── data_cleaning_report.png         # Visual summary dashboard
├── README.md                        # Project documentation
└── LICENSE                          # MIT License
```

---

## 🔧 Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core automation language |
| Pandas | Data manipulation & cleaning pipeline |
| NumPy | Numerical operations |
| Matplotlib | Visual dashboard generation |
| argparse | CLI support for custom input/output paths |

---

## 🧪 Data Quality Issues Handled

The script detects and fixes **7 categories** of real-world data problems:

| Issue Type | Detection Method | Fix Applied |
|---|---|---|
| Missing values | `.isnull().sum()` | Median (numeric) / Mode (categorical) per group |
| Duplicate rows | `.duplicated()` | `drop_duplicates()` |
| Inconsistent casing | Unique value inspection | `.str.title()` normalization |
| Outliers | IQR method (Q1 − 1.5×IQR, Q3 + 1.5×IQR) | Clipping to IQR bounds |
| Negative / invalid values | Range check | Set to NaN → filled |
| Wrong data types | `pd.to_numeric(errors='coerce')` | Coerce + median fill |
| Non-standard date formats | Multi-format `datetime` parser | Unified to `YYYY-MM-DD` |

---

## 📋 Cleaning Pipeline (8 Steps)

```
Step 1  → Load raw CSV and audit shape/memory
Step 2  → Data quality audit (missing, dupes, outliers, types, dates)
Step 3  → [1] Remove exact duplicates
           [2] Standardize text casing (Region, Status, Category)
           [3] Parse and unify date formats
           [4] Coerce numeric columns (handle word strings)
           [5] Remove negative/invalid values
           [6] Cap outliers using IQR method
           [7] Fill missing values (group median / mode)
           [8] Add derived columns (Net_Sales, Profit_Margin, Month, Quarter, Year)
Step 4  → Generate 9-panel visual summary dashboard (PNG)
Step 5  → Print automated business insights report to console
```

---

## 📊 Visual Report Dashboard (9 Panels)

| Panel | Content |
|---|---|
| 1 | Data Quality Summary Table — Before vs After |
| 2 | Missing Values % by Column (horizontal bar) |
| 3 | Issues Breakdown Donut Chart |
| 4 | Total Sales by Region |
| 5 | Total Sales by Category |
| 6 | Order Status Distribution |
| 7 | Monthly Net Sales Trend |
| 8 | Profit Margin Distribution (histogram) |
| 9 | Top 10 Customers by Net Sales |
| 10 | Discount vs Net Sales scatter (colored by Profit Margin) |

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/data-cleaning-automation-task4.git
cd data-cleaning-automation-task4
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib
```

### 3. Run with sample data
```bash
python data_cleaning_automation.py
```

### 4. Run with your own CSV file
```bash
python data_cleaning_automation.py --input your_file.csv --output ./results
```

**Output files generated automatically:**
- `cleaned_data_<timestamp>.csv` — fully cleaned dataset
- `cleaning_report_<timestamp>.png` — 9-panel visual dashboard

---

## 📈 Sample Results

```
Shape              : 205 rows × 10 columns   →   200 rows × 15 columns

Issues Fixed:
  Duplicates removed   : 5
  Missing vals filled  : 50
  Outliers capped      : 2
  Invalid Sales fixed  : 1
  Text casing fixed    : Yes (Region, Status, Category)
  Date formats unified : Yes (→ YYYY-MM-DD)
  Derived columns added: Net_Sales, Profit_Margin, Month, Quarter, Year

Business Insights:
  Total Net Sales     : ₹12,02,021.02
  Avg Net Sales/Order : ₹6,010.11
  Total Profit        : ₹3,45,334.24
  Avg Profit Margin   : 58.14%
  Top Region          : Central
  Top Category        : Furniture
```

---

## 📦 Input Data Format

The script expects a CSV with these columns (column names are flexible — script adapts):

| Column | Type | Example |
|---|---|---|
| Order_ID | string | ORD-1001 |
| Date | date string | 2023-01-01 |
| Customer | string | Customer_12 |
| Region | string | North |
| Category | string | Electronics |
| Sales | numeric | 7500.50 |
| Quantity | numeric | 10 |
| Discount | float (0–1) | 0.15 |
| Profit | numeric | 1200.00 |
| Status | string | Completed |

> The `sample_sales_data.csv` file is provided as ready-to-use test data with all common issues pre-injected.

---

## 🏷️ Tags

`python` `data-cleaning` `automation` `pandas` `data-preprocessing` `reporting` `etl` `data-analytics` `thiranex` `internship`

---

## 👩‍💻 Author

**Thaariha**  
Data Analytics Intern — Thiranex  
Amity University, Noida

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
