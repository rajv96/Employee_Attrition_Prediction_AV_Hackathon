# Employee_Attrition_Prediction_Analytics_Vidhya_Hackathon

## Problem Statement

You are working as a data scientist with HR Department of a large insurance company focused on sales team attrition. Insurance sales teams help insurance companies generate new business by contacting potential customers and selling one or more types of insurance. The department generally sees high attrition and thus staffing becomes a crucial aspect.

To aid staffing, you are provided with the monthly information for a segment of employees for 2016 and 2017 and tasked to predict whether a current employee will be leaving the organization in the upcoming two quarters (01 Jan 2018 - 01 July 2018) or not, given:

1. Demographics of the employee (city, age, gender etc.)
2. Tenure information (joining date, Last Date)
3. Historical data regarding the performance of the employee (Quarterly rating, Monthly business acquired, designation, salary)

## Approach

The target variable was not explicitly mentioned in the problem statement. However, the last working date of the employee as an attribute was given.
I did some basic exploratory analysis, built some plot which explored the relationships between the features.
Later, I realized that the last working date column had 92% missing data and then it struck me that I could use this column as my target variable. 
Feature Engineering was the key part here. I created a new column as “days_active” which was the difference between the reporting date and joining date of an employee. This could tell me how long the employee was associated with the company.
I made the last working date as the target column by considering the entries with missing data to be such that the employee hadn’t left the organization (0) and the entries having a date to be such that the employee had indeed left the organization. This was the tricky part to come up with.

I used random forest and XGBoost to build my model. XGBoost yielded a better score with respect to random forest algorithm.
Another tricky part was to get the data of the employee id’s mentioned in the test data. For this, I merged the 2 dataframes (i.e train and test) on emp_id column by using inner join.

