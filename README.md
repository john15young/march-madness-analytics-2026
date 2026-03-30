# 🏀 2026 March Madness Forecaster: The "Hardened Logic" Engine

### **Overview**
The **2026 Hardened Logic Engine** is a high-precision forecasting model built to navigate the high-variance environment of the NCAA Tournament. Rather than relying on simple win/loss records, this model analyzes **mechanical efficiency**—identifying the specific statistical "cliffs" where lower seeds typically fail and the elite defensive traits required for deep championship runs.

---

### 📊 2026 Tournament Performance Dashboard
The model's accuracy has remained remarkably stable as the field narrows and the competition level rises.

* **Round of 64 Accuracy:** **78.12%** (25/32 Games Correct)
* **Elite 8 Accuracy:** **100%** (4/4 Games Correct)
* **Current Status:** Optimized for the Final Four
* **Strategy Note:** Successfully predicted Arizona (1) over Purdue (2) by using a manual override to prioritize **Transition Speed** and **Recent Tournament Dominance** over interior efficiency.

---

### 🧠 The Four Pillars of the Model
The model's intelligence is derived from four core metric categories extracted and cleaned from the `MRegularSeasonDetailedResults` dataset.

#### **1. Scoring & Shooting Efficiency**
The model identifies how much "value" a team gets out of every single possession.
* **eFG% (Effective Field Goal Percentage):** Calculated as `(FGM + 0.5 * FGM3) / FGA`. This recognizes that 3-point shots are 50% more valuable than 2-pointers, rewarding teams with elite spacing.
* **PPS (Points Per Shot):** Calculated as `Score / FGA`. This identifies high-efficiency offenses that prioritize high-percentage shots over volume.

#### **2. Tactical Playmaking & Ball Security**
* **Ast_Diff (Assist Differential):** The gap between a team's assists and their opponents'. High assist differentials indicate a "Motion Offense" that is harder to scout and defend in a tournament setting.
* **FGM_Diff (Field Goals Made Differential):** Measures a team's ability to create more high-quality scoring opportunities than their opponent per game.

#### **3. The "Power Blend" (50/50 Logic)**
To ensure the model isn't fooled by "stat-stuffers" from weaker conferences, the final probability is a balanced hybrid:
* **50% Statistical Probability:** Derived from a **Logistic Regression** model trained on 14 years of historical tournament box scores.
* **50% Seed Probability:** A "Respect Factor" where each seed gap provides a **7% boost** to the higher seed. This ensures that a 1-seed's season-long dominance is mathematically respected.

#### **4. Tournament-Specific Logic Overrides**
The engine applies "Hardened" filters to account for the unique environment of the Big Dance:
* **🛡️ The 65 PPG Defensive Wall:** A **4% bonus** is applied to teams that allow fewer than 65 Points Per Game. The model recognizes that elite defense is the highest-probability indicator of tournament advancement.
* **🏅 Blue Blood Pedigree:** A **3% bonus** for institutional winners (e.g., UConn, Duke, Kansas). This accounts for coaching experience and "Tournament DNA" that raw regular-season box scores miss.
* **💎 Elite Seed Protection:** An **8% safety buffer** is applied when a top-2 seed faces a double-digit seed, protecting the bracket from high-variance early-round upsets.

---

### 🚀 Technical Implementation
1.  **Data Prep:** Cleans `MNCAATourneySeeds` and aggregates winning/losing stats to calculate true **Opponent Scoring (OppScore)**.
2.  **Model Training:** Uses `StandardScaler` to normalize features before training the Logistic Regression model on raw arrays for maximum precision.
3.  **Execution:** The `predict_game_v5` function executes the blend and applies overrides to produce the final win probability.