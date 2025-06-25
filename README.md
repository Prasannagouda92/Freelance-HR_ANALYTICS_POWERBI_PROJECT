HR Analytics Dashboard

Project Title
HR Analytics Dashboard with Power BI


Overview
This interactive HR Analytics Dashboard project is designed to empower HR departments with actionable insights. Built in Power BI, the dashboard visualizes employee data from CSV files to highlight trends in attrition, performance, demographics, and more. Users can dynamically filter, explore, and analyse the workforce through slicers, KPIs, bookmarks, and drill-throughs.


Key Features
•	Employee Attrition Analysis: Monitor terminations by year, department, and reasons.
•	Interactive Demographic Dashboard: Analyze age groups, gender balance, tenure, and diversity.
•	Performance Monitoring: Display average tenure, age, and other key stats.
•	Bookmark Navigation: Switch between views using interactive buttons.
•	Drill-through Filters: Deep dive into gender or department-based segments.
•	Gauge Visual: Compare average employee age vs target age (40).


KPIs Used
•	Total Employees
•	Terminated Employees
•	Active Employees
•	Termination Rate (%)
•	Average Age
•	Average Tenure
•	Gender Diversity Score


Pages in Report
1. Interactive Dashboard (Main Page)
•	KPIs: Total, Terminated, Average Age & Tenure
•	Slicers: Department, Gender, Age Group, Hire Date
•	Visuals:
o	Table: Gender x Department stats
o	Gauge: Avg Age vs Target (Target = 40, Range = 20-60)
o	Bar Chart: Top Termination Reasons
2. Demographics View
•	KPIs: Avg Tenure, Gender Diversity Score
•	Slicers: Gender
•	TreeMap: Employees by Age Group (with gender)
•	Bar Chart: Count of Employees by Age Group
3. Termination Stats
•	KPIs: Total, Terminated, Active, Termination Rate
•	Line Chart: Terminations Over Time
•	Bar Chart: Terminations by Department

Dataset Overview
Main dataset used: hr_data.csv
Column Name	Description
EmployeeID	Unique ID for each employee
Gender	M or F
Age	Age of the employee
Department	Department name
TerminationReason	Why employee left
HireDate	Joining date
TerminationDate	Exit date
Tenure	Years spent at company (calculated)


Key Calculated Columns (DAX)
•	ActiveEmployees = CALCULATE(COUNTROWS(hr_data),hr_data[IsTerminated]=0)
•	Age = DATEDIFF(hr_data[DateOfBirth],TODAY(),YEAR)
•	Average Age = AVERAGE(hr_data[Age])
•	AverageTenure = AVERAGE(hr_data[Tenure])
•	Female Percent = DIVIDE(CALCULATE(COUNT(hr_data[EmployeeID]),hr_data[Gender]="F"),[TotalEmployees])
•	Male Percent = DIVIDE(CALCULATE(COUNT(hr_data[EmployeeID]),hr_data[Gender]="M"),[TotalEmployees])
•	GenderBalanceScore = 
ABS(
    DIVIDE(
        CALCULATE(COUNT(hr_data[EmployeeID]), hr_data[Gender] = "M"), 
        [TotalEmployees]
    ) - 
    DIVIDE(
        CALCULATE(COUNT(hr_data[EmployeeID]), hr_data[Gender] = "F"), 
        [TotalEmployees]
    )
)
•	Tenure = DATEDIFF(hr_data[HireDate],COALESCE(hr_data[TerminationDate],TODAY()),YEAR)
•	TerminatedRate(%) = DIVIDE([TerminatedEmployees],[TotalEmployees])


Deployment Stack
•	Visualization: Power BI Desktop
•	Data Source: CSV (local import)
•	Modeling Tools: Power Query, DAX
•	Interactive Tools: Bookmarks, Slicers, Buttons


Team Contributions 
•	Data Cleaning: Prasanna Gouda
•	Dashboard Design: Prasanna Gouda
•	Interactivity Setup: Prasanna Gouda
•	Final Report & UX: Prasanna Gouda


Timeline
Milestone	Start Date	End Date
Data Preparation	March 1, 2024	March 7, 2024
Dashboard Design	March 8, 2024	March 14, 2024
Data Modeling	March 15, 2024	March 21, 2024
Visual Development	March 22, 2024	March 28, 2024
Final Polish & Review	April 5, 2024	April 10, 2024

How to Use
1.	Open Power BI Desktop.
2.	Load Employee.csv and related datasets.
3.	Follow the page tabs to explore:
o	Interactive Dashboard
o	Termination Insight
o	Demographic Summary
4.	Use filters/buttons to navigate between views.
5.	Analyze, export, or share your insights.
Extras You Can Add
•	Map Visual (if geographic data available)
•	Word Cloud for Termination Reasons
•	Export-to-PDF setup
•	RLS (Row-Level Security) by Region

RESULTS
The HR Analytics Dashboard delivered clear, data-driven insights that significantly enhanced the organization’s understanding of its workforce. Below are the key results observed from the analysis:
 1. Employee Overview
•	Total Employees Analyzed: 311
•	Terminated Employees Identified: 104
•	Active Employees Remaining: 207
•	Overall Termination Rate: 33.44%

 2. Attrition Insights
•	Most terminations occurred in the Production department.
•	The top termination reason was marked as "Another position" and "Unhappy", indicating retention issues.
•	Termination trends peaked around 2015, suggesting need for reviewing past HR practices during that period.

 3. Demographics Analysis
•	Average Age of employees is 46 years, with a target benchmark set at 40.
•	Majority of employees fall under the "under 25" age group.
•	Gender Diversity Score: 0.13, indicating a need to improve female participation in some departments.

4. Tenure & Experience
•	Average Employee Tenure: 11.19 years — reflecting workforce stability but possible lack of new talent inflow.
•	Some departments like IT/IS and Production show higher tenure, hinting at employee satisfaction or lack of growth movement.

5. Interactive Exploration
•	Filters and slicers enabled real-time analysis by gender, department, age group, and hire date.
•	Bookmarks allowed users to toggle between Demographics and Termination views, enhancing usability.


Results & Key Takeaways for Business Growth
1.	Improved Decision-Making
o	HR managers can now identify trends in employee attrition, age, and gender diversity to make proactive decisions.
2.	Attrition Management
o	By understanding top termination reasons and termination trends by department, leadership can reduce turnover and plan retention strategies.
3.	Workforce Planning
o	The dashboard highlights age groups and average tenure, helping in succession planning and future recruitment strategies.
4.	Enhanced Diversity Insights
o	With a Gender Diversity Score and visual breakdowns, the company can track inclusivity goals and meet diversity benchmarks.
5.	Performance Monitoring
o	Managers can filter by department, age group, or gender to monitor employee performance and satisfaction, helping improve engagement.
6.	Cost Optimization
o	Identifying departments with high attrition or low tenure enables budget realignment in hiring, training, or engagement efforts.
7.	Interactive Data Exploration
o	The use of bookmarks and drill-through reports gives HR teams the ability to dig deeper into data, promoting a data-driven culture.
8.	Real-Time Strategy Tuning
o	The slicers and filters allow real-time changes in views — making the dashboard a dynamic tool for strategy adjustment.
9.	Department-Specific Focus
o	HR can compare department-wise data to address department-specific issues and balance workforce distribution.
10.	Foundation for Predictive Analytics
•	The insights lay the groundwork for future integration of machine learning models to predict attrition, performance drops, etc.


Project Completed With: Power BI | DAX | CSV Data | Advanced Visuals | Interactivity
