# Give Me Some Credit — My Credit‑Risk Modeling Journey

Hey there! This repo is where I share my full end‑to‑end work on the Kaggle “Give Me Some Credit” challenge. The goal? Predict who’s at risk of falling 90+ days past due on their loans within two years.

I ended up with two key notebooks:

1. **`Give_Me_Some_Credit.ipynb`**  
   My first pass—basic EDA, quick models (Logistic, XGBoost, LightGBM), simple imputers, and class‑imbalance experiments.

2. **`Give_Me_Some_Credit_v2.ipynb`**  
   The “polished” pipeline you should really run:
   - Predictive imputation (MICE + targeted RandomForest)
   - Thoughtful feature engineering (capping outliers, custom delinquency score, decile bins, WoE)
   - Class‑imbalance tactics (cost‑sensitive XGBoost & SMOTEENN)
   - Recall‑focused cross‑validation, F₂‑grid search
   - Final model training on all the data + test‑set prediction output

---

## Quick Start

### If you’re in Colab
1. Upload the CSVs (`cs‑training.csv`, `cs‑test.csv`, plus sample submission & data dictionary).  
2. Upload **`Give_Me_Some_Credit_v2_clean.ipynb`**.  
3. Hit **Run All**—the first cell installs any missing packages, and everything else runs top‑to‑bottom.  
4. You’ll end up with a `GiveMeSomeCredit_test_predictions.csv` you can submit to Kaggle (or inspect for insights).

### If you prefer local
```bash
git clone <this‑repo>
cd GiveMeSomeCredit
python -m venv venv
source venv/bin/activate     # or on Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter lab                  # or jupyter notebook
