# PWC Power BI Virtual work experience- Call Centre Performance Report.

## Table of Contents

- [Problem Statement](#ProblemSatement)
- [Data Source](#datasource)
- [Data Preparation](#datapreparation)
- [Data Analysis (DAX)](#DataAnalysis(DAX))
- [Data Visualization Dashboard](#DataVisualizationDashboard)

## Problem Statement :
Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

Possible KPIs include (but are not limited to):

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

## Datasource :

The dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call center dataset:

Dataset: [Call Centre Trends](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Call-Center-Dataset.xlsx)

## Data Preparation:
Completed the Data transformation in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.

Call-Center dataset named:

- `Call Center Analysis` which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table was validated to have the correct data type.
- Changed null values to 0
- Extracted seconds, minutes from avg. talk duration and created a new column named - Duration on Calls

## Data Analysis (DAX):

Measures used in  all visualization are:

- Percentage_call_answered = Divide([Total Call Answered],[Total Calls],0)
- Percentage_call_rejected = DIVIDE([Total Calls Rejected]/[Total Calls],1)
- Total Call Answered = sum('Call Centre Analysis'[Calls Answered])
- Total Calls = COUNT('Call Centre Analysis'[Answered (Y/N)])
- Total Calls Rejected = SUM('Call Centre Analysis'[Calls rejected])


## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: [View Dashboard](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Call%20Center%20Analysis.pdf)

