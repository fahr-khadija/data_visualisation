# Data_visualisation

# Background
You've just joined Pymaceuticals, Inc., a new pharmaceutical company that specializes in anti-cancer medications. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

The executive team has tasked you with generating all of the tables and figures needed for the technical report of the clinical study. They have also asked you for a top-level summary of the study results.
###  code ipynb
##  https://github.com/fahr-khadija/data_visualisation/blob/main/pymaceuticals_starter.ipynb
### Report
##  https://github.com/fahr-khadija/data_visualisation/blob/main/Report.odt
## Table Of Contents 

* ### [*Prepare the data](https://github.com/Fahr-khadija/data_visualisation#Prepare-the-data)
* ### [*Create bar charts and pie charts](https://github.com/Fahr-khadija/data_visualisation#Create-bar-charts-and-pie-charts)
* ### [*Calculate quartiles, find outliers, and create a box plot.](https://github.com/Fahr-khadija/data_visualisation#Calculate-quartiles,-find-outliers,-and-create-a-box-plot.)
* ### [*Create a line plot and a scatter plot](https://github.com/Fahr-khadija/data_visualisation#Create-a-line-plot-and-a-scatter-plot)
* ### [*Calculate correlation and regression](https://github.com/Fahr-khadija/data_visualisation#Calculate-correlation-and-regression)
* ### [*Generate summary statistics](https://github.com/Fahr-khadija/data_visualisation#Generate-summary-statistics)
* ### [*Submit your final analysis](https://github.com/Fahr-khadija/data_visualisation#Submit-your-final-analysis)

## *Prepare the Data
Run the provided package dependency and data imports, and then merge the mouse_metadata and study_results DataFrames into a single DataFrame.
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/carbon%20(1).png))

## *Create bar charts and pie charts

1-Display the number of unique mice IDs in the data,
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/nbr%20of%20mice.png)

and then check for any mouse ID with duplicate time points. 
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/duplicat%20mice.png)
Display the data associated with that mouse ID,
and then create a new DataFrame where this data is removed. 
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/clean%20data.png)

Use this cleaned DataFrame for the remaining steps.
## *Calculate quartiles, find outliers, and create a box plot.
Display the updated number of unique mice IDs.
![image]()
# Checking the number of mice in the clean DataFrame.
num_unique_mice = clean_data['Mouse ID'].nunique()
print("Number of unique mice:", num_unique_mice)

## *Create a line plot and a scatter plot
![image]()
## *Generate summary statistics
Generate Summary Statistics
Create a DataFrame of summary statistics. Remember, there is more than one method to produce the results you're after, so the method you use is less important than the result.
![image]()
## *Calculate correlation and regression
Your summary statistics should include:
![image]()
## *Submit your final analysis
A row for each drug regimen. These regimen names should be contained in the index column.
A column for each of the following statistics: mean, median, variance, standard deviation, and SEM of the tumor volume.
Create Bar Charts and Pie Charts
Generate two bar charts. Both charts should be identical and show the total total number of rows (Mouse ID/Timepoints) for each drug regimen throughout the study.
Create the first bar chart with the Pandas DataFrame.plot() method.
Create the second bar chart with Matplotlib's pyplot methods.
![image]()
Generate two pie charts. Both charts should be identical and show the distribution of female versus male mice in the study.
![image]()
Create the first pie chart with the Pandas DataFrame.plot() method.
![image]()
Create the second pie chart with Matplotlib's pyplot methods.

Calculate Quartiles, Find Outliers, and Create a Box Plot
Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, calculate the quartiles and IQR, and determine if there are any potential outliers across all four treatment regimens. Use the following substeps:

Create a grouped DataFrame that shows the last (greatest) time point for each mouse. Merge this grouped DataFrame with the original cleaned DataFrame.

Create a list that holds the treatment names as well as a second, empty list to hold the tumor volume data.

Loop through each drug in the treatment list, locating the rows in the merged DataFrame that correspond to each treatment. Append the resulting final tumor volumes for each drug to the empty list.
![image]()
Determine outliers by using the upper and lower bounds, and then print the results.
![image]()
Using Matplotlib, generate a box plot that shows the distribution of the final tumor volume for all the mice in each treatment group. Highlight any potential outliers in the plot by changing their color and style.
![image]()
