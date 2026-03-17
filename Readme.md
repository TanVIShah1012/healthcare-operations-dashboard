Healthcare Operations Dashboard
An end-to-end analytics project simulating an outpatient clinic environment to analyze scheduling workflows, provider utilization, and billing lifecycle metrics.

Project Overview
This project models a real-world healthcare operations workflow using a synthetically generated dataset of 3,000 outpatient appointments across 5 departments and 10 providers. The goal was to surface operational inefficiencies through KPI analysis and structured reporting — the kind of work that supports BI implementation in clinical environments.
Key Finding


Cardiology and Orthopedics averaged 35+ minute wait times — more than 20% above the clinic average of 26 minutes. This pattern was completely invisible in the overall average and only surfaced after breaking down performance by department.


Project Structure
healthcare-operations-dashboard/
│
├── appointments.csv                  # Synthetic dataset (3,000 rows)
├── Healthcare_Operations_Dashboard.xlsx  # Excel dashboard with KPIs
├── generate_data.py                  # Python script to generate dataset
└── README.md

Dashboard Sheets
SheetDescriptionRaw Data3,000 simulated appointments with scheduling, billing, and claim fieldsKPI Dashboard8 operational KPIs benchmarked against industry targetsDepartment SummaryDepartment-level breakdown with flagged outliersProvider UtilizationPivot table showing completion rate per provider

KPIs Calculated
KPIValueBenchmarkTotal Appointments3,000—Completion Rate61.2%>65%No-Show Rate19.7%<15%Avg Wait Time (Overall)26.4 mins<25 minsAvg Wait — Cardiology35.3 mins<25 mins Avg Wait — Orthopedics35.4 mins<25 mins Avg Claim Turnaround18.0 days<20 daysClaim Denial Rate19.7%<15%Total Billing Revenue$822,488—

Tools Used

Python — synthetic data generation (pandas, numpy, datetime)
Excel — KPI analysis using COUNTIFS, AVERAGEIFS, SUMIFS, and Pivot Tables
GitHub — version control and project documentation


Dataset Schema
ColumnDescriptionAppointment_IDUnique identifier (APT0001 format)Appointment_DateDate in 2024DepartmentOne of 5 clinical departmentsProviderAssigned doctorAppointment_TypeNew Patient / Follow-Up / Annual Checkup / Urgent CareScheduled_HourHour of day (8am–5pm)Slot_Duration_Mins30 or 45 minutes depending on typeWait_Time_MinsSimulated wait time (higher for Cardiology & Orthopedics)StatusCompleted / No-Show / CancelledBilling_AmountRevenue for completed appointmentsClaim_StatusPaid / Pending / DeniedClaim_Turnaround_DaysDays to process claim (completed only)

How to Reproduce
1. Clone the repo
bashgit clone https://github.com/yourusername/healthcare-operations-dashboard.git
cd healthcare-operations-dashboard
2. Generate the dataset
bashpip install pandas numpy
python generate_data.py
This creates appointments.csv with 3,000 rows.
3. Open the dashboard
Open Healthcare_Operations_Dashboard.xlsx in Excel. All KPI formulas reference the Raw Data sheet and will recalculate automatically.

Insights & Recommendations

Cardiology and Orthopedics require scheduling review — wait times are consistently 35+ minutes vs a 26-minute clinic average
No-show rate of 19.7% exceeds the 15% benchmark across all departments — appointment reminder workflows should be evaluated
Claim denial rate of 19.7% suggests billing documentation or coding issues worth investigating
Dr. Wilson has the lowest provider utilization at 55.2% — capacity reallocation may be warranted
