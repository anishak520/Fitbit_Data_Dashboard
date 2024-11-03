# Fitbit_Data_Dashboard
portfolio project based on fitbit data showcases skills using HTML, CSS, JavaScript and SQL for data manipulation.
## Daily Activity Analysis
### Project Overview
This project aims to analyze daily activity data to explore trends, patterns, and correlations between various metrics, such as steps, calories burned, and activity levels. Using linear regression, visualizations, and descriptive statistics, we uncover insights about user activity, including identifying trends in active minutes and calorie burn, and exploring potential correlations among activity types.

### Dataset
The dataset used in this project (daily_activity_df) contains daily activity data for multiple users, with fields like total steps, active minutes (very active, fairly active, lightly active, and sedentary), and calories burned. The data is grouped by unique user IDs, with each row representing one day's worth of data for a specific user.

### Files and Code Structure
The data used in this project and contained in the CSV files in /Data_CSV come from https://www.kaggle.com/datasets/arashnic/fitbit. The data are published under the CC0: Public Domain license. 

Server: This directory contains the database (fitness_db.sqlite) and the notebook used to populate it. It also includes the code for running the Flask server.

Graph Files: This directory holds the graph.png files illustrating data from the data exploration.

data_exploration.ipynb: A Jupyter notebook used for preliminary data exploration, analysis, and visualization.

### Analysis Steps
##### 1. Data Preprocessing and Transformation

Merging Data: We combine multiple data points (steps, active minutes, distances, and activity days) for each user to create a comprehensive DataFrame with daily averages.
Calculating Percentages: For each activity level (very active, fairly active, lightly active, sedentary), we calculate the percentage of total daily activity.
##### 2. Descriptive Statistics and Initial Plots
Activity Analysis: We calculate and visualize the average daily metrics (steps, calories, active minutes) per user.
Correlations: Using linear regression, we explore potential correlations between:
TotalSteps and Calories
TotalDistance and Calories
VeryActiveMinutes, FairlyActiveMinutes, and Calories
##### 3. Linear Regression
We utilize a helper function perform_regression to perform linear regression on various metrics. This function calculates the slope, intercept, and correlation strength (Pearson r-value), and generates a plot with the regression line.

##### 4. User-Specific Analysis
For selected "interesting" users, we generate visualizations showing daily trends in steps, calories, and activity minutes to provide more personalized insights.

### Code Explanation
Linear Regression Function
The perform_regression function handles linear regression calculations and plots the data with a regression line. This function outputs the regression equation and interprets the correlation strength based on the r-value.

### User-Specific Analysis
For each selected user, we generate scatter plots of daily steps, calories, and active minutes, along with a combined plot for TotalSteps vs Calories. This helps to analyze individual trends.


### Running the Code
Prepare the Dataset: Ensure that the dataset (daily_activity_df) is loaded correctly as a DataFrame.

Run the Analysis: Execute main.py or the individual code cells in Jupyter Notebook (if applicable).

Interpret the Results: View the printed regression models, correlation strengths, and the generated plots to understand the relationships between different metrics.

Correlation Analysis: Each linear regression model will output the equation and Pearson r-value for the metrics being compared.

Plots: Scatter plots with regression lines and bar charts summarizing activity metrics for each user.

## Key Findings
Activity Variability: Users exhibit a wide range of activity levels, which can be seen in the spread of TotalSteps, Calories, and active minutes.
Calorie Burn and Steps: While there is some correlation between steps and calorie burn, other factors like active minutes and distance may also play a significant role.
User-Specific Patterns: For selected users, we observed unique trends in activity and calorie burn, potentially providing insights into daily habits.

## Next Steps
Future work could include:

Additional Data Exploration: Exploring correlations with other metrics such as heart rate or sleep data.
Improved Modeling: Implementing machine learning models to predict calories based on activity levels and other factors.
Time Series Analysis: Analyzing trends over time for each user to identify patterns or seasonal trends.