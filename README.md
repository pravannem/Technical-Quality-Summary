**📊 Technical Quality Insights Dashboard | Power BI**

**📌 Project Overview**

The Technical Quality Insights Dashboard is an end-to-end Power BI analytics solution designed to monitor and analyse consultant quality performance across multiple iQueue categories.

The dashboard provides leaders with visibility into consultant performance, quality score trends, sample completion volumes, and team-level insights, enabling targeted coaching, quality improvement, and operational decision-making.

**🎯 Business Problem**

The Tech Quality team required a centralised reporting solution to replace manual quality tracking across multiple iQueue streams.

Key objectives were to:

Monitor consultant quality performance.
Compare performance across Team Leaders and iQueue categories.
Track quality trends over time.
Measure sample completion volumes.
Identify performance gaps and support targeted coaching.

**🗂️ Data Sources**

The solution was built using five separate quality assessment datasets:

- AME Raw (Amendments
- CLM Raw (Claims)
- EML Raw (Emails)
- VAR Raw (Variations)
- TERM Raw (Terminations)

Reporting period:**July 2025 – April 2026**

**🛠️ Data Preparation (Power Query)**

Performed comprehensive data cleansing and transformation including:

- Removed unnecessary tables and redundant datasets.
- Handled missing values, #N/A errors, and invalid records.
- Corrected data types across all fields.
- Standardised consultant, Team Leader, and CSC information.
- Removed duplicate records where required.
- Added iQueue Category classifications.
- Appended five raw datasets into a consolidated fact table:Fact_QualityReviews
  
**🏗️ Data Model**

Designed a star schema consisting of:

**Fact Table**

- Fact_QualityReviews

Contains individual quality review records including:

- Consultant
- Team Leader
- CSC
- Review Date
- iQueue Number
- iQueue Category
- Quality Score
- Compliance Check Results
- Feedback
  
**Dimension Tables**

Dim_Date

Created using DAX Calendar with:

- Date
- Year
- Quarter
- Month
- Month Year

Dim_Consultant

- Consultant
- Team Leader
- CSC

Dim_iQueue

- Amendment
- Claims
- Emails
- Variations
- Terminations

  
**📐 Data Modelling Approach**

Implemented a one-to-many star schema relationship model:

                      Dim_Date
                         |
                         |
Dim_Consultant ---- Fact_QualityReviews ---- Dim_iQueue



**📊 DAX Measures**

Created reusable measures including:

Average Quality Score =
AVERAGE(Fact_QualityReviews[Score])

Samples Completed =
COUNTROWS(Fact_QualityReviews)

Consultants Reviewed =
DISTINCTCOUNT(Fact_QualityReviews[Consultant])

Total iQueue Categories =
DISTINCTCOUNT(Dim_iQueue[iQueue Category])


**📈 Dashboard Pages**

1. Tech Quality Summary - Provides an executive overview including:

- Average Quality Score KPI
- Total Samples Completed KPI
- Consultants Reviewed KPI
- Total iQueue Categories KPI
- Quality Score Matrix by Team Leader and Consultant
- Average Quality Score by Team Leader
- Average Quality Score by iQueue Category
- Average Quality Score by Consultant
  
2. Consultants Quality Over Time - Tracks consultant performance trends using:

- Monthly quality score matrix.
- Team Leader → Consultant drill-down hierarchy.
- Conditional formatting using quality thresholds: Performance Level & Score Range
  _🟢 Exceeding	90–100
   🔵 Meeting	85–89.99
   🩷 Approaching	80–84.99
   🔴 Unsatisfactory	<80_

3. Samples Completed Analysis - Analyses quality review workload by:

- Team Leader
- Consultant
- iQueue Category
- Reporting period filters
  
**🎨 Dashboard Features**

- Interactive slicers and filtering
- Cross-page analysis
- Drill-down capability
- Conditional formatting for performance monitoring
- KPI cards
- Clean executive reporting layout

**💻 Tools & Technologies**

Data Visualisation - Power BI Desktop

Data Transformation	- Power Query

Data Modelling - Star Schema

Calculations	- DAX

Data Source -	Microsoft Excel


**🚀 Key Skills Demonstrated**

- Data cleansing and transformation.
- Handling missing and invalid data.
- Data modelling and relationship design.
- Building reusable DAX measures.
- Creating interactive dashboards.
- KPI reporting and performance analytics.
- Translating business requirements into actionable insights.

**📷 Dashboard Preview**

<img width="940" height="517" alt="image" src="https://github.com/user-attachments/assets/693937c9-77c5-4364-939f-d4b9b8f81d24" />

<img width="940" height="540" alt="image" src="https://github.com/user-attachments/assets/574ef1ab-ad25-4e32-b85f-2b2729384e76" />

<img width="940" height="530" alt="image" src="https://github.com/user-attachments/assets/30ece25c-4185-40d5-93c2-13351841eef5" />


**📂 Repository Structure**

Maxxia-Tech-Quality-Dashboard/
│
├── Maxxia Quality Dashboard.pbix
├── README.md
│
└── Images/
    ├── Tech Quality Summary.png
    ├── Consultant Quality Over Time.png
    └── Samples Completed.png
    
**📌 Project Outcome**

Developed a professional Power BI reporting solution that transformed multiple raw quality datasets into an interactive executive dashboard, enabling efficient monitoring of consultant performance, quality trends, and operational workload.

👤 Author

**Pravalika Annem**

Aspiring Data Analyst | Power BI Developer | Reporting Specialist
