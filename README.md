# Predicting K-12 Academic Success Using Generalized Linear Models

---

## 📌 Overview
A comprehensive three-phase statistical analysis investigating how school 
choice and family engagement impact K-12 student academic success. Using 
data from the U.S. Department of Education's Parent and Family Involvement 
(PFI) Survey, this project develops and evaluates multiple generalized 
linear models to quantify these relationships and provide evidence-based 
recommendations for GVSU's K-12 Connect program.

---

## ❓ Research Question
**Does school choice and family engagement significantly predict K-12 
student academic success, and how do these factors interact?**

---

## 📂 Dataset
| Dataset | Description |
|---|---|
| PFI Survey 2019 | Primary dataset — 15,500 students, 71 variables |
| PFI Survey 2016 | Validation dataset for temporal sensitivity analysis |
| Source | U.S. Department of Education, National Center for Education Statistics |

---

## 🔍 Three-Phase Analysis

### Phase 1 — Data Understanding & Preparation
- Systematic variable identification across 4 categories: outcomes, school choice, family engagement, demographics
- Feature engineering: `success_binary`, `engagement_count`, `homework_intensity`, `school_involvement`, `communication_index`
- Missing data handling — variables with >30% missing removed
- Clean dataset saved for Phase 2

### Phase 2 — Exploratory Data Analysis
- Distribution analysis of outcome variables (binary and 4-category grades)
- Bivariate relationships between school choice, engagement, and success
- Correlation analysis and interaction effect exploration
- Univariate screening to rank predictors by statistical significance
- Variable selection strategy for modeling phase

### Phase 3 — GLM Development & Evaluation
- **Logistic Regression** — Core, Interaction, and LASSO models for binary outcome
- **Linear Discriminant Analysis (LDA)** — Classification with dimensionality reduction
- **Poisson Regression** — Modeling engagement count outcome
- **Multinomial Regression** — 4-category grade outcome modeling
- Model comparison via ROC-AUC, accuracy, sensitivity, and specificity
- LASSO regularization for automatic variable selection

---

## 📈 Key Engineered Features
| Feature | Description | Type |
|---|---|---|
| `success_binary` | 1 if grades A/B, 0 if C/D | Outcome |
| `engagement_count` | School activities participated (0-8) | Composite Index |
| `homework_intensity` | Average homework engagement frequency | Composite Index |
| `school_involvement` | Average school involvement frequency | Composite Index |
| `communication_index` | Parent-school communication frequency | Composite Index |
| `enrichment_count` | Home enrichment activities (0-7) | Composite Index |
| `has_choice` | Binary: had school choice or not | Simple Recode |

---

## 🔑 Key Findings
- School choice shows statistically significant positive association with academic success
- Family engagement — particularly homework support and school activities — meaningfully predicts student outcomes
- Low-income states experience more severe outcomes, suggesting socioeconomic factors moderate engagement effectiveness
- Best model achieves strong predictive performance (ROC-AUC > 0.70)
- LASSO selected 16 of 20 candidate predictors, confirming multi-factor nature of academic success

---

## 🛠️ Tools & Packages
| Category | Packages |
|---|---|
| Data Wrangling | `tidyverse`, `tidymodels`, `readr`, `lubridate`, `conflicted` |
| Visualization | `ggplot2`, `corrplot`, `GGally`, `gridExtra`, `viridis`, `patchwork` |
| Modeling | `nnet`, `MASS`, `pscl`, `glmnet`, `poissonreg`, `discrim` |
| Model Evaluation | `vip`, `probably`, `broom`, `car` |
| Reporting | `knitr`, `kableExtra`, `rmarkdown` |

---

## 🚀 Live Reports
👉 [Phase 1 — Data Understanding & Preparation](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase1_Data_Preparation.html)

👉 [Phase 2 — Exploratory Data Analysis](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase2_Exploratory_Analysis.html)

👉 [Phase 3 — GLM Development & Evaluation](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase3_GLM_Development.html)

---

## 📁 Repository Structure

* Phase1_Data_Preparation.Rmd - Data cleaning & feature engineering
* Phase2_Exploratory_Analysis.Rmd - EDA & variable selection
* Phase3_GLM_Development.Rmd        # Model building & evaluation
* pfi-data-2016.csv                 # Raw 2016 PFI Survey data
* pfi-data-2019.csv                 # Raw 2019 PFI Survey data
*  pfi_phase1_clean.csv              # Cleaned dataset from Phase 1
*  pfi_phase2_model_ready.csv        # Model-ready dataset from Phase 2
* .github/workflows/render.yml      # Auto-render GitHub Actions workflow
* README.md



---

## ▶️ How to Run Locally
```r
install.packages(c(
  "knitr", "kableExtra", "tidyverse", "tidymodels",
  "readxl", "ggplot2", "corrplot", "gridExtra", "viridis",
  "scales", "readr", "nnet", "MASS", "pscl", "car",
  "conflicted", "rmarkdown", "GGally", "patchwork", "broom",
  "glmnet", "poissonreg", "vip", "probably", "discrim"
))

rmarkdown::render("Phase1_Data_Preparation.Rmd")
rmarkdown::render("Phase2_Exploratory_Analysis.Rmd")
rmarkdown::render("Phase3_GLM_Development.Rmd")
```




### Kuladeep Roy G
