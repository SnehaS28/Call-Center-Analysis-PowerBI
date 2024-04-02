# PWC Power BI Virtual work experience - Diversity and Inclusion Analysis

## Table of Contents

- [Problem Statement](#ProblemSatement)
- [Data Source](#datasource)
- [Data Preparation](#datapreparation)
- [Data Analysis (DAX)](#DataAnalysis(DAX))
- [Data Visualization Dashboard](#DataVisualizationDashboard)

## Problem Statement :

The purpose of this task is to:

- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

Calculating the following measures could help to define proper KPIs:

- Number of men
- Number of women
- Number of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- % turnover 
- Average performance rating: men
- Average Performance rating: women

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and Diversity and Inclusion dataset:

Dataset:[Call Center Diversity & Inclusion-DataSet](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Diversity-Inclusion-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is given table named:

- `Diversity and Inclusion dataset` which has `500 rows and 31 Column` of observation

Data Cleaning for the dataset was done in the power query editor as follows:
- Changed the header row of dataset
- Replaced  the value is `New hire FY20?` N coverted No and Y converted Yes
- Replaced  the value is `In base group for turnover FY20` N coverted No and Y converted Yes
- Replaced  the value is `Promotion in FY20?` N coverted No and Y converted Yes
- Removed Unnecessary columns 
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Analysis (DAX):

Measures used in  all visualization are:

#Avg Men Rating = CALCULATE(AVERAGE(Pharma[FY20 Performance Rating]),FILTER(Pharma,Pharma[Gender]="Male"))

#Female = CALCULATE(DISTINCTCOUNT(Pharma[Employee ID]),FILTER(Pharma,Pharma[Gender]="Female"))

#male = CALCULATE(DISTINCTCOUNT(Pharma[Employee ID]),FILTER(Pharma,Pharma[Gender]="Male"))

#Promoted FY20 = CALCULATE(COUNT(Pharma[Employee ID]),Pharma[Promotion in FY20?]="Y")+CALCULATE(COUNT(Pharma[Promotion in FY21?]),Pharma[Promotion in FY21?]="Yes")

#Avg Female Rating = CALCULATE(AVERAGE(Pharma[FY20 Performance Rating]),FILTER(Pharma,Pharma[Gender]="Female"))

#Employee Turnover = DIVIDE(Pharma[#Leaver],COUNT(Pharma[Employee ID]),0)

#Leaver = CALCULATE(COUNT(Pharma[FY20 leaver?]), Pharma[FY20 leaver?]="Yes")

% Female = DIVIDE(Pharma[# Female],Pharma[# Female]+Pharma[# male])

% Male = DIVIDE(Pharma[# male],Pharma[# Female]+Pharma[# male])

## Data Visualization:

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard:[View Dashboard](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Diversity%20and%20Inclusion%20Analysis.pdf)
