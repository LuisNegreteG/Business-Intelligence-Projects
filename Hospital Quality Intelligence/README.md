# Hospital Quality Intelligence Dashboard – Tableau

It delivers an **executive-ready dashboard** using advanced Tableau techniques such as **data blending, Level of Detail (LOD) expressions, parameters (what-if), and trend/forecasting analysis**.

---

## Objective

- Build a comprehensive KPI panel (**national vs. state, % above national**).  
- Provide comparative insights by **ownership type** (Government, Private, Voluntary).  
- Develop two decision-support modules: **Timeliness What-If Simulator** and **Readmission Value Analysis**.  

---

## Data Preparation
- **Tool**: Tableau Prep Builder.  
- **Steps**:  
  - Removed non-analytic fields and standardized data types.  
  - Consolidated Ownership categories into Government, Private, Voluntary.  
  - Converted “Not Available” to `NULL` for consistent handling.  
  - Mapped text ratings into numeric scales (Overall 1–5; Mortality, Safety, Readmission, Timeliness 1–3).  
  - Corrected Latitude/Longitude and grouped U.S. territories as “Other”.  
  - Ensured one row per Provider ID.  
  - Generated synthetic fields in Python: Staff-to-Patient Ratio and Avg Readmission Cost (range checks, winsorization, fixed random seed).  
- **Final Output**: a `.hyper` extract joined on Provider ID powering all KPIs and decision modules:contentReference[oaicite:1]{index=1}.  

---

## Dashboard Stories

### 1. Hospital Quality Intelligence (Story A)
- **Timeliness vs Rating**: Efficiency outliers show that more staff doesn’t always equal better performance.  
- **Readmission: Cost vs Score**: Cost is a poor predictor of outcomes; high-cost/low-score hospitals (esp. Private) are priority targets.  
- **Top States**: South Dakota, Hawaii, and New Hampshire exceed national average (2.99).  
- **Geographic Patterns**: No strong regional trends → performance depends on management/ownership, not geography:contentReference[oaicite:2]{index=2}.  

### 2. Metrics by Ownership (Story B)
- **Private (For-Profit)**: Strong on Safety & Timeliness, weak on Readmission.  
- **Government**: Near average, but Mortality below benchmark.  
- **Voluntary (Non-Profit)**: Lead overall, but lag in Timeliness.  
- **Decision Actions**: Tailored bundles and interventions per ownership type:contentReference[oaicite:3]{index=3}.  

### 3. Trends Analysis (Story C)
- Tested association between **staff ratio and quality metrics** (Overall, Mortality, Timeliness, Safety).  
- Weak correlations (R² ≈ 0.02–0.30, non-significant p-values).  
- Insights: More staff does not guarantee better outcomes → consider skill mix, process design, and outlier benchmarking:contentReference[oaicite:4]{index=4}.  

### 4. Sensitivity Analysis (Story D)
- **What-If Simulator**: Adjusts state Timeliness based on Emergency capacity increases.  
- Example: California requires ~20–25% increase in capacity with ≥0.15 Timeliness lift per 10pp to exceed 2.0 rating.  
- **Impact**: Helps policymakers allocate resources where marginal ROI is highest:contentReference[oaicite:5]{index=5}.  

---

## Tools & Skills
- **Tableau Desktop** – dashboards, blending, LOD, parameters, forecasting.  
- **Tableau Prep Builder** – data cleaning and integration.  
- **Python** – synthetic data generation, reproducibility controls.  

---

## Dashboard Preview

<img width="1582" height="832" alt="image" src="https://github.com/user-attachments/assets/f5ce14b0-bdd0-43a9-a740-8a1055e023ae" />

<img width="1578" height="781" alt="image" src="https://github.com/user-attachments/assets/e7a4414d-ed47-4ccb-9855-5ea8de396b6f" />

<img width="1580" height="781" alt="image" src="https://github.com/user-attachments/assets/cb171a12-6597-45c5-90cd-ad72278b84f1" />

<img width="1582" height="832" alt="image" src="https://github.com/user-attachments/assets/28f62fc3-b179-4124-a5dc-a7b0c789afcd" />
