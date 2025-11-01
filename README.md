# 📊 Hypothesis Testing in Python — Data Analyst Portfolio Project

## 🧠 Overview

This project demonstrates the application of core statistical hypothesis testing techniques using Python. It is designed to showcase my ability to apply statistical reasoning to real-world business data, using Python libraries such as `pandas`, `scipy`, `statsmodels`, and `seaborn`. The analysis is conducted in a Jupyter Notebook format and includes both code and interpretation of results.

The project is part of my data analyst portfolio and reflects my proficiency in statistical testing, data wrangling, and drawing actionable insights from structured datasets.

---

## 📁 Repository Structure
├── Sample_Dataset.csv           # HR dataset used for statistical analysis 
├── jupyter_notebook             # Contains the hypothesis testing notebook (.ipynb) 
├── README.md                    # Project documentation

---

## 📂 Dataset Description

The dataset used in this project is a fictional HR dataset titled `Employee Sample Data.xlsx`. It contains employee-level information across various departments, roles, and demographics. This dataset is ideal for demonstrating statistical tests due to its diversity and structure.

### 🔑 Key Columns:

| Column Name       | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| `EEID`            | Unique employee identifier                                                  |
| `Full Name`       | Employee's full name                                                        |
| `Job Title`       | Role or designation (e.g., Analyst, Director, VP)                           |
| `Department`      | Department within the company (e.g., IT, Finance, Sales)                    |
| `Business Unit`   | Broader business division                                                   |
| `Gender`          | Gender identity                                                             |
| `Ethnicity`       | Ethnic background                                                           |
| `Age`             | Age of the employee                                                         |
| `Hire Date`       | Date of joining                                                             |
| `Annual Salary`   | Current annual salary in USD                                                |
| `Bonus %`         | Bonus as a percentage of salary                                             |
| `Country`         | Country of employment                                                       |
| `City`            | City of employment                                                          |
| `Exit Date`       | Date of exit (if applicable)                                                |

---

## 📐 Statistical Tests Performed

This project includes the following hypothesis tests, each with real-world business questions, assumptions, Python implementation, and interpretation of results:

### 1. ✅ Z-Test
- **Use Case**: Determine if the average salary of employees in a department differs from a known population mean.
- **Assumptions**:
  - Population standard deviation is known.
  - Sample size is sufficiently large (n > 30).
- **Example**: Is the average salary in the IT department significantly different from $100,000?

### 2. ✅ T-Test
- **One-Sample T-Test**:
  - Compare the sample mean to a known value when population standard deviation is unknown.
- **Two-Sample T-Test**:
  - Compare means between two independent groups (e.g., Male vs. Female salaries).
- **Assumptions**:
  - Data is normally distributed.
  - Equal or unequal variances handled accordingly.
- **Example**: Do male and female employees earn significantly different salaries?

### 3. ✅ One-Way ANOVA
- **Use Case**: Compare mean salaries across more than two departments.
- **Assumptions**:
  - Independence of observations.
  - Homogeneity of variances.
  - Normally distributed groups.
- **Example**: Is there a significant difference in average salary among IT, Finance, and Sales departments?

### 4. ✅ Two-Way ANOVA
- **Use Case**: Assess the effect of two categorical variables (e.g., Gender and Department) on a continuous outcome (e.g., Salary).
- **Assumptions**:
  - Same as One-Way ANOVA, plus interaction effects.
- **Example**: Do gender and department jointly affect employee salaries?

### 5. ✅ Chi-Square Test of Independence
- **Use Case**: Test the relationship between two categorical variables.
- **Assumptions**:
  - Observations are independent.
  - Expected frequency in each cell is at least 5.
- **Example**: Is there an association between gender and employee exit status?

---

## 🛠️ Tools & Libraries Used

- `pandas` — Data manipulation and preprocessing  
- `numpy` — Numerical operations  
- `scipy.stats` — Z-test, T-test, Chi-Square  
- `statsmodels` — ANOVA (One-Way and Two-Way)  
- `seaborn` & `matplotlib` — Data visualization  

---


## 📈 Statistical Tests Performed

| Test | Purpose | Result | Insight |
|------|----------|--------|---------|
| Independent T-Test | Salary difference by gender | ✅ Significant | Salary differs by gender |
| Chi-Square Test | Gender vs Department | ❌ Not significant | Gender distribution balanced |
| One-Way ANOVA | Salary vs Department | ✅ Significant | Salary differs by department |
| Two-Way ANOVA | Department × Ethnicity | ✅ / ❌ Partial | Department affects salary; ethnicity doesn’t |
| One-Sample Z-Test | Mean employee age | ❌ Not significant | Mean age ≈ 44 years |
| Two-Sample Z-Test | IT vs Finance salary | ✅ Significant | Finance pays higher salaries |
| Proportion Z-Test | Male ratio > 50%? | ❌ Not significant | Balanced gender ratio |

