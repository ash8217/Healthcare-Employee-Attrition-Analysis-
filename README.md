# Healthcare Sector Employee Attrition - Exploratory Data Analysis

## Introduction
This project applies **Exploratory Data Analysis (EDA)** to the **Watson Healthcare Employees dataset**.  
The dataset contains employee and organizational information useful for **supervised ML, unsupervised ML, and HR analytics**.  

**Goal:** Identify insights and key factors driving employee attrition (job quitting).

**Dataset Source:** LINK  

---

## About the Dataset
- **Target Variable:** `Attrition` (Yes/No – whether an employee left).  
- **Features:** Sociodemographic and workplace data (35 columns).  

### Dataset Dictionary (selected):
- **Age** – Employee’s age  
- **Attrition** – Target variable (Yes/No)  
- **BusinessTravel** – Frequency of business travel  
- **Department** – Healthcare department  
- **DistanceFromHome** – Distance from workplace  
- **MonthlyIncome** – Monthly salary  
- **JobLevel** – Numeric grade of the employee  
- **JobRole** – Role type (e.g., Nurse, Admin)  
- **OverTime** – Whether employee worked overtime  
- **YearsInCurrentRole**, **YearsSinceLastPromotion**, **YearsWithCurrentManager** – Career progression indicators  
- **JobSatisfaction**, **WorkLifeBalance**, **EnvironmentSatisfaction**, **RelationshipSatisfaction** – Engagement metrics  

---

## EDA Action Plan
Steps followed:  
1. Import Python Libraries (Pandas, NumPy, Matplotlib, Seaborn, Scipy)  
2. Data Cleaning & Preprocessing  
   - Dropped redundant columns (`EmployeeID`, `DailyRate`, etc.)  
   - Removed constant-value features (`Over18`, `StandardHours`, `EmployeeCount`)  
   - Fixed categorical redundancies (`Administrative` → `Admin`)  
3. Numerical Features Analysis (distribution, correlations, scatterplots)  
4. Categorical Features Analysis (bar charts, cross-tabs, chi-square tests)  
5. Numerical vs Categorical Relationships  
6. Key Takeaways & HR Recommendations  

---

## Numerical Features Analysis
- **20 numerical features** selected (`Age`, `MonthlyIncome`, `JobLevel`, etc.)  
- **Observations:**  
  - Average age ~36 years.  
  - No missing values, no major outliers.  
  - Key attrition-related features: `DistanceFromHome`, `MonthlyIncome`, `YearsInCurrentRole`, `YearsSinceLastPromotion`.  
- **Correlations:**  
  - `Age` ↔ `TotalWorkingYears`  
  - `JobLevel` ↔ `MonthlyIncome`  
  - `TotalWorkingYears` ↔ `MonthlyIncome`  
  - `PercentSalaryHike` ↔ `PerformanceRating`  

---

## Categorical Features Analysis
- **8 categorical features** (`BusinessTravel`, `Department`, `JobRole`, `OverTime`, etc.)  
- **Insights from visualizations:**  
  - Only ~200 employees left (low attrition).  
  - Higher attrition among **males (113 vs 86 females)**.  
  - **Overtime workers** more likely to quit (139 left vs 60 non-overtime).  
  - **Nurses** had highest attrition; **Maternity** & **Cardiology** had highest departmental attrition.  
  - **Single employees** left more (114 vs married/divorced).  
  - **Rare business travelers** showed higher attrition.  

---

## Statistical Significance (Chi-Square Test)
- Tested categorical feature relationships with attrition.  
- **Key statistically significant factors:**  
  - **Overtime**  
  - **Job Role (Nurses)**  
  - **Department (Maternity)**  
  - **Business Travel (rare travel)**  
  - **Marital Status (Single)**  

Gender showed higher attrition among males, but not statistically significant.  

---

## Numerical Features vs Attrition
- Visualized using **Seaborn strip plots**.  
- **Key patterns:**  
  - Majority attrition at **JobLevel 3**.  
  - Peak attrition at **6 years in current role**, **~3 years since last promotion**.  
  - Salary hikes showed little influence on retention.  
  - Work-life balance, job satisfaction, and environment satisfaction had minimal variation across attrition groups.  

---

## Key Takeaways & HR Recommendations
1. **Monitor overtime** in high-risk departments (Maternity, Nurses).  
2. **Encourage business travel** where possible (reduce stagnation).  
3. **Support single employees** with tailored engagement programs.  
4. **Implement job rotation** policies for employees staying **2–7 years** in the same role.  
5. **Rethink salary hike policies** as they may not effectively reduce attrition.  

---
. 
- Implement a policy of job rotations after the employee spends around 2 to 7 years in the same role where possible.
