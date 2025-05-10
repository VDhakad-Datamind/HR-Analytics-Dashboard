# 📊 HR Analytics Dashboard in Power BI

## 🔍 Project Overview

This project is a comprehensive HR Analytics Dashboard built in **Power BI** to provide actionable insights into key HR metrics like employee distribution, attrition, salary trends, and job satisfaction across different roles, age groups, departments, and other categories.

---

-**Dataset Link**: [HR Dataset](https://github.com/VDhakad-Datamind/HR-Analytics-Dashboard/blob/main/HR_Analytics.csv)

## 🧩 Business Requirement

The HR department of a mid-sized company wanted a data-driven solution to:

- Analyze **employee demographics** (age, education, department, gender).
- Monitor **monthly salary and salary hikes**.
- Understand **attrition patterns** and identify potential areas of concern.
- Evaluate **job satisfaction** and **overtime** trends by role.
- Help leadership make informed decisions around **employee retention** and **resource allocation**.

---

## 📌 Key Features of the Dashboard

### 🔹 Overview Page
- Total employee count, average salary, average age.
- Salary distribution by age, department, education.
- Job role comparison by salary, job satisfaction, and gender ratio.
- Interactive filters by department, age group, education field, etc.
![Overview](https://github.com/VDhakad-Datamind/HR-Analytics-Dashboard/blob/main/Overview.png)


### 🔹 Attrition Page
- Attrition rate across different job roles, education fields, genders, and income levels.
- Trend analysis by **job satisfaction** and **monthly income bins**.
- Attrition insight by business travel and age.
- Comparison of attrition percentages for HR, R&D, and Sales.
![Attrition](https://github.com/VDhakad-Datamind/HR-Analytics-Dashboard/blob/main/Attrition.png)

---

## 📊 Visualizations Used
- Bar Charts
- Donut Charts
- Scatter Plots
- Line Graphs
- KPI Cards
- Filters (Slicers)

---

## 🧰 Tools & Technologies Used
- Power BI Desktop
- DAX (Data Analysis Expressions)
- Power Query Editor
- Excel/CSV as data source

---

## 🧮 DAX Measures Used

### 📌 1. Employee Count & Salary Metrics

```DAX
Employee count = DISTINCTCOUNT(HR_Analytics[EmpID])

Overall monthly salary = SUM(HR_Analytics[MonthlyIncome])

Avg Monthly salary = [Overall monthly salary] / [Employee count]

```

### 📌 2. Attrition Analysis

```DAX
Attrition count = 
CALCULATE([Employee count], HR_Analytics[Attrition] = "Yes")

Attrition rate = 
[attrition count] / CALCULATE([Employee count], ALL(HR_Analytics[Attrition]))

Attrition Target = 0.2
```

### 📌 3. Workforce Demographics

```DAX
Average age = AVERAGE(HR_Analytics[Age])

Gender Ratio = 
CALCULATE([Employee count], HR_Analytics[Gender] = "Female") /
CALCULATE([Employee count], HR_Analytics[Gender] = "Male")
```

### 📌 3. Employee Experience & Compensation

```DAX
Average Years = AVERAGE(HR_Analytics[YearsAtCompany])

Average Hike = AVERAGE(HR_Analytics[PercentSalaryHike])
```

### 📌 3. Satisfaction & Overtime

```DAX

average job satisfaction_score = AVERAGE(HR_Analytics[JobSatisfaction])

Overtime % = 
CALCULATE([Employee count], HR_Analytics[OverTime] = "Yes") / [Employee count]
```


## 🧠 Insights & Outcomes
- The highest attrition is in Sales roles (21%).
- Younger employees (under 25) have the highest attrition.
- Non-traveling employees have lower attrition.
- Job satisfaction has a clear inverse relationship with attrition rate.
- Employees in R&D have higher salaries and lower attrition compared to Sales.

---

## 📁 Repository Structure
