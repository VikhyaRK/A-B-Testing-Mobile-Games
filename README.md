# A-B-Testing-Mobile-Games
Here's a brief step-by-step breakdown of what the code does:

*1. Import libraries:*
   - The code starts by importing necessary libraries for data manipulation, visualization, and statistical analysis. These include numpy, pandas, seaborn, matplotlib, os, scipy.stats, and io.

*2. Define functions:*
   - Two functions are defined:
     - load(path, info=True): This function loads data from a CSV or Excel file based on the file extension.
     - AB_Test(dataframe, group, target): This function performs an A/B testing hypothesis test on a given dataframe, considering the specified group and target variable.

*3. Load data:*
   - The code defines the data path (path) and loads the data using the load function.

*4. Exploratory data analysis (EDA):*
   - The code performs some initial EDA tasks:
     - Checks the number of unique users and compares it to the total number of observations to identify potential duplicates.
     - Calculates summary statistics for the "sum_gamerounds" variable to understand the distribution of game rounds played.
     - Creates histograms and boxplots to visualize the distribution of "sum_gamerounds".
     - Plots the time series of "sum_gamerounds" for each A/B group.

*5. Preprocessing:*
   - The code identifies and removes an outlier with an extremely high value in the "sum_gamerounds" variable, considering its potential impact on the analysis.

*6. Further analysis:*
   - The code calculates summary statistics for "sum_gamerounds" after removing the outlier.
   - Creates new visualizations including:
     - A histogram of the overall distribution of "sum_gamerounds".
     - Separate histograms for each A/B group.
     - A boxplot comparing the distribution of "sum_gamerounds" across the groups.
     - Plots of the time series of "sum_gamerounds" for each group again.
   - Analyzes the distribution of users across different game round counts.
   - Finds the number of users who reached specific game levels (30 and 40) for each group.
   - Calculates summary statistics for "sum_gamerounds" grouped by A/B group and user retention status (1-day and 7-day retention).
   - Creates a new variable "Retention" to combine the 1-day and 7-day retention information.
   - Calculates summary statistics for "sum_gamerounds" grouped by A/B group, new retention category, and resets the index for easier interpretation.

*7. A/B testing:*
   - The code defines a new variable "version" to categorize users into groups A ("gate_30") and B ("gate_40").
   - The AB_Test function is applied, considering "version" as the group variable and "sum_gamerounds" as the target variable. The function performs the A/B testing and prints the results, including the test type (parametric or non-parametric), p-value, hypothesis conclusion, and comments on the similarity of the groups.

*8. Additional analysis:*
   - The code calculates the average 1-day and 7-day retention rates for each A/B group.

It's important to note that this is a general overview of the code's functionality, and a deeper understanding of the libraries and statistical concepts involved might be necessary for a complete interpretation of the analysis.
