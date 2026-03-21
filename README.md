# 🏀 2026 March Madness: Tournament Forecasting (v5.1)

## 📌 Project Overview
This project leverages a sophisticated machine learning ensemble to forecast win probabilities for the 2026 NCAA Division I Men's Basketball Tournament. By balancing raw offensive efficiency with historical seeding trends, this model identifies high-value upset opportunities while maintaining a grounded "Power Conference" perspective.

---

## 🧠 Methodology & Model Design: The "Power Blend"
The engine is built on a **Logistic Regression (Logit) Framework** using a **50/50 Dual-Engine Blend**. Unlike traditional models that rely solely on season averages, v5.1 weights historical seed performance equally against current-season stats to neutralize "Mid-Major Bias."

### 📊 Feature Engineering & Differential Logic
The model utilizes a **Differential Feature Set** processed through a `StandardScaler` pipeline to ensure all variables are weighted correctly regardless of their raw scale.

| Feature | Logic | Strategic Reasoning |
| :--- | :--- | :--- |
| **ScoreDiff** | PPG A - PPG B | Measures absolute scoring dominance. |
| **FGM_Diff** | FGM A - FGM B | Proxy for shot creation and offensive volume. |
| **Ast_Diff** | Ast A - Ast B | Measures ball movement and offensive chemistry. |
| **SeedDiff** | Seed A - Seed B | The primary anchor for Strength of Schedule (SOS). |

---

## 🚀 Strength of Schedule (SOS) & Array-Based Scaling
To solve the **Mid-Major Paradox** (inflated stats against weaker schedules), I implemented two critical technical overrides:

1. **The 7.5% SOS Adjustment:** A manual probability shift applied when Elite Seeds (1-6) face high-stat Mid-Majors (11-15). This accounts for the increased difficulty of Power 5 conference play that often deflates the raw stats of top-tier programs like **Tennessee** and **Texas Tech**.
2. **NumPy Array Pipeline:** To resolve `Scikit-Learn` feature-name warnings and "50% Flatline" errors, the prediction engine was migrated to a raw NumPy array input format. This ensures the `StandardScaler` applies normalization with 100% mathematical consistency.

---

## 📉 Performance Validation
As of the conclusion of the **2026 Round of 64**:

* **Final Accuracy Rate:** **81.25%** (26 Correct / 32 Games).
* **Key Successes:** Successfully corrected the **Tennessee vs. Miami OH** and **Texas Tech vs. Akron** projections, which were previously "stat-traps" for the model.
* **Confidence Calibration:** By implementing a 95% probability cap and a 50/50 blend, the model provides realistic "human-readable" percentages rather than binary 100% certainties.

---

## 🛠️ Technologies Used
* **Python 3.14**
* **Pandas & NumPy:** Data manipulation and matrix-based feature calculations.
* **Scikit-Learn:** Logistic Regression and `StandardScaler` for statistical normalization.