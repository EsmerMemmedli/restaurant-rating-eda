# 🍽️ Restaurant Rating Analysis — EDA Project

## 📌 Overview

This project performs Exploratory Data Analysis (EDA) on Zomato restaurant data using Python libraries like Pandas, Matplotlib, and Seaborn. The goal of this project is to analyze what actually drives a restaurant's rating — cuisine type, price range, or location — and surface patterns a restaurant owner could act on.

## 🛠️ Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## 📌 Project Objectives

- Identify which cuisine types achieve the highest average ratings 
- Determine whether price range is associated with higher ratings 
- Explore the relationship between review count (popularity) and rating 
- Compare restaurant performance across cities 
- Visualize insights using bar charts, box plots, scatter plots, and a correlation heatmap

## 📁 Dataset

**Source:** [Zomato Restaurants Data — Kaggle](https://www.kaggle.com/datasets/shrutimehta/zomato-restaurants-data)

## 📊 Analysis Performed

✅ Data Cleaning

Removed restaurants with a rating of 0 (not yet rated) 
Split and exploded the Cuisines column so each cuisine could be analyzed individually 
Filtered out cuisines and cities with very low restaurant counts to avoid misleading averages

✅ Exploratory Data Analysis

Major business questions answered in this project:

Which cuisine types are rated highest by customers? 
Do more expensive restaurants actually get higher ratings?
Does popularity (a high number of reviews) mean a higher rating? 
Which cities represent the healthiest markets for a restaurant business? 
Which numeric variable has the strongest relationship with rating — votes, price range, or cost?

---

## 📊 Analysis 1 — Average Rating by Cuisine Type

**Business Question:** Which cuisine types are rated highest by customers?

**Work Done:** The `Cuisines` column was split and exploded so each restaurant's cuisines could be evaluated individually. Average rating was calculated for cuisines with at least 30 restaurants, and the top 15 were plotted as a bar chart.

**Result:** **Indian (4.16)**, **Bar Food (4.15)**, and **Sandwich (4.07)** rank highest. Widely available cuisines — **Chinese (3.28, 2184 restaurants)**, **North Indian (3.30, 3017 restaurants)**, and **Fast Food (3.26, 1563 restaurants)** — rank lower. Niche, less-competitive cuisines show more consistent customer satisfaction than saturated, high-volume categories.

**Visual:**
<img src="images/cuisine_bar_chart.png" width="600">

---

## 📊 Analysis 2 — Price Range vs Rating Comparison

**Business Question:** Do more expensive restaurants actually get higher ratings?

**Work Done:** Using `df_clean`, the distribution of Aggregate rating across Price range categories (1–4) was visualized with a box plot.

**Result:** Median rating rises from Price range 1 to 3, then levels off at 4. However, Price range 3 shows the most low-rating outliers — meaning a higher price does not guarantee consistent quality. Raising prices alone does not guarantee a better rating.

**Visual:**
<img src="images/price_boxplot.png" width="600">

---

## 📊 Analysis 3 — Review Count vs Rating

**Business Question:** Does popularity (a high number of reviews) mean a higher rating?

**Work Done:** The relationship between Votes (review count) and Aggregate rating was plotted as a scatter plot, with the x-axis on a log scale due to the wide range of Votes values.

**Result:** Low-rated restaurants generally receive few reviews, while high-rated restaurants are spread across a wide range — from just a handful of reviews to over 10,000. A high rating appears to be a prerequisite for popularity, but popularity itself doesn't guarantee a high rating.

**Visual:**
<img src="images/review_scatter.png" width="600">

---

## 📊 Analysis 4 — City-Level Performance Breakdown

**Business Question:** Which cities represent the healthiest markets for a restaurant business?

**Work Done:** Restaurants were grouped by `City`, and average rating was calculated for cities with at least 20 restaurants. The top 15 and bottom 15 cities were each plotted as bar charts.

**Result:** **London (4.54)**, **Orlando (4.48)**, and **Rest of Hawaii (4.41)** top the list. The largest, most saturated markets — **New Delhi (3.30, 4048 restaurants)**, **Gurgaon (3.33, 890 restaurants)**, and **Noida (3.16, 696 restaurants)** — show the lowest average ratings. Restaurant density and average rating appear inversely related.

**Visual:**

<img src="images/city_top15.png" width="600">
<img src="images/city_bottom15.png" width="600">

---

## 📊 Analysis 5 — Correlation Heatmap

**Business Question:** Which numeric variable has the strongest relationship with rating — Votes, Price range, or Cost?

**Work Done:** A Pearson correlation matrix was calculated across `Aggregate rating`, `Votes`, `Price range`, and `Average Cost for two`, and visualized as a heatmap.

**Result:** Both Votes (0.41) and Price range (0.40) show a similar, moderate positive correlation with Aggregate rating — meaning neither factor dominates the other in explaining rating differences. Votes and Price range themselves show a weaker correlation (0.27) with each other, suggesting they capture somewhat independent aspects of a restaurant's profile. Overall, no single numeric variable strongly determines rating on its own — this reinforces the earlier finding that rating is shaped by a combination of factors rather than any one dominant driver.

**Visual:**
<img src="images/correlation_heatmap.png" width="600">

---

## 🔍 Key Insights

- Indian, Bar Food, and Sandwich cuisines have the highest average ratings, while widely available cuisines like Chinese, North Indian, and Fast Food rank lower due to market saturation.
- Median rating rises with price range up to range 3, but higher prices don't guarantee consistent quality — range 3 shows the most low-rating outliers. 
- Low-rated restaurants generally receive few reviews, while high-rated restaurants span a wide range of review counts — popularity doesn't guarantee a high rating. 
- London, Orlando, and Rest of Hawaii top the list of cities by average rating, while the largest, most saturated markets (New Delhi, Gurgaon, Noida) show the lowest average ratings. 
- Votes (0.41) and Price range (0.40) show a similar, moderate correlation with rating — no single numeric factor dominates.

## 💡 Overall Business Conclusion

No single factor — cuisine, price, or location — fully determines a restaurant's rating on its own. Instead, a recurring theme across all analyses is **market saturation and competition level**: niche cuisines, less crowded price segments, and smaller markets consistently show higher average ratings than their saturated
