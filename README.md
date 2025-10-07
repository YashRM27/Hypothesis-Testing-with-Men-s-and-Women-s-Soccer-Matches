# Hypothesis-Testing-with-Men-s-and-Women-s-Soccer-Matches

## 📘 Overview

This repository investigates whether **more goals are scored in women's FIFA World Cup matches than in men's**. Using official match data since **2002-01-01**, we perform statistical testing to evaluate this hypothesis at a **10% significance level**.

## 🎯 Objective

Determine if the **mean number of goals per match** differs between men's and women's FIFA World Cups.

* **Null Hypothesis (H₀):** Mean goals in women's matches = Mean goals in men's matches
* **Alternative Hypothesis (H₁):** Mean goals in women's matches > Mean goals in men's matches

Significance level (α): **0.10**

---

## 🧩 Data

Two datasets are used:

* `women_results.csv` — official women's international match data
* `men_results.csv` — official men's international match data

Both datasets contain:

* `date` — date of the match
* `tournament` — tournament name
* `home_score`, `away_score` — team goals per match

Only **FIFA World Cup** matches since **2002-01-01** are analyzed.

---

## 🔍 Methodology

1. **Data Preparation**

   * Load data from CSV files.
   * Filter for matches: `tournament == 'FIFA World Cup'` and `date >= '2002-01-01'`.
   * Calculate `total_goals = home_score + away_score`.

2. **Exploratory Data Analysis (EDA)**

   * Compare distributions of total goals between men's and women's matches.
   * Check normality using **Shapiro–Wilk test** and visual plots.

3. **Hypothesis Testing**

   * Perform a **Welch’s two-sample t-test** (one-sided, `alternative='greater'`).
   * If normality is violated, use the **Mann–Whitney U test**.

4. **Decision Rule**

   * If *p-value < 0.10*, **reject H₀** → more goals are scored in women's matches.
   * Otherwise, **fail to reject H₀**.

5. **Result Output**
   The test result is stored in a dictionary:

   ```python
   result_dict = {"p_val": p_val, "result": result}
   ```

---

## 🧮 Interpretation

* **Reject H₀:** Strong evidence that women’s matches have higher mean goals per game.
* **Fail to Reject H₀:** No significant difference in mean goals per game.

---

## 🧠 Dependencies

* Python 3.9+
* pandas
* scipy
* pingouin
* matplotlib / seaborn (for visualization)

Install dependencies:

```bash
pip install pandas scipy pingouin matplotlib seaborn
```

---

