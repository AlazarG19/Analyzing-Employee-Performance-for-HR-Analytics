---
jupyter:
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.10.6
  nbformat: 4
  nbformat_minor: 5
---

::: {#3c8f7734 .cell .markdown}
# Analyzing Employee Performance for HR Analytics Using Python and MySQL

This project undertakes a thorough examination of real-world
employee-related data. This project intends to evaluate the provided
dataset, solve business problems on this dataset and mine information
Insights

In the face of escalating volume of data pertaining to employees and
their contributions across diverse organization functions, there arises
a critical imperative to leverage the combined power of Python and SQL
for a meticulous exploration and analysis.
:::

::: {#99fc6e77 .cell .markdown}
## Objectives

### Data Retrieval

Retrieve the World Bank Loan dataset from the data_worldbank.csv file
that is stored in csv format

### Data Cleaning

Cleaning the dataset to address missing,inconsistent,duplicate data

### Data Prepartion and Column Transformation

Preparing dataset for analysis by removing any unnecessary columns and
renaming some columns to improve calrity and consistency.

### Data Conversion and Export

Converting different colummns to their appropriate format

### Importing Data to Database and Creating Database Connection

Importing data to sql inorder to make the analysis.

### Trend Analysis

Identifying and analysing trends in World Bank Loan Distribution over
time and exploring patterins in loan allocation across different regions
and sectors
:::

::: {#eee677a6 .cell .markdown}
## Dataset

The dataset ,containing real-world data, provides a detailed overview of
employee-related data. With a focus on HR analytics, this dataset
encompasses a range of critical information related to employees. The
dataset is structured with the following columns.

### employee_id

A unique identifier assigned to each employee. It serves as a distinct
label to differentiate one employee from another.

### department

Indicates the specific department or functional area within the
organization where the employee is assigned.

### region

Denotes the geographical or organizational region where the employee\'s
workplace is located.

### education

Represents the highest level of education attained by the employee.
Common categories might include \"Below Secondary,\" \"Secondary (High
School),\" \"Bachelor\'s,\" \"Master\'s,\" or other relevant educational
qualifications.

### gender

Specifies the gender of the employee, typically categorized as \"Male\"
or \"Female.\"

### recruitment_channel

Describes the channel through which the employee was recruited into the
organization. Common channels include \"Direct\" (hired directly by the
company), \"Referral\" (recommended by existing employees), or \"Other\"
(recruited through external agencies).

### no_of_trainings

Indicates the number of training programs or courses the employee has
participated in. This could provide insights into the employee\'s
commitment to continuous learning and development.

### age

Represents the age of the employee. Age can be a relevant factor in
workforce planning, career development, and succession planning.

### previous_year_rating

Reflects the performance rating or evaluation assigned to the employee
in the previous year. Ratings are often on a numerical or categorical
scale and provide a measure of the employee\'s past performance.

### length_of_service

Signifies the total duration of an employee\'s service or tenure with
the organization. It is a valuable metric for understanding the level of
experience and commitment an employee brings to their role.

### KPIs_met_more_than_80

Binary indicator (1 or 0) that denotes whether the employee has met Key
Performance Indicators (KPIs) by more than 80%. KPIs are specific,
measurable goals set by the organization to assess performance.

### awards_won

Binary indicator (1 or 0) that signifies whether the employee has won
any awards or recognition for exceptional performance.

### avg_training_score

Represents the average score achieved by the employee in various
training programs. It offers insights into the employee\'s aptitude for
learning and skill development.
:::

::: {#43e5024c .cell .markdown}
## Tools

We\'ll be using the the library pandas from the python function to
facilitate data manipulation and perform inital assessment of the
dataset\'s strucutre. Once that is complete We\'ll be using mysql to
formulate SQL queries to extract relevant information for trend
analysis.
:::

::: {#39099403 .cell .markdown}
## Approach

### Data Import and Initial Exploration

In data analysis, the initial step of importing a dataset and exploring
its initial content is akin to opening a door to valuable insights.
:::

::: {#2abb148f .cell .markdown}
### Identifying Duplicate Data

In this step, we aim to identify and quantify the presence of duplicate
data within our dataset.
:::

::: {#afaae744 .cell .markdown}
### Removing Duplicate Data

In this step, we are removing duplicate data from our dataset by
utilizing the drop_duplicates function with the inplace=True parameter.
Duplicate data can introduce noise and inaccuracies into our analysis,
and removing them ensures that we work with unique and non-repetitive
records
:::

::: {#c682f05f .cell .markdown}
### Identifying Missing Data¶

Here, we\'re examining our dataset for missing values, indicated by
\'null\' values. The \'null_values\' variable holds the count of missing
data points for each column. Identifying and quantifying missing data is
crucial as it helps us understand the completeness of our dataset.
:::

::: {#c312c91a .cell .markdown}
### Handling Missing Data

In this step, we\'re addressing missing data in specific columns, namely
\'Education\' and \'previous_year_rating.\' We use the dropna function
with the subset parameter to remove rows with missing values in these
columns, setting inplace=True. Handling missing data is crucial to
maintain data integrity and accuracy in our analysis. By removing rows
with missing values in these specific columns, we ensure that the
dataset remains reliable and complete for our subsequent analysis.
:::

::: {#f3b21932 .cell .markdown}
### Data Preparation and Column Transformation

In this step, we are preparing the dataset for analysis. We remove
unnecessary columns and rename some columns to improve clarity and
consistency. We notice that the \"region\" column contains inconsistent
data. We extract the numeric part of the string and convert the result
to numeric values. This ensures that the dataset is optimized for our
analysis, making it more concise and easier to work with in the next
stages of our project.
:::

::: {#7a2003ea .cell .markdown}
### Data Conversion and Export {#data-conversion-and-export}

We export the cleaned dataset to a CSV file for future use and verify
the data types to ensure they are in the correct format.
:::

::: {#a6864f57 .cell .markdown}
## Trend Analysis {#trend-analysis}

Once we\'ve prepared our data, we\'ll use sql to analyse any patterns
within the data

Data Import and Database Connection We\'ll start by loading sql
libraries and connecting to the sql. In order to load the data we\'ll
have to use MySQLWorkbench. we\'ll first login into our Local instance.
Once that is complete, we\'ll have to create a new schema to hold our
new table. after the schema is created, use the table data import wizard
to load the data into the csv. During the import, MYSQL Workbench will
prompt the data type of each dataset. During this process, select the
appropriate data types such as datetime , double , string to the needed
attributes.
:::

::: {#d21d1cbd .cell .markdown}
### Creating the Database Connection

in the next step we create our database connection using the pymysql
library
:::

::: {#5c7225af .cell .markdown}
### Asking questions to uncover patterns

We start our analysis by asking questions relevant to the topic

#### Q1 Find the average age of employees in each department and gender group. ( Round average age up to two decimal places if needed). {#q1-find-the-average-age-of-employees-in-each-department-and-gender-group--round-average-age-up-to-two-decimal-places-if-needed}

This Questions Let\'s as have an insight in what the most typical age
for each department and gender is
:::

::: {#9da59f07 .cell .markdown}
#### Q2 List the top 3 departments with the highest average training scores. ( Round average scores up to two decimal places if needed) {#q2-list-the-top-3-departments-with-the-highest-average-training-scores--round-average-scores-up-to-two-decimal-places-if-needed}

Finding the top 3 departments with the highest average training scores
let\'s us know which departments have the best typical score
:::

::: {#7abc5446 .cell .markdown}
#### Q3 Find the percentage of employees who have won awards in each region. (Round percentages up to two decimal places if needed) {#q3-find-the-percentage-of-employees-who-have-won-awards-in-each-region-round-percentages-up-to-two-decimal-places-if-needed}

By answering this question, we can identify how much part of the
employees are rewarded and which are not which let\'s us know which
region has rewarded achievers
:::

::: {#00c4f061 .cell .markdown}
#### Q4 Show the number of employees who have met more than 80% of KPIs for each recruitment channel and education level. {#q4-show-the-number-of-employees-who-have-met-more-than-80-of-kpis-for-each-recruitment-channel-and-education-level}

This leads us to the answer of how many employees have met their
performance level based on what recruitment channel and education lever.
This lets us know whether or not recruitment channel and education level
have an impact on the productivity of employees
:::

::: {#28b9e413 .cell .markdown}
#### Q5 Find the average length of service for employees in each department, considering only employees with previous year ratings greater than or equal to 4. ( Round average length up to two decimal places if needed) {#q5-find-the-average-length-of-service-for-employees-in-each-department-considering-only-employees-with-previous-year-ratings-greater-than-or-equal-to-4--round-average-length-up-to-two-decimal-places-if-needed}

Answering this will let us know what is the typical amount of time an
employee ,who has been rated as a great empoyee, has stayed in the
company. This lets us know the retention in high performers, and let;s
us know which individuals have made long-tem contributions to the
organizaiton.
:::

::: {#5b2d683d .cell .markdown}
#### Q6 List the top 5 regions with the highest average previous year ratings. ( Round average ratings up to two decimal places if needed) {#q6-list-the-top-5-regions-with-the-highest-average-previous-year-ratings--round-average-ratings-up-to-two-decimal-places-if-needed}

This questions leads us to the answer of ,at average,what regions have
employees with higher previous year ratings, leading us to compare
performance between different regions, identify which regions contain
high performing individuals
:::

::: {#f300020f .cell .markdown}
#### Q7 List the departments with more than 100 employees having a length of service greater than 5 years. {#q7-list-the-departments-with-more-than-100-employees-having-a-length-of-service-greater-than-5-years}

This lets us identify departments with long-term employees. Whether or
not departmenets have stable work force with employees who have been
with the organization fro an extended period. Identifying departments
with a substantial number of long-serving employees can provide insights
.
:::

::: {#61a1d710 .cell .markdown}
#### Q8 Show the average length of service for employees who have attended more than 3 training, grouped by department and gender. ( Round average length up to two decimal places if needed) {#q8-show-the-average-length-of-service-for-employees-who-have-attended-more-than-3-training-grouped-by-department-and-gender--round-average-length-up-to-two-decimal-places-if-needed}

Answerting this let\'s us know whether or not training has an impact on
employee retention, since the result is grouped by department, identify
whether or not department specific training has relationship with
average length of service
:::

::: {#f1f2d344 .cell .markdown}
#### Q9 Find the percentage of female employees who have won awards, per department. Also show the number of female employees who won awards and total female employees. ( Round percentage up to two decimal places if needed) {#q9-find-the-percentage-of-female-employees-who-have-won-awards-per-department-also-show-the-number-of-female-employees-who-won-awards-and-total-female-employees--round-percentage-up-to-two-decimal-places-if-needed}

This leads us to recognize and apply places where gender equality is
needed and the effectiveness of awards programs.
:::

::: {#2d603750 .cell .markdown}
#### Q10 Calculate the percentage of employees per department who have a length of service between 5 and 10 years. ( Round percentage up to two decimal places if needed) {#q10-calculate-the-percentage-of-employees-per-department-who-have-a-length-of-service-between-5-and-10-years--round-percentage-up-to-two-decimal-places-if-needed}

This questions leads us to know whether a company is effectively
retaining employees within the 5-10 years of service range.
:::

::: {#f9e2d181 .cell .markdown}
#### Q11 Find the top 3 regions with the highest number of employees who have met more than 80% of their KPIs and received at least one award, grouped by department and region. {#q11-find-the-top-3-regions-with-the-highest-number-of-employees-who-have-met-more-than-80-of-their-kpis-and-received-at-least-one-award-grouped-by-department-and-region}

Answering this lets us know which department have the most productive
employees who have been awarded
:::

::: {#0d9dd1a5 .cell .markdown}
#### Q12 Calculate the average length of service for employees per education level and gender, considering only those employees who have completed more than 2 trainings and have an average training score greater than 75 ( Round average length up to two decimal places if needed) {#q12-calculate-the-average-length-of-service-for-employees-per-education-level-and-gender-considering-only-those-employees-who-have-completed-more-than-2-trainings-and-have-an-average-training-score-greater-than-75--round-average-length-up-to-two-decimal-places-if-needed}

this lets us discover whether or not education level and gender have any
effect on the length of service. In addition we want to know whether or
not people who have been well trained are staying within the company or
not.
:::

::: {#ef91857c .cell .markdown}
#### Q13 For each department and recruitment channel, find the total number of employees who have met more than 80% of their KPIs, have a previous_year_rating of 5, and have a length of service greater than 10 years. {#q13-for-each-department-and-recruitment-channel-find-the-total-number-of-employees-who-have-met-more-than-80-of-their-kpis-have-a-previous_year_rating-of-5-and-have-a-length-of-service-greater-than-10-years}

This questions lets us know from which department and recruitment
channel does the most effective employee that has stayed the longest in
the industry resides
:::

::: {#ee6042fe .cell .markdown}
#### Q14 Calculate the percentage of employees in each department who have received awards, have a previous_year_rating of 4 or 5, and an average training score above 70, grouped by department and gender ( Round percentage up to two decimal places if needed). {#q14-calculate-the-percentage-of-employees-in-each-department-who-have-received-awards-have-a-previous_year_rating-of-4-or-5-and-an-average-training-score-above-70-grouped-by-department-and-gender--round-percentage-up-to-two-decimal-places-if-needed}

this question helps us discover the relation ship between hig
performance and average training score in addition to know the
distribution of awards by gender within each department
:::

::: {#ec8c6034 .cell .markdown}
#### Q15 List the top 5 recruitment channels with the highest average length of service for employees who have met more than 80% of their KPIs, have a previous_year_rating of 5, and an age between 25 and 45 years, grouped by department and recruitment channel. ( Round average length up to two decimal places if needed {#q15-list-the-top-5-recruitment-channels-with-the-highest-average-length-of-service-for-employees-who-have-met-more-than-80-of-their-kpis-have-a-previous_year_rating-of-5-and-an-age-between-25-and-45-years-grouped-by-department-and-recruitment-channel--round-average-length-up-to-two-decimal-places-if-needed}

Using this question, we can identify the most effective recruitment
channels to get well performing employees who are middle aged and
typicall stay very long within the company
:::

## Visualizing the data
Visualizing this data is crucial for several reasons:

__Interactive Exploration__

Power BI offers interactive dashboards and reports that allow users to explore the data dynamically. With just a few clicks, stakeholders can drill down into specific regions, projects, or time periods to uncover insights and trends.

__Comprehensive Analysis__

Power BI provides a wide range of visualization options, including charts, graphs, maps, and tables. These visualizations allow analysts to conduct comprehensive analyses of the Employee's performance data

__Storytelling__

Power BI enables users to create compelling data stories by combining visualizations, text, and images into interactive presentations. This storytelling approach helps convey key insights and recommendations to stakeholders in a clear and engaging manner.