# FDE LAB 2 — Building a Basic ETL Data Pipeline Using Python



Course: Foundations of Data Engineering (FDE)

Author: Maanya Praveen

USN:1RVU23CSE244



### 🎯 Objective



This lab provides hands-on experience in building a Basic ETL (Extract, Transform, Load) data pipeline using Python.

The goal is to simulate real-world data engineering workflows — from extracting messy raw data, transforming it into a usable format, loading it into a target system, and deriving actionable business insights.

Additionally, this exercise demonstrates collaboration across data engineers, analysts, and machine learning engineers to build a data-driven solution.



### 🧠 Outcomes



* By the end of this lab, you will be able to:



* Identify and describe the stages of the data engineering lifecycle.



* Explain the roles and responsibilities of different stakeholders (Data Engineer, Data Analyst, Business Analyst, ML Engineer).



* Perform data ingestion, cleansing, transformation, and loading using Python.



* Collaborate across simulated roles to design and implement a data-driven solution.



* Apply a reverse ETL process after customer classification using machine learning.



### 🧰 Materials Used



* sales\_data\_raw.csv → Raw sales data with missing values and inconsistent formats.
* customer\_feedback.json → Customer sentiment data from another source.
* A mock data warehouse (folder structure for storing cleaned and processed data).
* Python libraries:

&nbsp;	pandas

&nbsp;	numpy

&nbsp;	matplotlib

&nbsp;	scikit-learn

* json

### 

### ⚙️ Lab Procedure

##### Stage 1: Problem Definition and Requirements Gathering (Business Analyst)



Reviewed sales\_data\_raw.csv and customer\_feedback.json.



Business Question:

“What are the top 5 products by revenue in the last quarter, and how does customer sentiment vary for these products?”



Identified required data points:

product\_id, sale\_price, sale\_date, customer\_id, sentiment\_score



Created a simple requirements document summarizing the problem and desired outcome.



##### Stage 2: Data Ingestion and Cleansing (Data Engineer)



1.Ingestion:

&nbsp;  Read data from CSV and JSON files using pandas.



2.Cleansing:

* Handled missing values by imputation or row removal.
* Corrected data types (e.g., sale\_price as float).
* Standardized date formats.
* 

3.Transformation:



* Computed total\_revenue = quantity \* sale\_price.
* Joined sales and feedback data on a common key (product\_id).



4.Loading:

* Stored the cleaned and transformed dataset as
* processed\_sales\_data.csv in the data\_warehouse folder.



##### Stage 3: Data Analysis (Data Analyst)





* Loaded the processed\_sales\_data.csv file.



* Grouped data by product\_id and summed total\_revenue.



* Calculated average sentiment\_score for each top product.



* Visualized results using a bar chart (matplotlib).



* Identified potential data quality issues for feedback to the engineering team.



Output:

A table or bar chart showing Top 5 Products by Revenue and Average Sentiment Score.



##### Stage 4: Reporting and Insights (Business Analyst)



* Interpretation Example:

“Product X generated the highest revenue but had below-average sentiment.

This may indicate customer dissatisfaction despite strong sales — suggesting a need for quality improvement or better customer support.”



* Deliverable:

A concise final report summarizing:



* The business question



* Data insights



* Actionable recommendations

##### 

##### Stage 5: Customer Classification (ML Engineer Task)



Objective:

To classify VIP customers based on purchasing behavior and update the dataset using a reverse ETL process.



Steps:



1. Feature Selection:

&nbsp;	Extracted features: customer\_id, total\_purchase\_amount, purchase\_frequency, avg\_transaction\_value.



2\. Preprocessing:



* Handled missing values
* Normalized features using StandardScaler



3\. Modeling:



* Used K-Means Clustering to segment customers or Logistic Regression for binary VIP classification.
* Labelled customers as “VIP” or “Non-VIP”.



4\.Reverse ETL:



* Added a new column vip\_status to the dataset.
* Exported the enriched dataset (enriched\_sales\_data.csv) to the mock CRM or data warehouse for business use.
