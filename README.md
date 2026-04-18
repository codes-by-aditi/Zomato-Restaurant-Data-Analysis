# 🍽️ Zomato Bangalore — Exploratory Data Analysis

<div align="center">

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-2A9D8F?style=for-the-badge)

**A professional end-to-end EDA project on 50,000+ restaurant records from Bangalore's food-tech ecosystem**

[📓 View Notebook](#-project-structure) • [📊 Key Insights](#-key-insights) • [🚀 Quick Start](#-quick-start) • [📁 Dataset](#-dataset)

</div>

---

## 📌 Project Overview

This project performs a **comprehensive Exploratory Data Analysis (EDA)** on the [Zomato Bangalore Restaurants dataset](https://www.kaggle.com/datasets/himanshupoddar/zomato-bangalore-restaurants) from Kaggle. The goal is to uncover actionable insights about dining patterns, customer preferences, and business trends across one of India's most vibrant food cities.

> **Skills demonstrated:** Data Cleaning · Feature Engineering · Statistical Analysis · Data Visualization · Storytelling with Data

---

## 🎯 Objectives

- Understand the **structure, quality, and quirks** of a real-world messy dataset
- Apply **systematic data cleaning** techniques (type fixing, noise removal, imputation)
- Extract **5 meaningful business insights** through grouping and aggregation
- Communicate findings through **6 professional-grade visualizations**

---

## 📁 Dataset

| Property | Detail |
|----------|--------|
| **Source** | [Kaggle — Zomato Bangalore Restaurants](https://www.kaggle.com/datasets/himanshupoddar/zomato-bangalore-restaurants) |
| **File** | `zomato.csv` |
| **Rows** | ~51,717 restaurant records |
| **Columns** | 17 features |
| **Coverage** | Multiple localities across Bangalore, India |

**Key Features Used:**

| Column | Description |
|--------|-------------|
| `name` | Restaurant name |
| `location` | Locality in Bangalore |
| `rest_type` | Type of restaurant (Casual Dining, Quick Bites, etc.) |
| `cuisines` | Comma-separated cuisine types offered |
| `rate` | Customer rating (out of 5) |
| `votes` | Total number of ratings received |
| `approx_cost(for two people)` | Approximate cost for two diners (₹) |
| `online_order` | Whether online ordering is available |
| `book_table` | Whether table booking is available |

---

## 🧰 Tech Stack

```
Python 3.11
├── pandas       — Data manipulation & aggregation
├── numpy        — Numerical operations
├── matplotlib   — Base plotting engine
└── seaborn      — Statistical visualizations
```

---

## 📂 Project Structure

```
zomato-eda/
│
├── 📓 zomato_eda.ipynb        ← Main Jupyter Notebook
├── 📄 README.md               ← You are here
├── 📊 zomato.csv              ← Dataset (download from Kaggle)
│
└── plots/                     ← Auto-generated visualization exports
    ├── plot1_restaurant_types.png
    ├── plot2_online_order_countplot.png
    ├── plot3_rating_by_cost.png
    ├── plot4_heatmap.png
    ├── plot5_top_cuisines.png
    └── plot6_location_rating_trend.png
```

---

## 🧹 Data Cleaning Steps

| Step | Issue | Fix Applied |
|------|-------|-------------|
| Column Rename | Verbose names like `approx_cost(for two people)` | Renamed to `cost_for_two` |
| Duplicate Removal | Exact duplicate rows | `drop_duplicates()` |
| `rate` column | Stored as `"4.1/5"` string | Stripped `"/5"`, cast to `float` |
| `cost_for_two` column | Commas in numbers (`"1,200"`) | Removed commas, cast to `int` |
| Missing `rate` | ~7% missing — primary metric | Dropped rows |
| Missing `cost_for_two` | ~1% missing | Imputed with **median** |
| Missing `cuisines` | Small fraction | Filled with `'Unknown'` |
| Boolean columns | `"Yes"` / `"No"` strings | Mapped to `True` / `False` |

---

## 💡 Key Insights

### 1 · Online Ordering Lifts Ratings
Restaurants that accept online orders score measurably higher on average. This likely reflects a more customer-forward operational mindset — faster feedback loops, greater visibility, and broader reach.

### 2 · Location Has a Real Impact
Localities like **Lavelle Road**, **Residency Road**, and **Koramangala** consistently top the rating charts. These upscale areas attract both higher spending and higher expectations — creating a virtuous quality cycle.

### 3 · Price Correlates With Rating — But Not Linearly
Budget restaurants (`< ₹300`) score lowest, but **mid-range (₹600–₹1000)** and **premium (₹1k–₹2k)** restaurants show the best rating-per-rupee value. Luxury dining (`₹2k+`) scores high but with wider variance — expectations are harder to meet consistently.

### 4 · North Indian & Chinese Rule Bangalore
Despite Bangalore's South Indian identity, **North Indian** and **Chinese** are the most widely offered cuisines — reflecting pan-Indian urban taste preferences. South Indian cuisine ranks third.

### 5 · Quick Bites Lead in Volume; Fine Dining Leads in Ratings
**Quick Service Restaurants (QSR)** and **Casual Dining** dominate by count, but **Fine Dining** and **Bar & Pub** formats consistently earn the highest average ratings. Niche formats serve fewer customers but satisfy them more deeply.

---

## 📊 Visualizations

| # | Chart Type | What It Shows |
|---|-----------|----------------|
| 1 | Horizontal Bar | Top 10 most common restaurant types by count |
| 2 | Count Plot | Online order availability split across top 5 restaurant types |
| 3 | Box Plot | Rating distribution across 5 price segments |
| 4 | Heatmap | Correlation matrix between numerical and boolean features |
| 5 | Horizontal Bar | Top 10 most offered cuisines |
| 6 | Line + Fill | Average rating trend across top 20 localities |

---

## 🚀 Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/your-username/zomato-eda.git
cd zomato-eda
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Download the dataset
Download `zomato.csv` from [Kaggle](https://www.kaggle.com/datasets/himanshupoddar/zomato-bangalore-restaurants) and place it in the project root.

### 4. Launch the notebook
```bash
jupyter notebook zomato_eda.ipynb
```

> ✅ Run all cells top-to-bottom. Plots are auto-saved as `.png` files.

---

## 📈 What I Learned

- How to handle **real-world messy data** — string-encoded numbers, mixed types, inconsistent formatting
- The importance of **cleaning strategy documentation** — explaining *why* each decision was made
- How to ask **business-relevant questions** from raw data and translate them to grouped aggregations
- Building a **consistent visual language** across multiple chart types using shared palettes and themes

---

## 🔭 Future Work

- [ ] **NLP Sentiment Analysis** on customer reviews
- [ ] **Geospatial visualization** — restaurant density map of Bangalore
- [ ] **Predictive Modelling** — Predict rating from restaurant features (Random Forest / XGBoost)
- [ ] **Cuisine Clustering** — Group locations by dominant cuisine profile

---

## 📜 License

This project is open-source under the [MIT License](LICENSE).

---

<div align="center">

**Made with 🔍 curiosity and 📊 pandas**

*If you found this useful, consider giving it a ⭐*

</div>
