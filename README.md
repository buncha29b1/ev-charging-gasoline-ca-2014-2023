# ⚡ Driving Change: Assessing the Impact of Electric Vehicle Charging Infrastructure on Gasoline Consumption Across California Counties

**Author:** Khoi Van

**Project Advisor:** Dr. Alexandre Scarcioffolo, Professor at Denison Data Analytics Department

**Program:** Lisska Summer Scholars Research - Denison University

---

## 🔍 Overview
How does public **EV charging infrastructure** relate to **gasoline use** over time—and who benefits?  
This project builds a **county–year panel (2014–2023)** for California and estimates the relationship between **charger availability** and **gasoline consumption**, with attention to **equity** (access across different communities).

**Core questions**
- Do more public chargers associate with **lower gasoline use** (per capita / per registered vehicle)?
- Are effects **heterogeneous** (urban vs. rural; income levels; EV adoption levels)?
- How is **charger access** distributed (equity lens)?

**Methods (high level)**
- **Two-way fixed effects (TWFE)** panel models with **county FE** + **year FE**  
- Robust/clustered SEs; alternative specs as sensitivity checks  
- Descriptive mapping and trend plots

---

## 🗂 Project Structure

```
├── data/                                  # relevant data files (see documentations in the "Data" section of research paper)
├── .gitignore                             # ignores history/caches/local libs
├── Khoi Van - Summer Research Paper.pdf   # research paper
├── Khoi Van - Summer Research Poster.pdf  # research poster
├── README.md                              # this file
├── Summer_Research_Code_Final.Rmd         # main analysis (R/Quarto)
├── Summer_Research_Code_Final.html        # rendered notebook (open in browser)
```

---

## 🛠 Methodology

1. **Data Preprocessing**
- Construct county–year panel (2014–2023): public charger counts (L1/L2/DC Fast), EV registrations, income, population, gasoline sales.
- Build derived metrics: charger density (per capita / per EV), **capacity proxy**, and **coverage** (% of land within a buffer of any public charger).

2. **Model Formulation (TWFE OLS)**

Our study employs a two-way fixed-effects OLS regression model:

```math
\begin{aligned}
\text{gas\_per\_capita}_{it} &= \beta_1\,\text{level1}_{it} + \beta_2\,\text{level2}_{it} + \beta_3\,\text{dc\_fast}_{it} + \beta_4\,\text{ev\_adoption}_{it} \\
&\quad + \beta_5\,\text{income}_{it} + \beta_6\,\text{charger\_ratio}_{it} + \beta_7\,\text{capacity\_ratio}_{it} + \beta_8\,\text{coverage}_{it} \\
&\quad + \alpha_i + \gamma_t + \epsilon
\end{aligned}
```

where $\alpha_i$ and $\gamma_t$ are county and year fixed effects respectively. Standard errors are clustered by county to account for serial correlation.

3. **Outputs**
- Clean tables of FE model coefficients (with units, p-value and interpretation)
- Maps/plots of charger access and gasoline trends
- Equity charts (e.g., charger access by income quintile)

---

## 🔁 Reproducibility
- **Quick view:** open `Outputs/Summer_Research_Code_Final.html` in your browser.
- **Run locally (R):**
  1) Open the project at repo root  
  2) Restore packages and render:
     ```r
     install.packages("renv")      # if needed
     renv::restore()               # installs exact versions from renv.lock
     rmarkdown::render("Notebooks/Summer_Research_Code_Final.Rmd",
                       output_file = "../Outputs/Summer_Research_Code_Final.html")
     ```
- Environment managed with **renv** (commit `renv.lock`, `renv/activate.R`, `.Rprofile`; ignore `renv/library/`).

---

## 📈 Key Findings
- Greater **public charger availability/coverage** is associated with **lower gasoline use per capita**, controlling for county/year effects.  
- Relationships tend to be **stronger in high-EV or urban counties**; equity views highlight variation in access across communities.  
- Results are **robust** across alternative normalizations and coverage definitions; diagnostics support model assumptions.  
*(See the paper and HTML notebook for coefficients, CIs, and full figures.)*

---

## 📚 References

*(See the Data and References sections in the PDF research paper for full lists of references and data sources.)*

---

## 📬 Contact
- Khoi Van: van_k1@denison.edu
- Dr. Alexandre Scarcioffolo: scarcioffoloa@denison.edu
