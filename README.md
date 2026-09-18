# 🍽️ Restaurant Rating Analysis — EDA Project

## 📌 Overview

What factors actually drive a restaurant's rating — cuisine type, price range, or location? This project analyzes the [Zomato Restaurants Dataset](https://www.kaggle.com/datasets/shrutimehta/zomato-restaurants-data) to surface patterns a restaurant owner could act on.

**Project Type:** Exploratory Data Analysis (EDA)

## 🛠️ Tools & Technologies

- Python
- Pandas
- Seaborn
- Matplotlib

## 🎯 Objective

- Identify which cuisine types achieve the highest average ratings
- Determine whether price range is associated with higher ratings
- Explore the relationship between review count (popularity) and rating
- Compare restaurant performance across cities
- Translate findings into actionable recommendations for restaurant owners

## 📁 Dataset

**Source:** [Zomato Restaurants Data — Kaggle](https://www.kaggle.com/datasets/shrutimehta/zomato-restaurants-data)

| Column | Description |
|---|---|
| Restaurant Name | Name of the restaurant |
| City | City where the restaurant is located |
| Cuisines | Cuisine type(s) served (comma-separated) |
| Price range | Price category (1 = Cheap, 4 = Expensive) |
| Aggregate rating | Average customer rating (0–5) |
| Votes | Number of reviews/votes received |

## 🧹 Data Cleaning

- Removed restaurants with `Aggregate rating = 0` (not yet rated)
- Split the `Cuisines` column (comma-separated) and exploded it into individual rows for cuisine-level analysis
- Filtered out cuisines and cities with very low restaurant counts to avoid misleading averages based on tiny samples

## 📊 Analysis & Key Findings

### 1. Average Rating by Cuisine Type
Restricting to cuisines with 30+ restaurants, **Indian (4.16)**, **Bar Food (4.15)**, and **Sandwich (4.07)** rank highest. Widely available cuisines like **Chinese (3.28, 2184 restaurants)**, **North Indian (3.30, 3017 restaurants)**, and **Fast Food (3.26, 1563 restaurants)** rank lower — likely due to market saturation and intense competition.

**Takeaway:** Niche cuisines with less competition tend to sustain higher customer satisfaction than saturated, high-volume categories.

### 2. Price Range vs Rating
Median ratings rise as price range increases from 1 to 3, then level off at 4. However, price range 3 shows the most low-rating outliers, meaning higher prices do not guarantee consistent quality.

**Takeaway:** Raising prices alone does not guarantee a better rating — mid-to-upper price segments carry a higher risk of underdelivering on customer expectations.

### 3. Review Count vs Rating
Restaurants with low ratings tend to receive few reviews, while high-rated restaurants show a wide spread — from a handful of reviews to over 10,000.

**Takeaway:** High ratings appear to be a prerequisite for popularity, but popularity alone does not guarantee a high rating.

### 4. City-Level Performance
**London (4.54)**, **Orlando (4.48)**, and **Rest of Hawaii (4.41)** top the list among cities with 20+ restaurants. On the other end, **New Delhi (3.30, 4048 restaurants)**, **Gurgaon (3.33, 890 restaurants)**, and **Noida (3.16, 696 restaurants)** — the largest, most saturated markets — show the lowest average ratings.

**Takeaway:** Restaurant density and average rating appear inversely related — larger, more competitive markets tend to show lower average customer satisfaction.

## 💡 Overall Business Conclusion

No single factor — cuisine, price, or location — fully determines a restaurant's rating on its own. Instead, **market saturation and competition level** emerge as a recurring theme across all four analyses: niche cuisines, less crowded price segments, and smaller markets consistently show higher average ratings than their saturated counterparts. For restaurant owners, this suggests that **differentiation and quality consistency matter more than simply competing on price or entering high-density markets**.

## 🖼️ Visualizations

*(Add screenshots here)*

- `images/cuisine_bar_chart.png`
- `images/price_boxplot.png`
- `images/review_scatter.png`
- `images/city_top15.png`
- `images/city_bottom15.png`

## 🚀 How to Run

```bash
git clone <your-repo-link>
cd zomato-restaurant-rating-eda
pip install pandas seaborn matplotlib
jupyter notebook notebooks/zomato_eda.ipynb
```

