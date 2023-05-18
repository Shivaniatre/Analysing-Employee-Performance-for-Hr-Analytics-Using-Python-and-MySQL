# Analysing-Employee-Performance-for-Hr-Analytics-Using-Python-and-MySQL

    ****    Module 1  ****
Step 1: Removing duplicate rows.

Step 2: Removing rows for which numeric columns are having irrelevant data type values

Step 3: Remove irrelevant values from each column if any. Validation all values for a column, Check for any inconsistencies or discrepancies in data types, units, or formats.Feel free to add more validation checks which you might feel necessary for the dataset’s integrity

Step 4: Export the cleaned dataset as a .csv file: prefer UTF-8 encoding.

Step 5: Convert the pre-processed dataset into an SQL file. 

Step 6: Manually generate a table by utilizing the database information provided in the "Database Info" tab.

    
**#Import the Libraray**
import pandas as pd
import numpy as np

**#Load the Dataset**
DB = pd.read_csv("/content/Uncleaned_employees_final_dataset.csv")

**#View the Data  First 5 rows of data**
DB.head()

**# Last 5 rows of data**
DB.tail()

**#View the Shape**
DB.shape

**#Information prints the column header and the data type stored in each column**
DB.info()

**#To check Datatype**
DB.dtypes

**#Count the number of datapoints**
DB.count()

**#Identifying dupliacte rows**
DB.duplicated().sum()

**#Remove the duplicate row**
DB.drop_duplicates(keep =False)

**#Checking Missing values**
DB.isnull().sum()

#**To remove duplicates rows from coulmns**
DB = DB.dropna(subset = ['education'])
DB = DB.dropna(subset =['previous_year_rating'])
DB.info()   // to view the structure of DataFrame

#**Save the data**
from google.colab import files
DB.to_csv('Cleaned_Employee_data.csv', encoding = 'utf-8', index = False)
open('Cleaned_Employee_data.csv', mode='r', encoding='utf-8').read()
#download the new clean data
files.download('Cleaned_Employee_data.csv')

****************************************************************************************************************************************************************************************
         ****    Module 2  ****

**Project Description**

In this module, you will be working on performing data analysis on the pre-processed data from the previous module and conducting Data Analysis using SQL. 
You will generate queries for given problem statements. 

1.List the top 3 departments with the highest average training scores. ( Round average scores up to two decimal places if needed)

2.Find the average age of employees in each department and gender group. (Round average age up to two decimal places if needed).

3.Find the percentage of employees who have won awards in each region. (Round percentages up to two decimal places if needed)

4.Show the number of employees who have met more than 80% of KPIs for each recruitment channel and education level.

5.Find the average length of service for employees in each department, considering only employees with previous year ratings greater than or equal to 4. ( Round average length up to two decimal places if needed)

6.List the top 5 regions with the highest average previous year ratings. ( Round average ratings up to two decimal places if needed)

7.List the departments with more than 100 employees having a length of service greater than 5 years.

8.Show the average length of service for employees who have attended more than 3 trainings, grouped by department and gender. ( Round average length up to two decimal places if needed)

9.Find the percentage of female employees who have won awards, per department. Also show the number of female employees who won awards and total female employees. ( Round percentage up to two decimal places if needed)

10.Calculate the percentage of employees per department who have a length of service between 5 and 10 years. ( Round percentage up to two decimal places if needed)

11.Find the top 3 regions with the highest number of employees who have met more than 80% of their KPIs and received at least one award, grouped by department and region.

12.Calculate the average length of service for employees per education level and gender, considering only those employees who have completed more than 2 trainings and have an average training score greater than 75 ( Round average length up to two decimal places if needed)

13.For each department and recruitment channel, find the total number of employees who have met more than 80% of their KPIs, have a previous_year_rating of 5, and have a length of service greater than 10 years.

14.Calculate the percentage of employees in each department who have received awards, have a previous_year_rating of 4 or 5, and an average training score above 70, grouped by department and gender ( Round percentage up to two decimal places if needed).



15.List the top 5 recruitment channels with the highest average length of service for employees who have met more than 80% of their KPIs, have a previous_year_rating of 5, and an age between 25 and 45 years, grouped by department and recruitment channel. ( Round average length up to two decimal places if needed).

***********************************************************************************************************************************************************************************************************************
 






