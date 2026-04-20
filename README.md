# 🏀 2026 March Madness Forecaster: Strategic Win-Probability Engine

### **Overview**
The **2026 Strategic Win-Probability Engine** is a high-precision forecasting model built to navigate the high-variance environment of the NCAA Tournament. Rather than relying on simple win/loss records, this model analyzes **mechanical efficiency**—identifying the statistical thresholds where lower seeds typically fail and the elite defensive traits required for deep championship runs.

### 📊 **2026 Tournament Performance Dashboard**
The model's accuracy has remained remarkably stable as the field narrows and the competition level rises.
* **Round of 64 Accuracy:** 78.12% (25/32 Games Correct)
* **Elite 8 Accuracy:** 100% (4/4 Games Correct)
* **Current Status:** Optimized for the Final Four
* **Key Insight:** Successfully predicted Arizona (1) over Purdue (2) by using a manual override to prioritize **Transition Speed** and **Recent Tournament Dominance** over interior efficiency.

---

### 🧠 **The Four Pillars of the Model**
The model's intelligence is derived from four core metric categories extracted and cleaned from historical tournament datasets.

#### **1. Scoring & Shooting Efficiency**
The model identifies how much "value" a team gets out of every possession:
* **eFG% (Effective Field Goal Percentage):** Rewards teams with elite spacing by recognizing that 3-point shots are 50% more valuable than 2-pointers.
* **PPS (Points Per Shot):** Identifies high-efficiency offenses that prioritize high-percentage looks over volume.

#### **2. Tactical Playmaking & Ball Security**
* **Ast_Diff (Assist Differential):** High assist differentials indicate "Motion Offenses" that are historically harder to scout and defend in tournament settings.
* **FGM_Diff (Field Goals Made Differential):** Measures a team's ability to create more high-quality scoring opportunities than their opponent.

#### **3. The Hybrid Probability Blend**
To ensure the model isn't skewed by "stat-stuffers" from weaker conferences, the final output is a balanced hybrid:
* **50% Statistical Probability:** Derived from a **Logistic Regression** model trained on 23 years of historical tournament box scores (2003–2025).
* **50% Seed Probability:** A "Respect Factor" where each seed gap provides a **7% boost** to the higher seed, respecting season-long dominance.

#### **4. Tournament-Specific Overrides**
The engine applies specific filters to account for the unique environment of the Big Dance:
* 🛡️ **The 65 PPG Defensive Wall:** A **4% bonus** for teams allowing fewer than 65 PPG, recognizing elite defense as a primary indicator of advancement.
* 🏅 **Institutional Pedigree:** A **3% bonus** for programs with deep tournament history (e.g., UConn, Duke, Kansas) to account for coaching experience.
* 💎 **Elite Seed Protection:** An **8% safety buffer** when a top-2 seed faces a double-digit seed to protect against high-variance early-round upsets.

---

### 🚀 **Technical Implementation**
* **Data Prep:** Cleans historical seed data and aggregates winning/losing stats to calculate true **Opponent Scoring (OppScore)**.
* **Model Training:** Uses `StandardScaler` to normalize features before training the **Logistic Regression** model for maximum precision.
* **Execution:** The `predict_game_v5` function executes the probability blend and applies overrides to produce the final win percentage.