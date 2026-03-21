# 🏀 2026 March Madness: Tournament Forecasting

## 📌 Project Overview
This project leverages a machine learning approach to forecast win probabilities for the 2026 NCAA Division I Men's Basketball Tournament. By calculating the relative strength between opponents, this model identifies high-value upset opportunities and validates top-seed dominance.

---

## 🧠 Methodology & Model Design
The engine is built on a **Logistic Regression (Logit) Framework**. Logistic regression was chosen because it specifically predicts the probability of a binary outcome (Win/Loss), mapping the output to a 0 to 1 range.

### 📊 Feature Engineering & Differential Logic
The model utilizes a **Differential Feature Set**. Instead of looking at raw season totals, the model calculates the delta between Team A and Team B to reflect the relative nature of a tournament game.

| Feature | Logic | Strategic Reasoning |
| :--- | :--- | :--- |
| **ScoreDiff** | PPG Diff A - PPG Diff B | Measures absolute scoring dominance. |
| **FGM_Diff** | FGM A - FGM B | Proxy for offensive efficiency. |
| **SeedDiff** | Seed A - Seed B | Proxy for Strength of Schedule. |

---

## 🚀 The 'Power 5' Seed-Weight Correction
To account for the **Mid-Major Paradox** (inflated stats against weaker schedules), I implemented a **Weighted Seed Influence (w=3.0)**. 

By tripling the coefficient of the SeedDiff feature, the model forces a "respect" for the rigor of Power 5 conference play. This adjustment successfully corrected the model's initial bias toward mid-major teams, providing more realistic forecasts for elite programs like **Purdue** and **Duke**.

---

## 📉 Performance Validation
As of the conclusion of the 2026 Round of 64:

* **Accuracy Rate:** **78.13%** (25 Correct / 32 Games).
* **Confidence Interval:** The model maintained a 90%+ confidence level on all #1 and #2 seeds.
* **Analysis:** The misses (e.g., VCU and High Point) were driven by high-variance upsets that define the tournament's "chaos factor."

---

## 🛠️ Technologies Used
* **Python 3.10**
* **Pandas:** Data manipulation and feature delta calculations.
* **Scikit-Learn:** Logistic Regression implementation.