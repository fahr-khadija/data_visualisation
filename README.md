# Data_visualisation

# Background
You've just joined Pymaceuticals, Inc., a new pharmaceutical company that specializes in anti-cancer medications. Recently, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

As a senior data analyst at the company, you've been given access to the complete data from their most recent animal study. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

The executive team has tasked you with generating all of the tables and figures needed for the technical report of the clinical study. They have also asked you for a top-level summary of the study results.
## Table Of Contents 
### Instructions
     This assignment is broken down into the following tasks:

![image](https://github.com/fahr-khadija/data_visualisation/assets/100168693/92c858a7-7019-4a29-bf2d-d9c75461411a)
<img src="">


* ### [*Prepare the data](https://github.com/Fahr-khadija/data_visualisation#Prepare-the-data)
* ### [*Create bar charts and pie charts](https://github.com/Fahr-khadija/data_visualisation#Create-bar-charts-and-pie-charts)
* ### [*Calculate quartiles, find outliers, and create a box plot.](https://github.com/Fahr-khadija/data_visualisation#Calculate-quartiles,-find-outliers,-and-create-a-box-plot.)
* ### [*Create a line plot and a scatter plot](https://github.com/Fahr-khadija/data_visualisation#Create-a-line-plot-and-a-scatter-plot)
* ### [*Calculate correlation and regression](https://github.com/Fahr-khadija/data_visualisation#Calculate-correlation-and-regression)
* ### [*Generate summary statistics](https://github.com/Fahr-khadija/data_visualisation#Generate-summary-statistics)
* ### [*Submit your final analysis](https://github.com/Fahr-khadija/data_visualisation#Submit-your-final-analysis)

## *Prepare the Data
Run the provided package dependency and data imports, and then merge the mouse_metadata and study_results DataFrames into a single DataFrame.
![image](https://carbon.now.sh/?bg=rgba%2874%2C144%2C226%2C1%29&t=a11y-dark&wt=none&l=auto&width=680&ds=false&dsyoff=20px&dsblur=68px&wc=true&wa=true&pv=56px&ph=56px&ln=false&fl=1&fm=Fira+Code&fs=14px&lh=152%25&si=false&es=2x&wm=false&code=%2523%2520Dependencies%2520and%2520Setup%250Aimport%2520matplotlib.pyplot%2520as%2520plt%250Aimport%2520pandas%2520as%2520pd%250Aimport%2520scipy.stats%2520as%2520st%250A%250A%2523%2520Study%2520data%2520files%250Amouse_metadata_path%2520%253D%2520%2522data%252FMouse_metadata.csv%2522%250Astudy_results_path%2520%253D%2520%2522data%252FStudy_results.csv%2522%250A%250A%2523%2520Read%2520the%2520mouse%2520data%2520and%2520the%2520study%2520results%250Amouse_metadata%2520%253D%2520pd.read_csv%28mouse_metadata_path%29%250Astudy_results%2520%253D%2520pd.read_csv%28study_results_path%29%250A%250A%2523%2520Combine%2520the%2520data%2520into%2520a%2520single%2520DataFrame%250A%250Amerged_data%2520%253D%2520pd.merge%28study_results%252Cmouse_metadata%252C%2520on%253D%2522Mouse%2520ID%2522%29%250A%2523%2520Display%2520the%2520data%2520table%2520for%2520preview%250Amerged_data.head%285%29%2520%250A)

## *Create bar charts and pie charts
Display the number of unique mice IDs in the data, and then check for any mouse ID with duplicate time points. Display the data associated with that mouse ID, and then create a new DataFrame where this data is removed. Use this cleaned DataFrame for the remaining steps.
## *Calculate quartiles, find outliers, and create a box plot.
Display the updated number of unique mice IDs.
## *Create a line plot and a scatter plot
## *Generate summary statistics
Generate Summary Statistics
Create a DataFrame of summary statistics. Remember, there is more than one method to produce the results you're after, so the method you use is less important than the result.
## *Calculate correlation and regression
Your summary statistics should include:
## *Submit your final analysis
A row for each drug regimen. These regimen names should be contained in the index column.

A column for each of the following statistics: mean, median, variance, standard deviation, and SEM of the tumor volume.

Create Bar Charts and Pie Charts
Generate two bar charts. Both charts should be identical and show the total total number of rows (Mouse ID/Timepoints) for each drug regimen throughout the study.

Create the first bar chart with the Pandas DataFrame.plot() method.

Create the second bar chart with Matplotlib's pyplot methods.

Generate two pie charts. Both charts should be identical and show the distribution of female versus male mice in the study.

Create the first pie chart with the Pandas DataFrame.plot() method.

Create the second pie chart with Matplotlib's pyplot methods.

Calculate Quartiles, Find Outliers, and Create a Box Plot
Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, calculate the quartiles and IQR, and determine if there are any potential outliers across all four treatment regimens. Use the following substeps:

Create a grouped DataFrame that shows the last (greatest) time point for each mouse. Merge this grouped DataFrame with the original cleaned DataFrame.

Create a list that holds the treatment names as well as a second, empty list to hold the tumor volume data.

Loop through each drug in the treatment list, locating the rows in the merged DataFrame that correspond to each treatment. Append the resulting final tumor volumes for each drug to the empty list.

Determine outliers by using the upper and lower bounds, and then print the results.

Using Matplotlib, generate a box plot that shows the distribution of the final tumor volume for all the mice in each treatment group. Highlight any potential outliers in the plot by changing their color and style.
