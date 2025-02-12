Project 1 \- Egg Price Change Analysis and Bird Flu Outbreaks

## Question 1: How has the cost of eggs changed in a 6-year period?

Code Source: Jupyter notebook:  5-yr\_cost\_of\_eggs.ipynb  
Data input: “Resources/5\_year\_eggs.csv”

- United States Department of Agriculture \- Agricultural Marketing Service.   
- Report: National Weekly Sell Egg Inventory for 2024

Output: “Resources/output\_data”

- Contains 4 .jpg files generated from the code.   
- Line graph, bar graph, box plot, and scatter plot

Processing: Jupyter Notebook 5-yr\_cost\_of\_eggs.ipynb

1. Data intake and clean up:   
   1. Read csv file and create a dataframe.   
   2. Filter the data to National and Shell Eggs. Drop no-reporting stores and unnecessary columns.   
   3. Calculated a weighted average for each category in the dataset    
   4. Created the dataframe weighted\_usda  
2. Separate the month and year for reporting  
   1. Converted the date to datetime   
   2. Separated the month and year columns  
   3. Calculated the weighted average for each month  
3. Set year and month as the index  
   1. Concatenate the year and month into 1 column  
   2. Reset the column index.  
4. Created a line graph to compare month to month changes  
5. Created a data analytics summary table  
   1. Calculated the mean, median, variance, std dev, and sem  
   2. Did not calculate the mode since we are working from averages there is not way to determine the most frequent raw datapoint.  
6. Created a bar graph, which I ultimately didn’t use in the slides  
7. Created a box and whisker plot to compare the percentiles over time  
8. Combined the 6-year dataset with Kelley Blue’s bird flu data in a scatter plot to see if there is a correlation.

Question 2: Are spikes in the cost of eggs localized to a specific region?

1. Code source  
   1. jupyter notebook, “RegionalAnalysis.ipynb”  
2. Data input  
   1. “Resources/USDA\_Eggs\_2024.csv”  
      1. United States Department of Agriculture \- Agricultural Marketing Service.   
      2. Report: National Weekly Sell Egg Inventory for 2024  
3. Output  
   1. “Output\_files/AnnualAvgPricesByRegionBar.png”  
   2. “Output\_files/WeeklyPricesByRegionLine.png”  
   3. “Output\_files/MonthlyPricesByRegionBar.png”  
4. Processing  
   1. Data intake and cleanup  
      1. Read in csv file and create dataframe  
      2. Select fields needed for calculation and reporting  
      3. Filter out data not needed for analysis (limit to only shell egg data)  
      4. Reformat Date data  
      5. Clean up Region data  
      6. Calculate total price (store count \* average price) on each row to be used for weighted average prices  
   2. General processing by Level (Annual by Region, Weekly by Region, Monthly by Region)  
      1. Sum avg price by Level  
      2. Extract National data into separate dataset for overlay (if needed)  
      3. Exclude National data from plotting dataset  
      4. Create pivot for plotting multiple datasets (if needed)  
      5. Create graph for Level and send image to Output\_files folder  
5. Analysis  
   1. Summary analysis and graphs included in presentation document  
   2. Detailed analysis available in jupyter notebook, “RegionalAnalysis.ipynb”

Question 3:   
\# Code Source  
Jupyter code (Enviro.ipynb) within Main branch

\#\# Analysis:   
Added complete analysis to top of Jupyter Notebook. Dollar signs are not included as the notebook was trying to format based off the dollar sign locations. 

\#\# Dependencies and Read CSV:  
Imported all dependencies and read in data CSV file. 

Dataset: USDA\_Eggs\_2024.csv.   
\#\#Weighted Avg. Price  
Some duplicate columns with different average prices based on store count to get to average price; weighted the average to combine duplicate rows to clean up file. 

\#\# Filtered Down Environment  
Removed non-relevant columns, keeping the date of the report, environment (either specifically USDA Organic or Conventional), and average price. 

\#\#Converted Data to Monthly  
Found average price per environment per month by finding average price per environment using weekly data and finding average per month.