---

## 🧮 Detailed Test Insights

### 1️⃣ Independent T-Test (Salary vs Gender)
**Objective:** To test whether there is a significant difference in mean annual salary between male and female employees.  
**Result:**  
- *t-statistic = 2.80*, *p-value = 0.028*  
✅ **Reject null hypothesis**

**Insight:**  
There is a **significant difference** in average salary between male and female employees.

---

### 2️⃣ Chi-Square Test (Department vs Gender)
**Objective:** To check whether gender distribution is independent of department assignment.  
**Result:**  
- *Chi² = 3.91*, *p-value = 0.688*  
❌ **Fail to reject null hypothesis**

**Insight:**  
There is **no significant association** between gender and department — gender representation is fairly balanced across departments.

---

### 3️⃣ One-Way ANOVA (Salary vs Department)
**Objective:** To determine whether mean annual salary differs significantly across departments.  
**Result:**  
- *F-statistic = 7.02*, *p-value = 2.44e-07*  
✅ **Reject null hypothesis**

**Insight:**  
There is a **significant difference** in mean salary among departments — some departments pay more than others.

---

### 4️⃣ Two-Way ANOVA (Salary vs Department & Ethnicity)
**Objective:** To analyze how department and ethnicity affect employee salary and to check for interaction effects.  

| Factor | F-value | p-value | Significance |
|:--------|:--------:|:---------:|:-------------:|
| Department | 6.81 | 4.36e-07 | ✅ Significant |
| Ethnicity | 1.24 | 0.29 | ❌ Not Significant |
| Interaction (Dept × Ethnicity) | 0.96 | 0.49 | ❌ Not Significant |

**Insights:**  
- Department has a **strong influence** on salary.  
- Ethnicity has **no significant effect**.  
- No interaction effect — salary differences across departments are consistent across ethnic groups.

---

### 5️⃣ One-Sample Z-Test (Average Age)
**Objective:** To determine whether the average employee age differs from a population average of 44 years.  
**Result:**  
- *z-statistic = 0*, *p-value = 1.0*  
❌ **Fail to reject null hypothesis**

**Insight:**  
Average employee age (≈44 years) is **not significantly different** from the population average.

---

### 6️⃣ One-Sided Two-Sample Z-Test (IT vs Finance Salary)
**Objective:** To test whether IT department salaries are greater than Finance department salaries.  
**Result:**  
- *z-statistic = -4.42*, *p-value = 9.7e-06*  
✅ **Reject null hypothesis**

**Insight:**  
Finance department has a **significantly higher average salary** than IT.  
(IT mean ≈ ₹97,790 vs Finance mean ≈ ₹122,803)

---

### 7️⃣ One-Sample Z-Test for Proportion (Gender)
**Objective:** To test whether the proportion of male employees is greater than 50%.  
**Result:**  
- Male proportion = 48.2%, *z = -1.14*, *p = 0.25*  
❌ **Fail to reject null hypothesis**

**Insight:**  
Proportion of male employees (48%) is **not significantly greater than 50%**, indicating **gender balance**.

---

## 🧭 Overall Findings

- **Department** is the **strongest factor** influencing salaries.  
- **Gender** has a measurable impact on salary levels.  
- **Ethnicity** does not significantly affect pay.  
- **No bias** is found in gender distribution across departments.  
- **Finance** employees earn significantly higher salaries than **IT** employees.  
- The company has a **balanced gender and age demographic** overall.

---

## 🎨 Visualizations Used

- Boxplots for salary by gender  
- Count plots for department vs gender  
- Bar charts for salary by department and ethnicity  
- Interaction plots for two-way ANOVA  
- Pie chart for gender distribution  
- Histogram for age distribution  

---

## 👨‍💻 About Me

Hi, I'm **Nishant**, a data analyst passionate about statistical modeling, clean Python workflows, and solving real-world problems with data. This project reflects my hands-on approach to hypothesis testing and my commitment to clarity, efficiency, and reproducibility.

---

## 📬 Connect with Me

- 📂 GitHub: [your-github-username]  
- 💼 LinkedIn: [your-linkedin-profile]  
- 📧 Email: [your-email-address]



