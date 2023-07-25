# Road-Accidents_Dashboard

![dahboard](https://github.com/Murriel11/Road-Accidents_Dashboard/assets/129143386/14fbbd5d-266b-47f5-9ffb-9753f8f10228)


## Introduction
<ul>
  <li>This project is aimed at developing a Power BI Dashboard for generating insights about road accident data in the United Kingdom.</li>
  <li>The dataset can be accessed from this link:<a href= "https://drive.google.com/drive/folders/1d9OuJpJPRIwnFMr-29HnLldgAGZjGOWP?usp=sharing"> Road Accident Data (UK)</li>
</ul>


## Dashboard Requirements
<ul>
  <li>Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth</li>
  <li>Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth</li>
  <li>Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year</li>
  <li>Monthly Trend showing comparison of Casualties for Current Year and Previous Year</li>
  <li>Casualties by Road Type for Current Year</li>
  <li>Current Year Casualties by Area/Location & Day/Night</li>
  <li>Total Casualties and Total Accident by Location</li>
</ul>


## Installation / Usage
<ul>
  <li>Install Power BI Desktop from Official <a href="https://powerbi.microsoft.com/en-us/downloads/" >Power BI Download Site</li>
  <li>Download data files from link given in Introduction</li>
  <li>Clone/download this repository to your local machine</li>
  <li>Open Dashboard report file (Road Accidents Analysis.pbix) in Power BI Desktop, to access the dashboard's interactivity</li>
</ul>



**1. Total Casualties For Current Year and Year on Year Growth**

(a) Current Year To Date Casualties -- CY Casualties Measure
* `CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])`

(b) Previous Year Casualties -- PY Casualties Measure
* `PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))`

(c) Year on Year Growth of Casualties - YoY Casualties Measure
* `YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]`

**2. Total Accidents for Current Year and Year on Year Growth**

(a) Current Year Accidents Count -- CY Accidents Count Measure
*  `CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])`

(b) Previous Year Accidents Count -- PY Accidents Count Measure
* `PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))`

(c) Year on Year Growth of Accidents - YoY Accidents Measure
* `YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]`
