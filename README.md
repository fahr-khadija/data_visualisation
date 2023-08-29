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
```
# Generate a bar plot showing the total number of rows (Mouse ID/Timepoints) for each drug regimen using Pandas.
# Group data by drug regimen and count the number of rows in each group
regimen_counts = clean_data['Drug Regimen'].value_counts()
# Create a bar plot using Pandas
regimen_counts.plot(kind='bar', color='skyblue', alpha=0.7)
# Set plot labels and title
plt.xlabel('Drug Regimen')
plt.ylabel('Number of Rows')
plt.title('Total Number of Rows for Each Drug Regimen')
# Rotate x-axis labels for better readability
plt.xticks(rotation=90)
# Display the plot
plt.show()

```
and then check for any mouse ID with duplicate time points. 
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/duplicat%20mice.png)
Display the data associated with that mouse ID,
and then create a new DataFrame where this data is removed. 
![image](https://github.com/fahr-khadija/data_visualisation/blob/main/clean%20data.png)

Use this cleaned DataFrame for the remaining steps.
## *Calculate quartiles, find outliers, and create a box plot.
```
# Calculate the final tumor volume of each mouse across four of the treatment regimens:  
# Capomulin, Ramicane, Infubinol, and Ceftamin
# List of treatment regimens 
treatment_regimens = ['Capomulin', 'Ramicane', 'Infubinol', 'Ceftamin']
# Start by getting the last (greatest) timepoint for each mouse
last_timepoint = clean_data.groupby("Mouse ID")["Timepoint"].max()
last_timepoint_df = last_timepoint.reset_index()
# Merge this group df with the original DataFrame to get the tumor volume at the last timepoint
merged_last_timepoint = pd.merge(last_timepoint_df, clean_data, on=["Mouse ID", "Timepoint"])

```

# Checking the number of mice in the clean DataFrame.
```

```

## *Create a line plot and a scatter plot
```
# Put treatments into a list for for loop (and later for plot labels)
treatments = ["Capomulin", "Ramicane", "Infubinol", "Ceftamin"]
# Create empty list to fill with tumor vol data (for plotting)
tumor_volumes = []
# Calculate the IQR and quantitatively determine if there are any potential outliers. 
  # Locate the rows which contain mice on each drug and get the tumor volumes
for treatment in treatments:
    volumes = merged_last_timepoint.loc[merged_last_timepoint["Drug Regimen"] == treatment, "Tumor Volume (mm3)"]
    tumor_volumes.append(volumes)
for i, treatment in enumerate(treatments):
    quartiles = tumor_volumes[i].quantile([0.25, 0.5, 0.75])
    lower_q = quartiles[0.25]
    upper_q = quartiles[0.75]
    iqr = upper_q - lower_q
   # Determine outliers using upper and lower bounds
    lower_bound = lower_q - 1.5 * iqr
    upper_bound = upper_q + 1.5 * iqr
    outliers = tumor_volumes[i][(tumor_volumes[i] < lower_bound) | (tumor_volumes[i] > upper_bound)]
    print(f"{treatment}'s potential outliers: {outliers}")    
 
```

## *Calculate correlation and regression
Your summary statistics should include:
```
# Calculate the correlation coefficient and a linear regression model 
# for mouse weight and average observed tumor volume for the entire Capomulin regimen
plt.scatter(mouse_weights, average_tumor_volume, marker='o', label='Data Points')
regression_line = slope * mouse_weights + intercept
plt.plot(mouse_weights, regression_line, color='red', label='Linear Regression')
plt.title('Mouse Weight vs. Average Tumor Volume (Capomulin)')
plt.xlabel('Mouse Weight (g)')
plt.ylabel('Average Tumor Volume (mm3)')
plt.legend()
plt.grid(True)
plt.show()
```

## *Submit your final analysis
### Report
##  https://github.com/fahr-khadija/data_visualisation/blob/main/Report.odt

