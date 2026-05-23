📊 HR Employee Attrition Dashboard 

📌 Project 

This project is an interactive HR Employee Attrition Dashboard built using Power BI Desktop.  
The dashboard helps companies understand why employees are leaving by visualizing key patterns  
across departments, age groups, salary ranges, job satisfaction levels, and overtime status.

| Detail                  | Info                                      |
|-------------------------|-------------------------------------------|
| Dataset Used            | IBM HR Analytics Employee Attrition Dataset |
| Total Employees         | 1,470                                     |
| Employees Who Left      | 237                                       |
| Overall Attrition Rate  | 16.1%                                     |

 🚀 Features

- ✅ 3 KPI Cards — Instantly shows Total Employees, Attrition Count, and Attrition Rate
- ✅ Donut Chart — Shows attrition split across departments
- ✅ Bar Chart — Shows which age group leaves the most
- ✅ Column Chart — Shows how job satisfaction affects attrition
- ✅ Bar Chart — Shows the impact of overtime on attrition
- ✅ Line Chart — Shows how monthly income relates to attrition rate
- ✅ 3 Interactive Slicers — Filter entire dashboard by Department, Age Group, and Overtime
- ✅ One-click filtering — Clicking any slicer updates all charts simultaneously
- ✅ Clean professional layout — Dark background with bold titles and red highlights

🛠️ Technologies Used

| Technology       | Purpose                               |
|------------------|---------------------------------------|
| Power BI Desktop | Building and designing the dashboard  |
| DAX Formulas     | Creating calculated measures          |
| Power Query      | Cleaning and transforming data        |
| CSV Dataset      | IBM HR Attrition data source          |
| GitHub           | Project documentation and sharing     |

🔄 Workflow

```
START
  │
  ▼
Download Dataset
  │   └── IBM HR Attrition CSV from Kaggle
  │
  ▼
Open Power BI Desktop
  │
  ▼
Load Dataset
  │   └── Get Data → Text/CSV → Select File → Load
  │
  ▼
Clean Data in Power Query Editor
  │   ├── Age           →  Whole Number
  │   ├── MonthlyIncome →  Whole Number
  │   ├── YearsAtCompany→  Whole Number
  │   ├── Attrition     →  Text
  │   ├── Department    →  Text
  │   └── Gender        →  Text
  │
  ▼
Create Calculated Column
  │   └── Age Group
  │         ├── Under 25
  │         ├── 26 to 35
  │         ├── 36 to 45
  │         └── Above 45
  │
  ▼
Create DAX Measures
  │   ├── Total Employees
  │   ├── Attrition Count
  │   └── Attrition Rate
  │
  ▼
Build Visualizations
  │   ├── KPI Card 1  →  Total Employees
  │   ├── KPI Card 2  →  Attrition Count
  │   ├── KPI Card 3  →  Attrition Rate
  │   ├── Donut Chart →  Attrition by Department
  │   ├── Bar Chart   →  Attrition by Age Group
  │   ├── Column Chart→  Attrition by Job Satisfaction
  │   ├── Bar Chart   →  Overtime Impact on Attrition
  │   └── Line Chart  →  Monthly Income vs Attrition Rate
  │
  ▼
Add Interactive Slicers
  │   ├── Slicer 1  →  Department
  │   ├── Slicer 2  →  Age Group
  │   └── Slicer 3  →  OverTime
  │
  ▼
Format Dashboard
  │   ├── Apply dark background color
  │   ├── Add bold titles to all charts
  │   ├── Apply red highlights for high attrition
  │   └── Add main dashboard title at top center
  │
  ▼
Save and Export
  │   ├── Save as .pbix file
  │   └── Export as PDF
  │
  ▼
END
```
📂 Project Structure

```
HR-Employee-Attrition-Dashboard/
│
├── 📁 Dataset/
│   └── HR-Employee-Attrition.csv             # Raw IBM HR dataset
│
├── 📁 Dashboard/
│   └── HR_Attrition_Dashboard.pbix           # Power BI dashboard file
│
├── 📁 Export/
│   └── HR_Attrition_Dashboard.pdf            # Exported PDF of dashboard
│
├── 📁 Screenshots/
│   ├── dashboard_overview.png                # Full dashboard screenshot
│   ├── kpi_cards.png                         # Three KPI cards at top
│   ├── donut_chart.png                       # Attrition by Department
│   ├── bar_chart_age.png                     # Attrition by Age Group
│   ├── column_chart_satisfaction.png         # Attrition by Job Satisfaction
│   ├── bar_chart_overtime.png                # Overtime Impact on Attrition
│   └── line_chart_income.png                 # Income vs Attrition Rate
│
└── README.md                                 # Project documentation
```
 DAX Formulas Used in This Project

```dax
-- Calculated Column
Age Group = 
IF('HR-Employee-Attrition'[Age] <= 25, "Under 25",
IF('HR-Employee-Attrition'[Age] <= 35, "26 to 35",
IF('HR-Employee-Attrition'[Age] <= 45, "36 to 45",
"Above 45")))

-- Measure 1
Total Employees = 
FORMAT(COUNT('HR-Employee-Attrition'[EmployeeNumber]),"0")

-- Measure 2
Attrition Count = 
FORMAT(
CALCULATE(
COUNT('HR-Employee-Attrition'[Attrition]),
'HR-Employee-Attrition'[Attrition] = "Yes"
), "0")

-- Measure 3
Attrition Rate = 
FORMAT(
DIVIDE(
CALCULATE(
COUNT('HR-Employee-Attrition'[Attrition]),
'HR-Employee-Attrition'[Attrition] = "Yes"
),
COUNT('HR-Employee-Attrition'[EmployeeNumber])
* 100,
"0.0"
)
```
 🎯 Conclusion

This HR Employee Attrition Dashboard proves that employees do not leave  randomly.  
There are clear, measurable, and fixable reasons behind every resignation.

```
Key Takeaways
─────────────────────────────────────────────────────────────────
  🔴  Overtime    →  Single biggest driver of attrition
  🔴  Low Salary  →  Makes employees easy targets for competitors
  🔴  Low Satisfaction → Creates silent but steady resignations
  🔴  Young Employees → Need better career growth opportunities
  🔴  Sales Dept  →  Needs urgent culture and workload changes
─────────────────────────────────────────────────────────────────
```
