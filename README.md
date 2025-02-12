# Project 1
Question 4: Effect of seasons on average price of eggs
# Code Source
Jupyter code (Eggs_Season.ipynb) within Main branch
# Question 4:
## Dependencies and Data Clean Up:
Imported all dependencies, added warnings.filterwarnings('ignore'), and function that allows the display of more than one variable in a cell.  

Dataset: Adjusted_Cost_of_Eggs.csv. Cleaned up file.
## Season column created and season_sum_df new DataFrame
Established the Seasons:  

Fall= (September, October, November), Spring= (March, April, May), Summer= (June, July, August), Winter= (December, January, February)  

season_df: season, month, report_begin_date, price_avg, and store_count. Needed to create a average weighted price DataFrame.  

Different price_avg within the dataset hold varying degrees of importance (store_count), allowing more weight to the more significant price_avg values, resulting in a more accurate representation of the overall data.  

season_sum_df DataFrame has the average weighted price by season for analysis.
## Summary Statistics and Mean Bar Chart by Seasons
Generated a summary statistics table of mean, median, variance, standard deviation, and SEM of the weighted price average.  

Generated a bar plot showing the weighted_price mean for each season.  

Analysis can be found in presentation and within Jupyter notebook observations.
## Comparison of seasons versus average weighted price
Calculated the IQR and quantitatively determine if there are any potential outliers.  

Created boxplot grouped by season. Graph can be found in Project 1 folder (Boxplot_grouped_Season.png).  

Performed Analysis on ANOVA. Results can be found in presentation and within Jupyter notebook discussion about the ANOVA.
## Correlation and Regression
Created a scatter plot and regression on relationship between months and weighted_price. Analysis can be found within jupyter notebook discussion about linear relationship.
## References:
United States Department of Agriculture - Agricultural Marketing Service. Report: National Weekly Sell Egg Inventory for 2024.  

Used google for ANOVA analysis, accessed February 2025.
