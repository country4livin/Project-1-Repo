Project 1 - Egg Price Change Analysis and Bird Flu Outbreaks

Question 1: How has the cost of eggs changed in a 6-year period?
Code Source: Jupyter notebook:  5-yr_cost_of_eggs.ipynb
Data input: “Resources/5_year_eggs.csv”
United States Department of Agriculture - Agricultural Marketing Service. 
Report: National Weekly Sell Egg Inventory for 2024
Output: “Resources/output_data”
Contains 4 .jpg files generated from the code. 
Line graph, bar graph, box plot, and scatter plot
Processing: Jupyter Notebook 5-yr_cost_of_eggs.ipynb
Data intake and clean up: 
Read csv file and create a dataframe. 
Filter the data to National and Shell Eggs. Drop no-reporting stores and unnecessary columns. 
Calculated a weighted average for each category in the dataset  
Created the dataframe weighted_usda
Separate the month and year for reporting
Converted the date to datetime 
Separated the month and year columns
Calculated the weighted average for each month
Set year and month as the index
Concatenate the year and month into 1 column
Reset the column index.
Created a line graph to compare month to month changes
Created a data analytics summary table
Calculated the mean, median, variance, std dev, and sem
Did not calculate the mode since we are working from averages there is not way to determine the most frequent raw datapoint.
Created a bar graph, which I ultimately didn’t use in the slides
Created a box and whisker plot to compare the percentiles over time
Combined the 6-year dataset with Kelley Blue’s bird flu data in a scatter plot to see if there is a correlation.



Question 2: Are spikes in the cost of eggs localized to a specific region?
Code source
jupyter notebook, “RegionalAnalysis.ipynb”
Data input
“Resources/USDA_Eggs_2024.csv”
United States Department of Agriculture - Agricultural Marketing Service. 
Report: National Weekly Sell Egg Inventory for 2024
Output
“Output_files/AnnualAvgPricesByRegionBar.png”
“Output_files/WeeklyPricesByRegionLine.png”
“Output_files/MonthlyPricesByRegionBar.png”
Processing
Data intake and cleanup
Read in csv file and create dataframe
Select fields needed for calculation and reporting
Filter out data not needed for analysis (limit to only shell egg data)
Reformat Date data
Clean up Region data
Calculate total price (store count * average price) on each row to be used for weighted average prices
General processing by Level (Annual by Region, Weekly by Region, Monthly by Region)
Sum avg price by Level
Extract National data into separate dataset for overlay (if needed)
Exclude National data from plotting dataset
Create pivot for plotting multiple datasets (if needed)
Create graph for Level and send image to Output_files folder
Analysis
Summary analysis and graphs included in presentation document
Detailed analysis available in jupyter notebook, “RegionalAnalysis.ipynb”




Question 3: 
# Code Source
Jupyter code (Enviro.ipynb) within Main branch

## Analysis: 
Added complete analysis to top of Jupyter Notebook. Dollar signs are not included as the notebook was trying to format based off the dollar sign locations. 

## Dependencies and Read CSV:
Imported all dependencies and read in data CSV file. 

Dataset: USDA_Eggs_2024.csv. 
##Weighted Avg. Price
Some duplicate columns with different average prices based on store count to get to average price; weighted the average to combine duplicate rows to clean up file. 

## Filtered Down Environment
Removed non-relevant columns, keeping the date of the report, environment (either specifically USDA Organic or Conventional), and average price. 

##Converted Data to Monthly
Found average price per environment per month by finding average price per environment using weekly data and finding average per month.

## Summary Statistics and Monthly Line Chart by Environment:
Generated a line chart that shows the average monthly price per environment over 2024. The green line shows the organic price; the blue line indicates the conventional price. Added a title, axis labels, and legend. 

Analysis can be found in presentation and within Jupyter notebook observations.
## Statistical Analysis
Calculated the min, max, and mean per environment in order to see statistical data and more accurately analyze results. 

## References:
United States Department of Agriculture - Agricultural Marketing Service. Report: National Weekly Sell Egg Inventory for 2024.  


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




#Question 5: Have there been spikes in Bird Flu that correspond with the spikes in the cost of eggs? 
##Code source: jupyter notebook, “Project 1 Bird Flu 2.ipynb”
##Data input: “Project 1/Resources/commercial-backyard-flocks.csv” from CDC
##Output: “National Map.png”, “National Outbreak.png”
##Processing
###Data intake from CDC
###Read in csv file and create dataframe
###Filter for Table Egg Layers needed for analysis
###Combine flock sizes for rows with the same date
###Assign Outbreak date as index and sort by ascending date
###Create graph to shows the outbreaks across the Nation
###Utilize GeoApify to pull latitude and longitude coordinates for each county to create a holoviews map plot to show the outbreaks and identify clusters
###Save images
###Pull data from each region for every year to do a yearly comparison and where this year ranks so far per region and as a whole
##Analysis: Analysis and graphs included in presentation document as well as at the top in jupyter notebook, “Project 1 Bird Flu 2.ipynb”
##Correlation to Egg Prices: Create a graph with both egg prices and bird flu outbreaks to visualize the correlation. Egg prices remained fairly consistent until the first reported outbreak in 2022, which is when egg prices began to become more volatile.
