movies data set EDA
Performed basic to advanced EDA operations on dataset: Full TMDB Movies Dataset 2024 (1M Movies) 
link to dataset: https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies/data

Expected EDA :
## 🔹 1. First Look at the Data

* `df.shape` → how many rows & columns.
* `df.info()` → datatypes, missing values.
* `df.describe()` → summary of numeric columns.
* `df.isnull().sum()` → check missing data.
* `df.duplicated().sum()` → check duplicates.

---

## 🔹 2. Data Cleaning

* Convert `release_date` → `datetime`.
* Handle missing values (`budget`, `revenue` often missing).
* Convert `adult` → Boolean (True/False).
* Ensure numeric columns (`vote_average`, `budget`, `revenue`, `runtime`, `popularity`) are proper numbers.

---

## 🔹 3. Univariate Analysis (Single-column insights)

👉 **Questions you can ask & plots**:

* **Vote average** → distribution of ratings (`sns.histplot(df['vote_average'])`).
* **Runtime** → typical movie lengths (histogram, boxplot).
* **Budget & Revenue** → log-scale histograms (movies vary a lot in size).
* **Release year** → movies per year (`df['release_date'].dt.year.value_counts()`).
* **Languages** → most common original languages.
* **Genres** → explode into multiple rows, then count most frequent genres.

---

## 🔹 4. Bivariate Analysis (Relationships between two columns)

👉 **Examples**:

* **Budget vs Revenue** → scatterplot (`sns.scatterplot(x='budget', y='revenue')`).
* **Runtime vs Vote Average** → is longer better?
* **Vote Count vs Vote Average** → do more votes stabilize ratings?
* **Genre vs Revenue** → barplot of average revenue per genre.
* **Language vs Revenue** → English vs Non-English.

---

## 🔹 5. Time Trends

* Movies produced per year (`release_date`).
* Average budget/revenue trend over time.
* Popularity trends for genres.

---

## 🔹 6. Textual Columns (Overview, Tagline, Keywords)

* Word clouds (e.g., most common keywords).
* Length of overview text vs popularity.
* Frequent words in taglines.

---

## 🔹 7. Correlation & Heatmaps

* Use only numeric columns: `budget`, `revenue`, `runtime`, `vote_average`, `vote_count`, `popularity`.
* `sns.heatmap(df.corr(), annot=True, cmap="coolwarm")`.
* See which variables drive revenue or votes.

---

## 🔹 8. Advanced Ideas

* **Profitability metric** → `profit = revenue - budget`.
* **ROI** → `(revenue - budget) / budget`.
* Top profitable movies per genre/year.
* Compare streaming-era (2010+) vs older movies.
* Does runtime affect revenue/profit?
* Do sequels (detect in titles like “2”, “Part II”) perform better?

---

✅ **Flow to follow in your notebook**:

1. Data Overview
2. Data Cleaning
3. Univariate Analysis
4. Bivariate Analysis
5. Time Trends
6. Text Analysis
7. Correlations
8. Insights & Visual Storytelling

