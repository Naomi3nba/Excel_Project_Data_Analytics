
# Project 2: Skills Analysis in Data Jobs

![analysis1](https://github.com/user-attachments/assets/37348c9e-9f93-46cf-851d-0ae8ed2c2c87)


📁 Dashboard File:
My final dashboard is in: [Skills Analysis in Data Jobs](https://github.com/Naomi3nba/Excel_Project_Data_Analytics/tree/d9fc5b430625762ccaf69aa72c18859615738c02/11_Project%20final_2_Analysis)


## 🔴 Define the Question:

Main Question:

1️⃣ What are the top skills of data professionals?

Secondary Questions:

2️⃣ Do more skills get you better pay, if I pursuing a career in data jobs?

3️⃣ What skill should learn to get better pay?

4️⃣ What’s the pay for the top 10 skills?
  
5️⃣ What’s the median salary for data jobs in different regions, compared to The United States?



## 🖥️ Collect data:

This skill analysis for data jobs was created to help job seekers explore the median salary based on the type of skills they possess in data-related roles.

The data is from a Excel course from Luke Barousse, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, country, and essential skills that are presented here.

The dataset used for this project contains real-world data science job information from 2023 which provides a foundation for analyzing data using Excel. It includes detailed information on:

👨‍💼 Job titles
💰 Salaries
📍 Country
🛠️ Skills


### 🧹 Clean data:

The data analysis process—starting with the very important step of data cleaning and data analize.

For this project, the different formulas and funtions mentioned in detail below were applied using only Excel.

#### 🧮 Formulas and Functions:

1. Funtion: Power Query (ETL)

* Extract

  I first used Power Query to extract the original data (`data_salary_salary.xlsx`) and create two queries:

    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

* Transform and Load

  Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess 
  whitespace.
  
    - 📊 data_jobs_salary
      
![transform data](https://github.com/user-attachments/assets/6aa24cee-a806-40dd-a136-cb527dc05c0c)

   - 🛠️ data_jobs_skills

![transform data skills](https://github.com/user-attachments/assets/b86ee8a8-d76e-49cc-b0e3-250aebdd02db)

2. Funtion: Power Pivot

I created a data model by integrating the *data_jobs_all* and *data_jobs_skills* tables into one model.

Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

Data Model

I created a relationship between my two tables using the job_id column.

![model1](https://github.com/user-attachments/assets/eaed3ede-1a68-4391-9f96-5115336b6421)

![model1 1](https://github.com/user-attachments/assets/12489892-df54-4a95-beb0-1e7d8e8b9899)


### 📈 Analysis data

## 1️⃣ What are the top skills of data professionals?

## 2️⃣ What skill should learn to get better pay?

1. Pivot Table and DAX    

📊 I moved the *job_skills* to the rows area and *skill likelihood (%)* into the values area.

🧮 Then I added new measures in DAX.

- Name: Skill Count Dax
  
  Formula:
```
=COUNT(data_jobs_skills[jobs_skills])

```
- Name: Job Count

  Formula:
```
=DISTINCTCOUNT(data_jobs_salary[job_id])

```
- Name: skill likelihood (%)

  Formula:

```
=DIVIDE([SKILL COUNT DAX],[JOB COUNT])
```
### 📊 Create Visualization:

1. Chart

- Bar Chart for visual comparison of skills.
- Horizontal bar chart for visual comparison of the skills likelihood (%) of each data job. 
- Sorted skills likelihood (%) by descending 
- Added Slices: Title job and country. 

    ![question 2 chart](https://github.com/user-attachments/assets/325b5986-99f7-4182-961c-14b0dfbc9a61)

## 🟢 Conclusion

Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies. 

If I want to work as a Data Analyst in Norway, I should focus on learning Python, Excel, SQL, Go, and Looker. In contrast, if I were seeking a similar role in Mexico, I would prioritize Excel, Tableau, Power BI, and SQL.


## 3️⃣ Do more skills get you better pay, if I pursuing a career in data jobs?

1. Pivot Table and DAX    

📊 I moved the *job_skills* to the rows area and *median salary,  into the values area.

🧮 Then I added new measures in DAX.

- Name: Median Salary
  
  Formula:

```
=MEDIAN(data_jobs_salary[salary_year_avg])
```
- Name: Skill per job
  
  Formula: 
```
=DIVIDE([SKILL COUNT DAX],[JOB COUNT])
```

### 📊 Create Visualization:

 1. Chart

    I used a chart X Y (Scatter) based on Median Salary ($) and the average skill request.

![question 1 chart](https://github.com/user-attachments/assets/49ea8e55-b25f-41cc-bcbc-6c0ceafc6efe)

## 🟢 Conclusion

This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles. 

There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist. 

Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

## 4️⃣ What’s the pay for the top 10 skills?

1. Pivot Table and DAX

📊 I moved the *job_skills* to the rows area, *median salary* and *skill likelihood*, into the values area.

### 📊 Create Visualization:

 2. Chart

    I used a chart combo:
    
    - Median Salary Skills --> Clustered Column
      
    - Skill Likelihood --> Line and Markers (Secundary Axis)
   
    - Slicer: Country and Job Title.

  ![question 4chart](https://github.com/user-attachments/assets/26911268-5794-4f19-80a0-6a5b21b8b725)

## 🟢 Conclusion
    
💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.

📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.


--------------------
## 5️⃣ What’s the median salary for data jobs in different regions, compared to The United States?

### 📈 Clean and Analysis data:

#### 🧮 Formulas and Functions:

Funtion: PivotTables & DAX

🔢 I created a PivotTable using the Data Model I created with Power Pivot.

📊 I moved the job_title_short to the rows area and median salary, median salary USA, median salary non USA, into the values area.

🧮 I added new measure to calculate the median salary for United States jobs and median salary non USA in DAX. 

🧮 Added Slicer: Title Job, Country.

Formula:  Median salary USA

```
=CALCULATE([Median Salary],data_jobs_salary[job_country]="United States")
```
Formula:  Median salary non USA

```
=CALCULATE([Median Salary],data_jobs_salary[job_country]<>"United States")
```

![question 3t](https://github.com/user-attachments/assets/f566d604-1a72-4f0f-8d67-78636259f29c)

## 🟢 Conclusion

💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.

💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

-----------------------------------------





 


--------------------------------------

## Conclusion

As a data enthusiast and former job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