\#\# Summary Statistics and Monthly Line Chart by Environment:  
Generated a line chart that shows the average monthly price per environment over 2024\. The green line shows the organic price; the blue line indicates the conventional price. Added a title, axis labels, and legend. 

Analysis can be found in presentation and within Jupyter notebook observations.  
\#\# Statistical Analysis  
Calculated the min, max, and mean per environment in order to see statistical data and more accurately analyze results. 

\#\# References:  
United States Department of Agriculture \- Agricultural Marketing Service. Report: National Weekly Sell Egg Inventory for 2024\.  

Question 4: Effect of seasons on average price of eggs  
\# Code Source  
Jupyter code (Eggs\_Season.ipynb) within Main branch  
\# Question 4:  
\#\# Dependencies and Data Clean Up:  
Imported all dependencies, added warnings.filterwarnings('ignore'), and function that allows the display of more than one variable in a cell.  

Dataset: Adjusted\_Cost\_of\_Eggs.csv. Cleaned up file.  
\#\# Season column created and season\_sum\_df new DataFrame  
Established the Seasons:  

Fall= (September, October, November), Spring= (March, April, May), Summer= (June, July, August), Winter= (December, January, February)  

season\_df: season, month, report\_begin\_date, price\_avg, and store\_count. Needed to create a average weighted price DataFrame.  

Different price\_avg within the dataset hold varying degrees of importance (store\_count), allowing more weight to the more significant price\_avg values, resulting in a more accurate representation of the overall data.  

season\_sum\_df DataFrame has the average weighted price by season for analysis.  
\#\# Summary Statistics and Mean Bar Chart by Seasons  
Generated a summary statistics table of mean, median, variance, standard deviation, and SEM of the weighted price average.  

Generated a bar plot showing the weighted\_price mean for each season.  

Analysis can be found in presentation and within Jupyter notebook observations.  
\#\# Comparison of seasons versus average weighted price  
Calculated the IQR and quantitatively determine if there are any potential outliers.  

Created boxplot grouped by season. Graph can be found in Project 1 folder (Boxplot\_grouped\_Season.png).  

Performed Analysis on ANOVA. Results can be found in presentation and within Jupyter notebook discussion about the ANOVA.  
\#\# Correlation and Regression  
Created a scatter plot and regression on relationship between months and weighted\_price. Analysis can be found within jupyter notebook discussion about linear relationship.  
\#\# References:  
United States Department of Agriculture \- Agricultural Marketing Service. Report: National Weekly Sell Egg Inventory for 2024\.  

Used google for ANOVA analysis, accessed February 2025\.

\#Question 5: Have there been spikes in Bird Flu that correspond with the spikes in the cost of eggs?   
\#\#Code source: jupyter notebook, “Project 1 Bird Flu 2.ipynb”  
\#\#Data input: “Project 1/Resources/commercial-backyard-flocks.csv” from CDC  
\#\#Output: “National Map.png”, “National Outbreak.png”  
\#\#Processing  
\#\#\#Data intake from CDC  
\#\#\#Read in csv file and create dataframe  
\#\#\#Filter for Table Egg Layers needed for analysis  
\#\#\#Combine flock sizes for rows with the same date  
\#\#\#Assign Outbreak date as index and sort by ascending date  
\#\#\#Create graph to shows the outbreaks across the Nation  
\#\#\#Utilize GeoApify to pull latitude and longitude coordinates for each county to create a holoviews map plot to show the outbreaks and identify clusters  
\#\#\#Save images  
\#\#\#Pull data from each region for every year to do a yearly comparison and where this year ranks so far per region and as a whole  
\#\#Analysis: Analysis and graphs included in presentation document as well as at the top in jupyter notebook, “Project 1 Bird Flu 2.ipynb”  
\#\#Correlation to Egg Prices: Create a graph with both egg prices and bird flu outbreaks to visualize the correlation. Egg prices remained fairly consistent until the first reported outbreak in 2022, which is when egg prices began to become more volatile.
