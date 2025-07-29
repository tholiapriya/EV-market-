EV Market Segmentation Based on Vehicle Type (India)

This project focuses on **segmenting the Indian EV market based on the type of vehicle purchased**, using demographic and income data from an automobile buying behavior dataset. The goal is to understand **which customer profiles prefer specific EV types**—such as sedans, SUVs, hatchbacks—and how preferences vary by salary, family size, and other features.

---

Dataset Overview

**Primary Dataset:** `Indian automoble buying behavour study 1.0.csv`

| Column             | Description                            |
|--------------------|----------------------------------------|
| Age                | Age of the individual buyer            |
| Profession         | Salaried / Business                    |
| Marital Status     | Married / Single                       |
| Education          | Graduate / Post Graduate               |
| No of Dependents   | Number of dependent family members     |
| Personal loan      | Whether buyer has a personal loan      |
| House Loan         | Whether buyer has a housing loan       |
| Wife Working       | Whether spouse is employed             |
| Salary             | Individual's annual salary             |
| Wife Salary        | Annual salary of spouse (if working)   |
| Total Salary       | Sum of individual and spouse salary    |
| Make               | Car model (used to infer vehicle type) |
| Price              | Price of the car owned (in INR)        |

---
 Vehicle Type Mapping

Mapped the `Make` column to general **vehicle categories**:

| Make          | Vehicle Type |
|---------------|--------------|
| Verna         | Sedan        |
| Nexon EV      | SUV          |
| Tiago EV      | Hatchback    |
| Tigor EV      | Sedan        |
| MG ZS EV      | SUV          |
| e2oPlus       | Hatchback    |
| ...           | ...          |

---
Exploratory Data Analysis (EDA)

- **SUV buyers**: Typically 30–45 years old, high income, fewer dependents
- **Hatchback buyers**: Younger (20–30), budget-conscious, entry-level salary
- **Sedan buyers**: Moderate to high income, often salaried, low loan exposure
- **Price distribution**: SUVs are priced higher (₹12–22L), hatchbacks lower (₹6–10L)

 Correlation Highlights:
- **Total Salary** correlates strongly with **SUV ownership**
- **No. of Dependents** impacts preference: families prefer SUVs
- **Wife Working = Yes** correlates with mid-high vehicle price (dual income)

---

 Data Preprocessing

- Created `Vehicle Type` column from car `Make`
- Applied **Label Encoding** to: `Profession`, `Marital Status`, etc.
- Applied **Feature Scaling** using `StandardScaler` on numerical features

---

📈 Clustering (KMeans)

Performed KMeans clustering on customer features based on vehicle type preference.

Optimal Clusters**: 3 (identified using Elbow Method)
  Cluster Summary**:

| Cluster | Dominant Vehicle Type | Buyer Profile                           |
|---------|------------------------|------------------------------------------|
| 0       | Hatchback              | Young, budget-conscious, first-time buyers |
| 1       | SUV                    | Families, high salary, urban professionals |
| 2       | Sedan                  | Professionals, average to high income      |

Visuals:
- Pairplots (Vehicle Type vs Salary, Age, Dependents)
- Heatmaps and Boxplots for deeper insights

---

 Insights & Recommendations

 Vehicle Type Preferences

| Vehicle Type | Preferred Age Group | Salary Range  | Ideal Buyer Segment           |
|--------------|----------------------|---------------|-------------------------------|
| Hatchback    | 20–30 years          | ₹4–8L         | First-jobbers, college grads  |
| Sedan        | 30–40 years          | ₹8–15L        | Working professionals         |
| SUV          | 35–50 years          | ₹15–25L       | Dual-income urban families    |

---

Strategy Suggestions

| Strategy Type     | Actionable Steps                                |
|------------------|--------------------------------------------------|
| Product Strategy | Design EVs targeting each segment's use-case     |
|                  | - Hatchbacks: city mileage, compact design       |
|                  | - Sedans: comfort, tech features                 |
|                  | - SUVs: range, safety, family size               |
| Marketing        | - Social media for Hatchbacks                    |
|                  | - Finance/EMI benefits for Sedans                |
|                  | - Family-oriented campaigns for SUVs             |

---

Additional Brand-Level Analysis

Used secondary dataset `evdataset3.csv`:

- Converted Euro prices to INR
- Compared EV efficiency across vehicle types
- Visualized:
  - Vehicle Type vs Efficiency
  - Vehicle Type vs Price
  - Price vs Efficiency

---
 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---
How to Run

```bash
pip install pandas matplotlib seaborn scikit-learn
python vehicle_type_segmentation.py  # or run the notebook
