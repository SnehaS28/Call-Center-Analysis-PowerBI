# PWC Power BI Virtual work experience- Call Centre Churn Analysis.

## Table of Contents

- [Problem Statement](#ProblemSatement)
- [Data Source](#datasource)
- [Data Preparation](#datapreparation)
- [Data Analysis (DAX)](#DataAnalysis(DAX))
- [Data Visualization Dashboard](#DataVisualizationDashboard)

## Problem Statement :
The purpose of this task is to:

- Define proper KPI's
- Create a dashboard for the retention manager reflecting the KPI's
- Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
- Customers who left within the last month
- Services each customer has signed up for phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
- Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges, and number of tickets opened in the categories administrative and technical
- Demographic info about customers – gender, age range, and if they have partners and dependents purpose of this task is to:


## Datasource :

The dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and customer churn Retention dataset:

Dataset: [Call Center Churn-DataSet](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Churn-Dataset.xlsx)

## Data Preparation:
Completed the Data transformation in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modeling.

 Customer Churn dataset named:

- `Customer churn dataset` which has `23 columns and 7043 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each column in the table was validated to have the correct data type.
-  Added New column name Tenure(in years) using M formula-
  = Table.AddColumn(#"Changed Type", "Tenure (in years)", each if [tenure] <= 12 then "<1 Year" else if [tenure] <= 24 then "<2 Year" else if [tenure] <= 36 then "<3 Year" else if [tenure] <= 48 then "<4 Year" else if [tenure] <= 60 then "<5 Year" else if [tenure] <= 72 then "<6 Year" else if [tenure] <= 84 then "<7 Year" else null)

## Data Analysis (DAX):

Measures used in  all visualization are:

- % Churn Rate = DIVIDE(CALCULATE(COUNT(churn[Churn]), churn[Churn] = "yes" ),COUNT (churn[Churn]), 0)
- % Device protection = DIVIDE(CALCULATE(COUNT(churn[DeviceProtection]), churn[DeviceProtection]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[DeviceProtection]),churn[Churn]="Yes"),0)
- % NO-Multiple lines = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="No", churn[Churn]="Yes"),CALCULATE(COUNT(churn[MultipleLines]),churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)
- % of Dependents = DIVIDE(CALCULATE(COUNT(Churn[Dependents]),Churn[Dependents]="Yes",Churn[Churn]="Yes"),CALCULATE(COUNT(Churn[Dependents]),Churn[Churn]="Yes"),0)
- % of Partner = DIVIDE(CALCULATE(COUNT(Churn[Partner]),Churn[Partner]="Yes",Churn[Churn]="Yes"),CALCULATE(COUNT(Churn[Partner]),Churn[Churn]="Yes"),0)
- % of Senior Citizen = DIVIDE(CALCULATE(COUNT(Churn[SeniorCitizen]),Churn[SeniorCitizen]=1,Churn[Churn]="Yes"), CALCULATE(COUNT(Churn[SeniorCitizen]),Churn[Churn]="Yes"),0)
- % Online Backup = DIVIDE(CALCULATE(COUNT(churn[OnlineBackup]), churn[OnlineBackup]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[OnlineBackup]),churn[Churn]="Yes"),0)
- % Online Sec. = DIVIDE(CALCULATE(COUNT(churn[OnlineSecurity]), churn[OnlineSecurity]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[OnlineSecurity]),churn[Churn]="Yes"),0)
- % Phone Service = DIVIDE(CALCULATE(COUNT(churn[PhoneService]), churn[PhoneService]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[PhoneService]),churn[Churn]="Yes"),0)
- % Streaming Movies = DIVIDE(CALCULATE(COUNT(churn[StreamingMovies]), churn[StreamingMovies]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[StreamingMovies]),churn[Churn]="Yes"),0)
- % Streaming TV = DIVIDE(CALCULATE(COUNT(churn[StreamingTV]), churn[StreamingTV]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[StreamingTV]),churn[Churn]="Yes"),0)
- % Tech Support = DIVIDE(CALCULATE(COUNT(churn[TechSupport]), churn[TechSupport]="Yes", churn[Churn]="Yes"),CALCULATE(COUNT(churn[TechSupport]),churn[Churn]="Yes"),0)
- % Yes-Multiple Lines = DIVIDE(CALCULATE(COUNT(churn[MultipleLines]), churn[MultipleLines]="Yes", churn[Churn]= "Yes"), CALCULATE(COUNT(churn[MultipleLines]), churn[Churn]="Yes", churn[MultipleLines] <> "No phone service"),0)
- Churn Count = CALCULATE(COUNT(Churn[Churn]),Churn[Churn]="Yes")

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: [View Dashboard](https://github.com/SnehaS28/Data-Simulation-Project/blob/main/Churn%20Data%20Analysis.pdf)

