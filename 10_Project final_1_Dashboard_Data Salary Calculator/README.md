# Excel Data Salary Dashboard

![DASHBOARD](https://github.com/user-attachments/assets/202b1652-df14-4165-8bce-733aa09b4359)

### 📁 Dashboard File:
My final dashboard is in [Data Salary Calculator.xlsx](https://github.com/Naomi3nba/Excel_Project_Data_Analytics/tree/e7bf63012c9d2d240ba3779c8f030a3a6c8f2840/10_Project%20final_1_Dashboard_Data%20Salary%20Calculator)

## 🔴 Define the Question: 

Main Question:

**How can I make an informed decision about pursuing a career in the data field based on median salary, country, and job type?**

Secondary Questions:

- What is the average salary for different data-related positions by country?
- What are the most common job type (full-time, remote) for these roles?
- Which platforms are most commonly used to find data-related jobs?
- How many data-jobs postings were available in 2023 by country?

## 🖥️ Collect data:

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data is from a Excel course from Luke Barousse, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

The dataset used for this project contains real-world data science job information from 2023 which provides a foundation for analyzing data using Excel. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**
  
## 📈 Clean and Analize data:

The data analysis process—starting with the very important step of data cleaning and data analize. 

For this project, the different formulas and funtions mentioned in detail below were applied using only Excel.

### 🧮 Formulas and Functions

#### ⏰ Count of Job Schedule Type

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

Background Table

![tabla2](https://github.com/user-attachments/assets/bea73739-5a4b-4deb-abbc-87eec121fbaf)


#### 💰 Median Salary by Job Titles

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```
Background Table

![tabla](https://github.com/user-attachments/assets/63c67fc9-b0fe-4541-8589-a0bf743220d2)

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option.

![data validation](https://github.com/user-attachments/assets/6220df34-bbd7-44ff-9912-f01996760a89)
##Create Visualization: 


## 📊 Create Visualization:

### 📉 Charts

📊 Data Science Job Salaries: 

- Bar Chart for visual comparison of median salaries.
- Horizontal bar chart for visual comparison of median salaries.
- Sorted job titles by descending salary for improved readability.

🗺️ Country Median Salaries: Map Chart
 
- Map Chart plotted median salary for each country with available data
- Color-coded map to visually differentiate salary levels across regions.
  
![charts](https://github.com/user-attachments/assets/0154a3a5-63fd-458c-bb23-5556bf45e180)


## Conclusion

This dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
