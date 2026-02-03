# 🏙️ NYC Airbnb Exploratory Data Analysis (EDA)

## 📌 Project Overview
This project performs an **end-to-end exploratory data analysis (EDA)** on New York City Airbnb listings to help a **real estate company** identify **high-return investment opportunities**, with a specific focus on **private room listings**.

The analysis combines data from multiple file formats and derives **pricing, demand, and geographic insights** to answer the question:

> **Where should the company invest to maximize returns while minimizing risk?**

---

## 🎯 Business Objective
- Understand **pricing patterns** across neighborhoods and room types  
- Evaluate **private room performance** relative to overall market prices  
- Identify **neighborhoods with strong demand and undervalued private rooms**  
- Provide **actionable recommendations** for investment strategy  

---

## 📂 Dataset Description
The analysis uses three datasets related to NYC Airbnb listings (2019):

| File Name | Format | Description |
|---------|-------|-------------|
| `airbnb_price.csv` | CSV | Listing prices and neighborhood information |
| `airbnb_room_type.xlsx` | Excel | Room type and listing descriptions |
| `airbnb_last_review.tsv` | TSV | Host information and last review dates |

### Key Columns
- `listing_id` – Unique listing identifier  
- `price` – Nightly price (USD)  
- `room_type` – Private room / Entire home / Shared room  
- `nbhood_full` – Borough and neighborhood  
- `last_review` – Date of last review  

---

## 🧰 Tools & Technologies
- **Python**
- **Pandas & NumPy** – Data manipulation
- **Matplotlib & Seaborn** – Data visualization
- **Jupyter Notebook** – Analysis workflow

---

## 🧹 Data Preparation
- Merged multiple datasets using `listing_id`
- Cleaned price data and converted it to numeric format
- Normalized room type values
- Converted review dates to datetime
- Extracted **borough-level** information from neighborhoods

---

## 📊 Key Analyses Performed

### 1️⃣ Supply Analysis
- Distribution of listings by room type
- Share of private rooms across NYC

### 2️⃣ Pricing Analysis
- Average price by room type
- Average price by borough
- Price distribution and outlier detection

### 3️⃣ Demand Signal Analysis
- Review recency used as a proxy for listing activity
- Active vs inactive listings (reviewed in last 12 months)

### 4️⃣ Neighborhood-Level ROI Analysis
- Average price per neighborhood (all room types)
- Average price of private rooms per neighborhood
- Private room price vs neighborhood average
- Private room supply share
- Active listing rate per neighborhood

---

## 📈 Key KPIs Defined

| KPI | Description |
|---|---|
| Average Price (All Rooms) | Baseline pricing power of a neighborhood |
| Average Private Room Price | Target investment segment pricing |
| Private Price Ratio | Private price vs neighborhood average |
| Private Room Share | Market acceptance of private rooms |
| Active Listing Rate | Demand proxy based on recent reviews |
| Investment Score | Composite score ranking neighborhoods |

### 📐 Investment Score Logic
```text
Investment Score =
(1 - Private Price Ratio) × 0.4 +
Private Room Share × 0.3 +
Active Listing Rate × 0.3
