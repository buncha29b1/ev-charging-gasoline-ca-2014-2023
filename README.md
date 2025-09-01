# ⚡ Driving Change: Assessing the Impact of Electric Vehicle Charging Infrastructure on Gasoline Consumption Across California Counties

**Author:** Khoi Van

**Project Advisor:** Alexandre Scarcioffolo

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

**Key variables (examples)**
- **Outcome:** gasoline use (per capita / per registered vehicle) at county–year
- **Main regressor:** public chargers (per 1k people / per 1k vehicles / per EV)
- **Controls (optional):** EV share, income, urbanization, unemployment, population
- **Equity views:** charger access per capita or per EV across income/urbanization groups

**Model (schematic)**
$ \text{gas\_per\_capita}_{it} &= \beta_1\,\text{level1}_{it} + \beta_2\,\text{level2}_{it} + \beta_3\,\text{dc\_fast}_{it} + \beta_4\,\text{ev\_adoption}_{it} \\
&\quad + \beta_5\,\text{income}_{it} + \beta_6\,\text{charger\_ratio}_{it} + \beta_7\,\text{capacity\_ratio}_{it} + \beta_8\,\text{coverage}_{it} \\
&\quad + \alpha_i + \gamma_t + \epsilon $

**Outputs**
- Clean tables of coefficients (with units and interpretation)
- Maps/plots of charger access and gasoline trends
- Equity charts (e.g., charger access by income quintile)

---
