# Predicting-k-12-Success-using-generalized-linear-models
Built GLMs in R using U.S. Census education data to analyze socioeconomic factors affecting student performance across school districts. Applied cross-validation and AIC-based model selection, and created visualizations and coefficient interpretations to communicate key academic outcome predictors.

# Predicting K-12 Success Using Generalized Linear Models
### STA 631 — Grand Valley State University | Kuladeep Roy G

---

## 📌 Overview
A three-phase statistical analysis investigating the impact of school 
choice and family engagement on K-12 educational success using data from 
the U.S. Department of Education's Parent and Family Involvement (PFI) 
Survey. Developed to provide evidence-based recommendations for GVSU's 
K-12 Connect program.

---

## ❓ Research Question
**Does school choice and family engagement significantly predict 
K-12 student academic success?**

---

## 📂 Dataset
| Dataset | Year | Observations | Variables |
|---|---|---|---|
| PFI Survey | 2019 (Primary) | 15,500 | 71 |
| PFI Survey | 2016 (Validation) | - | - |

**Source:** U.S. Department of Education, National Center for Education Statistics

---

## 🔍 Three-Phase Analysis

**Phase 1 — Data Preparation**
- Variable identification and classification
- Feature engineering (engagement index, homework intensity, school involvement)
- Missing data handling and data quality assessment

**Phase 2 — Exploratory Analysis**
- Summary statistics and distribution analysis
- Correlation analysis and visualization
- Key predictor identification

**Phase 3 — GLM Development**
- Logistic Regression (binary outcome: A/B vs C/D grades)
- Multinomial Regression (4-category grade outcomes)
- Poisson Regression (engagement count outcome)
- Discriminant Analysis
- Model comparison and validation

---

## 🛠️ Tools & Packages
| Category | Packages |
|---|---|
| Data Wrangling | `tidyverse`, `tidymodels`, `readr`, `conflicted` |
| Visualization | `ggplot2`, `corrplot`, `gridExtra`, `viridis` |
| Modeling | `nnet`, `MASS`, `pscl`, `car` |
| Reporting | `knitr`, `kableExtra`, `rmarkdown` |

---

## 📈 Key Features Engineered
| Feature | Description |
|---|---|
| `success_binary` | 1 if grades A/B, 0 if C/D |
| `engagement_count` | School activities participated (0-8) |
| `homework_intensity` | Average homework engagement frequency |
| `school_involvement` | Average school involvement frequency |
| `communication_index` | Parent-school communication frequency |
| `has_choice` | Binary: had school choice or not |

---

## 🚀 Live Reports
👉 [Phase 1 — Data Preparation](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase1_Data_Preparation.html)
👉 [Phase 2 — Exploratory Analysis](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase2_Exploratory_Analysis.html)
👉 [Phase 3 — GLM Development](https://kdeepr.github.io/Predicting-k-12-Success-using-generalized-linear-models/Phase3_GLM_Development.html)

---

## ▶️ How to Run Locally
```r
install.packages(c("knitr","kableExtra","tidyverse","tidymodels",
                   "ggplot2","corrplot","gridExtra","viridis",
                   "nnet","MASS","pscl","car","conflicted","rmarkdown"))

rmarkdown::render("Phase1_Data_Preparation.Rmd")
rmarkdown::render("Phase2_Exploratory_Analysis.Rmd")
rmarkdown::render("Phase3_GLM_Development.Rmd")
```
