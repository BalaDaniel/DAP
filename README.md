# Patient_Waiting_Time_Analysis
This project is about the average and total waiting time by inpatient and outpatient using PowerBI

**Resources Used**
1. Inpatient and Outpatient data from 2018 to 2021
2. PowerBI Desktop

## Methodology
1. First I changed the date format which in text type to date type format in excel, otherwise it won't change data type in powerbi.
2. Then I load the Inpatient and Outpatient data from my local machine.
3. Then I replaced some repetitive values in the same column by one standard value in power query editor by replace value.
4. Appended the inpatient data table and outpatient data table
5. Established the relationship between tables and used star schema model.
6. Then wrote the DAX functions to derive the insights

## DAX functions Used
1. Latest Month Wait List, this function is used to find the total wait list in the latest in the given dataset.
   Latest_Month_wait_List= CALCULATE(SUM(All_Data[Total]),All_Data[Date]=MAX(All_Data[Date]))
2. Previous Year Latest Month Waut List, this function is used to find the total wait list of this month in the previous year.
PY_Latest_Month_Wait_List = CALCULATE(SUM(All_Data[Total]),All_Data[Date]=EDATE(MAX(All_Data[Date]),-12))
3. Average Wait List, this function is used to find the total average wait list of the total patients.
4. Median Wait List, this function s used to find the median value of the total wait list in the given dataset, if there is any outliers present.
5. Avg/Medain Wait List, this function is used to switch between the average and median vlaue of the waiting list
Avg/Median_Wait_List = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average",[Avg_Wait_List],"Median",[Median_Wait_List])

## Visualizations
1. Card visuals for Latest Month Wait List and PY Latest Month Wait List
2. Doughnut chart for average or median wait list by case type
3. Clustered column chart for average or median wait list by time band and age profile.
4. Multi card visualization for top 5 specialities in the average wait time
5. Line charts for total wait time by date and case type


