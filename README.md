# 🏙️ New York City Airbnb Market Analysis  
### Scalable Data Engineering, Statistical Testing, and Price Modeling

A full-cycle data analytics project exploring pricing dynamics, availability patterns, and market segmentation in New York City's Airbnb ecosystem.

Built using automated data ingestion (Kaggle API), exploratory data analysis, statistical hypothesis testing, regression modeling, and relational database integration.

---

## 🔎 Executive Summary

This project analyzes NYC Airbnb listings to understand:

- What drives price differences across boroughs and room types?
- Does availability significantly influence pricing?
- How do stay duration patterns reflect market demand?
- Can pricing be statistically explained using structured features?

The analysis integrates data cleaning, visualization, ANOVA testing, linear regression modeling, and SQLite database storage to simulate a production-style analytics workflow.

---

## 📦 Dataset

Source: Kaggle — NYC Airbnb Open Data  
Dataset Identifier: `dgomonov/new-york-city-airbnb-open-data`

Key Features:
- Price
- Room Type
- Neighbourhood Group (Borough)
- Availability (365 days)
- Minimum Nights
- Reviews per Month
- Number of Reviews
- Latitude / Longitude

Total Records: ~49,000+ listings

---

## ⚙️ System Architecture

### 1️⃣ Data Ingestion
- Kaggle API authentication
- Automated dataset download
- Programmatic loading into Pandas DataFrame

### 2️⃣ Data Cleaning
- Missing value detection
- Removal of non-analytical columns (`id`, `host_name`, `last_review`)
- Imputation:
  - `reviews_per_month` → filled with 0
- Dataset normalization

### 3️⃣ Exploratory Data Analysis
- Descriptive statistics (mean, median, IQR, percentiles)
- Outlier detection using IQR method
- Distribution visualization
- Borough-level segmentation
- Room-type segmentation

### 4️⃣ Statistical Testing

#### ANOVA Test: Price vs Room Type
- Null Hypothesis (H0): No price difference across room types
- Result: p-value < 0.05
- Conclusion: Room type significantly impacts pricing

#### Linear Regression: Price vs Availability
- R² ≈ 0.014
- Availability statistically significant but weak predictor
- Indicates other variables dominate price formation

---

## 📊 Key Insights

### 🏢 Room Type Segmentation
- Entire Home/Apt: Highest mean price and highest variance
- Private Rooms: Mid-range pricing
- Shared Rooms: Lowest and most stable pricing

Strong statistical evidence confirms segmentation-based pricing structure.

---

### 🗺️ Borough-Level Trends
- Manhattan dominates across all room types
- Brooklyn balances price and availability
- Queens and Bronx offer lower-cost alternatives
- Staten Island serves niche market

Location remains the strongest pricing determinant.

---

### 📈 Availability Patterns
- Manhattan & Brooklyn: Low availability → High demand
- Queens & Staten Island: Higher availability → Lower demand pressure

Market liquidity varies significantly across boroughs.

---

### 🛏️ Minimum Stay Patterns
- 1–2 night minimums dominate (≈60%+ of listings)
- Airbnb heavily optimized for short-term travel

---

## 🤖 Predictive Modeling

### Linear Regression Model

Features Used:
- Latitude
- Longitude
- Minimum Nights
- Number of Reviews
- Reviews per Month
- Availability_365

Evaluation:
- Mean Squared Error calculated
- R² score reported
- Feature coefficients interpreted

Conclusion:
Basic regression explains limited variance → pricing likely influenced by nonlinear or unobserved variables (e.g., amenities, property quality).

---

## 🗃️ Database Integration

To simulate production data flow:

- Data exported to SQLite database
- Table: `ab_nyc_listings`
- Re-ingested using SQL query
- Validated schema integrity

Demonstrates pipeline continuity between analytics and storage layers.

---

## 📈 Visualizations Included

- Price distribution histograms
- Room-type price bar charts
- Borough-room heatmap
- Boxplots of availability
- Scatterplot: Price vs Location
- Stay-duration pie chart
- ANOVA validation results

---

## 🧠 Business Implications

For Hosts:
- Optimize pricing based on borough demand elasticity
- Entire homes in Manhattan → premium strategy
- Private rooms → occupancy-maximization strategy

For Travelers:
- Queens and Bronx → value-driven alternatives
- Private rooms → best price-privacy tradeoff

For Platform Strategy:
- Strong borough-based market segmentation
- Availability weakly predicts pricing → demand-side metrics more valuable
- Pricing optimization models require richer features

---

## 🚀 Technical Stack

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Scikit-learn
- Kaggle API
- SQLite

---

## 👥 Team

Group 5  
- Dhruv Sharma  
- Krishi Shah  
- Devansh Bhavsar  
- Nisargvan Goswami  
- Devarshi Lala  

---

## 🎯 Takeaways

This project demonstrates:

- Automated data ingestion via API
- Data cleaning at scale
- Statistical hypothesis testing
- Feature-based regression modeling
- Data visualization storytelling
- Relational database integration
- End-to-end analytics pipeline thinking

---

## 📌 Future Enhancements

- Random Forest / Gradient Boosting
- Log-price transformation
- Outlier trimming
- Feature engineering (price per night percentile ranking)
- Geospatial clustering
- Elasticity modeling
- Cross-validation performance tuning
