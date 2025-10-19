# Megaline Plans Revenue Analysis

![Status](https://img.shields.io/badge/Status-Completed-success)  
![Python](https://img.shields.io/badge/Python-3.11%2B-blue)  
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-yellow)  
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)  
![Scipy](https://img.shields.io/badge/SciPy-Hypothesis%20Testing-lightgrey)  
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Visualization-9cf)

---

## Project Description

This project analyzes customer behavior and revenue patterns for **Megaline**, a telecommunications company offering two prepaid plans: **Surf** and **Ultimate**.  

The goal is to determine **which plan generates more revenue** and whether **location impacts customer spending**.  

We use data exploration, aggregation, and hypothesis testing to guide data-driven decisions for Megaline’s commercial team.

---

## Dataset Overview

The analysis uses data from **500 Megaline users** during 2018.  
Each user has information about calls, messages, internet usage, city, and plan type.

**Files included:**
- `megaline_users.csv` — customer information (age, city, plan, registration dates)  
- `megaline_calls.csv` — number and duration of calls  
- `megaline_messages.csv` — SMS usage  
- `megaline_internet.csv` — data usage in MB  
- `megaline_plans.csv` — plan details (costs, limits, overage fees)

**Key variables:**
- `plan_name`, `usd_monthly_fee`, `minutes_included`, `messages_included`, `mb_per_month_included`
- `usd_per_minute`, `usd_per_message`, `usd_per_gb`
- `duration`, `mb_used`, `message_date`, `city`, `user_id`

---

## Data Preparation

1. **Loaded and inspected all five datasets** using `pandas`.  
2. **Fixed data types** (converted dates to `datetime`).  
3. **Handled missing and duplicate values**.  
4. **Merged datasets** to calculate monthly usage for each user.  
5. **Computed monthly revenue** based on plan limits and overage fees:  
   - Rounded minutes up per call.  
   - Converted total MB per month to GB (rounded up).  
   - Added plan’s monthly fee + extra usage costs.  

---

## Exploratory Data Analysis (EDA)

### Usage Behavior
- Checked call duration, message counts, and internet consumption per month.  
- Verified logical ranges for `order_hour_of_day` and `order_dow`.  
- Observed higher data usage among **Ultimate** users.

### Revenue by Plan
| Plan | Mean Revenue (USD) | Std. Deviation (USD) |
|------|--------------------:|---------------------:|
| **Surf** | **60.71** | **55.39** |
| **Ultimate** | **72.31** | **11.40** |

**Interpretation:**  
- Ultimate users generate **~$11.6 more** per month on average.  
- Surf users show **high variability**, meaning some exceed limits heavily.  
- Ultimate users have **more stable and predictable** revenue.

---

## Hypothesis Testing

### **Hypothesis 1 — Plan Comparison**

**H₀:** The average monthly revenue for Surf and Ultimate users is equal.  
**H₁:** The average monthly revenue for Surf and Ultimate users differs.


**t-test Result**

**p-value** → **0.0000** 


**Conclusion:**  
We reject H₀, there is a statistically significant difference between the two plans.  
**Ultimate** users generate higher revenue than Surf users.

---

### **Hypothesis 2 — Regional Comparison**

**H₀:** The average monthly revenue for users in the NY–NJ area equals that of other regions.  
**H₁:** The average monthly revenue differs.

| Group | Mean Revenue (USD) |
|--------|-------------------:|
| **Other Regions** | **65.22** |
| **NY–NJ Area** | **59.92** |


**t-test Result**

**p-value** → **0.0335** 


**Conclusion:**  
We reject H₀, there is a **statistically significant difference** between regions — users in the **NY–NJ area spend slightly less** (≈ $5 difference).  
While significant, this effect is **small in business terms**.

---

## Visualizations

- Histograms and boxplots of user revenue by plan.  
- Distribution plots of minutes, SMS, and data usage.  
- Comparative bar charts of mean revenue by plan and by city.  

---

## Technologies Used

- **Language:** Python 3.11+  
- **Libraries:**  
  - `pandas` — data wrangling  
  - `numpy` — rounding and calculations  
  - `matplotlib, seaborn` — visualizations  
  - `scipy` — statistical tests  
  - `jupyter` — notebooks

---

## Conclusion (to be filled after analysis)

- Which plan (Surf/Ultimate) has higher **average monthly revenue**?  
- Are NY–NJ users significantly different from others?  
- What usage patterns drive revenue (minutes, SMS, or data overages)?  
- Recommendations for **marketing budget allocation**.

---

## Author

**Gerzon Medina Ortiz**  
📧 [gerzon13medin@gmail.com](mailto:gerzon13medin@gmail.com)  
💼 [LinkedIn](https://www.linkedin.com/in/gerzon-medina-robotics-datascience)