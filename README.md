# 🏀 2026 March Madness Predictive Modeling
### *A Machine Learning Approach to Tournament Forecasting*

## 📌 Project Overview
This project leverages historical NCAA Division I basketball data to forecast win probabilities for the 2026 March Madness tournament.

## 🧠 Model Design & Logic
The model utilizes a **Differential Feature Set** including:
* **ScoreDiff:** Average points per game margin.
* **FGM_Diff:** Field Goals Made margin.
* **SeedDiff:** The difference in tournament seeds (Strength of Schedule proxy).

## 🚀 The 'Power 5' Correction
I implemented a **Weighted Seed Influence** to ensure the model respects the difficulty of Power 5 conference schedules over high-volume mid-major stats. This corrected the 'Mid-Major Paradox' and provided more realistic win probabilities for teams like Wisconsin and Nebraska.
