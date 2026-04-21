# Brazilian E-Commerce Data Analytics

> **Data and Visual Analytics Capstone Project**  
> Dataset: [Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle)

---

## Project Overview

This project performs end-to-end data cleaning, integrity validation, and visual analytics on the Olist Brazilian E-Commerce dataset — a real-world dataset of ~100,000 orders placed on the Olist marketplace between 2016 and 2018.

The dataset consists of **9 interrelated CSV files** covering orders, customers, products, sellers, payments, reviews, and geolocation.

---

## Repository Structure

```
brazilian-ecommerce-data-analytics/
│
├── data/
│   ├── raw/                  # Original CSV files from Kaggle (not tracked by git)
│   └── cleaned/              # Cleaned output CSVs after each notebook
│
├── notebooks/
│   ├── 01_clean_orders.ipynb
│   ├── 02_clean_customers.ipynb
│   ├── 03_clean_order_items.ipynb
│   ├── 04_clean_payments.ipynb
│   ├── 05_clean_products.ipynb
│   ├── 06_clean_sellers.ipynb
│   ├── 07_clean_reviews.ipynb
│   ├── 08_key_integrity_check.ipynb
│   └── 09_merge_final_dataset.ipynb
│
├── .gitignore
└── README.md
```

---

## Dataset Files

| File | Rows | Description |
|------|------|-------------|
| `olist_orders_dataset.csv` | 99,441 | Order lifecycle and timestamps |
| `olist_order_items_dataset.csv` | 112,650 | Items, prices, freight per order |
| `olist_customers_dataset.csv` | 99,441 | Customer location info |
| `olist_order_payments_dataset.csv` | 103,886 | Payment type, installments, value |
| `olist_order_reviews_dataset.csv` | 99,224 | Review scores and comments |
| `olist_products_dataset.csv` | 32,951 | Product catalog with dimensions |
| `olist_sellers_dataset.csv` | 3,095 | Seller location info |
| `olist_geolocation_dataset.csv` | 1,000,163 | Zip code to lat/lng mapping |
| `product_category_name_translation.csv` | 71 | Portuguese → English category names |

---

## Cleaning Workflow

### Phase 1 — Per-Table Cleaning (Notebooks 01–07)
Each table is cleaned independently:
- Fix dtypes (datetime columns, numeric fields, IDs as strings)
- Handle missing values using table-specific logic
- Standardize text fields (city names, state codes, payment types)
- Remove/flag outliers and impossible values
- Export cleaned CSV to `data/cleaned/`

### Phase 2 — Key Integrity Check (Notebook 08)
- Validate all foreign keys across tables
- Find and handle orphan records
- Cross-table consistency checks (e.g., payment totals vs item totals)
- Flag orders with impossible timestamp sequences

### Phase 3 — Final Merge (Notebook 09)
- Build order-level analytical fact table
- Build item-level analytical table
- Join product category translations
- Derive features: delivery delay, basket size, repeat customers

---

## Tech Stack

- **Python 3.x**
- **Pandas** — data manipulation and cleaning
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — visualizations
- **Jupyter Notebooks** — interactive analysis

---

## Setup

```bash
# Clone the repo
git clone https://github.com/CosmicGalactus/brazilian-ecommerce-data-analytics.git
cd brazilian-ecommerce-data-analytics

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# Download dataset from Kaggle and place CSVs in data/raw/
# https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

# Launch notebooks
jupyter notebook notebooks/
```

---

## Status

| Notebook | Status |
|----------|--------|
| 01 - Clean Orders | In Progress |
| 02 - Clean Customers | Pending |
| 03 - Clean Order Items | Pending |
| 04 - Clean Payments | Pending |
| 05 - Clean Products | Pending |
| 06 - Clean Sellers | Pending |
| 07 - Clean Reviews | Pending |
| 08 - Key Integrity Check | Pending |
| 09 - Final Merge | Pending |

---

*Capstone Project — Data and Visual Analytics*
