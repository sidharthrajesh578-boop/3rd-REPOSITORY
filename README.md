# 3rd-REPOSITORY
1. Introduction

This assignment involved cleaning, transforming, analysing, and visualising healthcare-related data using Microsoft Excel. Three tables—Customer Names, Medical Examinations, and Hospitalization Details—were processed and combined using Customer ID as the common field. The cleaned data was then analysed using formulas, VLOOKUP, PivotTables, charts, and an interactive dashboard.

2. Data Cleaning
2.1 Checking Missing Values

The Medical Examinations and Hospitalization Details tables were checked for missing values represented by ?. Each column was reviewed to identify incomplete records and determine appropriate methods for handling the missing information.

2.2 Filling Missing Month and Year

The missing values in the month column were replaced with Sep (September).

For the missing year values, the average of the available years was calculated and rounded to the nearest whole number. The resulting rounded average was then used to replace the missing year values.

2.3 Filling Missing Categorical Values

The most frequently occurring value, or mode, was identified for the relevant categorical columns.

The results were:

Smoker: No
Hospital tier: tier - 2
City tier: tier - 2

The missing ? values in these columns were replaced with their respective most frequently occurring values.

2.4 Handling Missing State ID

Missing values in the State ID column were replaced with Unknown. This ensured that every record had a value in the State ID field and prevented missing information from affecting subsequent analysis.

3. Data Transformation
3.1 Splitting Customer Names

The names column in the Customer Names table was separated into three meaningful columns:

Title
First Name
Last Name

This made the customer information easier to use for further analysis.

3.2 Converting Number of Major Surgeries

The NumberOfMajorSurgeries column was converted into numerical data. The text value NO MAJOR SURGERY was replaced with 0, because it represents zero major surgeries.

This allowed the column to be used for numerical calculations and PivotTable analysis.

3.3 Standardising Heart Issues and Smoker

The Heart Issues and smoker columns were checked for inconsistent values. Text values such as yes were standardised to Yes so that values with different capitalisation would be treated consistently during analysis.

3.4 Creating Weight Status

A new column called Weight Status was created using the BMI value.

The categories used were:

BMI	Weight Status
Below 18.5	Underweight
18.5–24.9	Normal Weight
25.0–29.9	Overweight
30.0 and above	Obesity


3.5 Creating Diabetes Status

A new column called Diabetes Status was created using the HbA1C value.

The categories used were:

HbA1C	Diabetes Status
Below 5.7	Normal
5.7–6.4	Prediabetes
6.5 and above	Diabetes

3.6 Creating Date of Birth

The year, month, and date columns from the Hospitalization Details table were combined into a single Date of Birth column.

The date was created using the Excel DATE function and formatted using the custom format:

DD-MMM-YYYY

3.7 Calculating Age

The age of each customer was calculated using their Date of Birth and the dataset collection date of 8 June 2023.

3.8 Formatting Healthcare Charges

The charges column was formatted as Currency ($) so that healthcare expenses were displayed in an appropriate monetary format.

4. Combining the Tables

A new worksheet named Healthcare was created.

The three original tables were combined using Customer ID as the common field. VLOOKUP was used to retrieve the required information from the different tables.

The final Healthcare table contained the following fields:

Customer ID
First Name
BMI
HBA1C
Heart Issues
Any Transplants
Cancer history
NumberOfMajorSurgeries
smoker
Weight Status
Diabetes Status
Date of Birth
charges
Hospital tier
City tier
State ID
Age

For example, VLOOKUP was used to retrieve fields such as BMI, HbA1C, Heart Issues, transplants, cancer history, surgeries, and smoker information based on Customer ID.

5. Data Analysis and Visualization
5.1 Cancer History Among Smokers and Non-Smokers

A PivotTable was created to analyse cancer history according to smoking status.

The PivotTable used:

Rows: smoker
Columns: Cancer history
Values: Count of Customer ID

The results were:

Smoking Status	No Cancer	Cancer
Non-smokers	1,540	307
Smokers	404	84

Separate Donut Charts were created to visually represent the cancer-history distribution among smokers and non-smokers.

5.2 Major Surgeries and HbA1C by Transplant History

A PivotTable was created to compare patients with and without a history of transplantation.

The PivotTable contained:

Rows: Any Transplants
Values: Sum of NumberOfMajorSurgeries
Values: Average of HBA1C

The results were:

Transplant History	Total Major Surgeries	Average HbA1C
No	1,417	6.6704
Yes	162	5.1876

Two charts were created:

Total Major Surgeries by Transplant History
Average HBA1C by Transplant History

These charts made it easier to compare the two groups.

5.3 Healthcare Charges by Weight and Diabetes Status

A PivotTable was created to examine average healthcare charges according to both weight status and diabetes status.

The PivotTable used:

Rows: Weight Status
Columns: Diabetes Status
Values: Average of charges

A Clustered Column Chart was then created with the title:

Average Healthcare Charges by Weight Status and Diabetes Status

This visualization allowed healthcare charges to be compared across different BMI categories and diabetes conditions.

5.4 Average Charges by Hospital Tier and State

Another PivotTable was created to compare average healthcare charges for different hospital tiers across states.

The PivotTable used:

Rows: State ID
Columns: Hospital tier
Values: Average of charges

A Clustered Column Chart was created with the title:

Average Healthcare Charges by Hospital Tier and State

This chart allowed comparisons of average healthcare charges across hospital tiers and states.

6. Correlation Analysis
6.1 Age and BMI

A Scatter Plot was created to investigate the relationship between age and BMI. A linear trendline and R² value were added to the chart.

The R² value was approximately 0.0027, indicating very little linear association between age and BMI in this dataset.

6.2 Age and HbA1C

A second Scatter Plot was created to examine the relationship between age and HbA1C.

The R² value was approximately 0.212, indicating a positive linear association between age and HbA1C in the dataset. The R² value indicates that approximately 21.2% of the variation in HbA1C is represented by the fitted linear relationship with age.

6.3 Age and Healthcare Charges

A Scatter Plot with a linear trendline was created to examine the relationship between age and healthcare charges.

The R² value was approximately 0.093, indicating a relatively weak linear association between age and healthcare charges.

7. Dashboard Creation

An interactive worksheet named Dashboard was created to consolidate the major findings from the analysis.

The dashboard contained the key visualizations created during the analysis, including:

Cancer history among smokers and non-smokers
Total major surgeries by transplant history
Average HbA1C by transplant history
Average healthcare charges by weight and diabetes status
Average healthcare charges by hospital tier and state
Age vs BMI
Age vs HbA1C
Age vs healthcare charges

The charts were arranged on the Dashboard to make the information easier to compare and interpret.

8. Adding Interactive Slicers

Two slicers were added to make the dashboard interactive:

Weight Status
Diabetes Status

The slicers were connected to the relevant PivotTables using Report Connections.

This allows the user to select different weight categories or diabetes conditions and observe the corresponding changes in the connected dashboard visualizations.

For example, selecting a particular Weight Status filters the connected PivotTable-based charts so that the corresponding healthcare information can be compared more easily.
