# Matplotlib Homework - The Power of Plots
# matplotlib-challenge

This is the commit for the matplotlib homework. This took a long time lol

At the top of the pymaceuticals file you will see my observations and insights - the cherry on top of my hours of labor. It is just three analyses of data trends I saw while working through and reviewing the greater analysis.

First steps of the code are to import all dependencies and then create some dataframes. One for the mouse data csv, another for the study results csv, and then combine them.

Next, we return the total number of mice represented (249). 
Then we check if there are any mice whose data was duplicated (there was, one - mouse g989). 
We then create a new dataframe without the duplicate. This df will be referenced frequently.

Now that we have our full, cleaned dataset, we doing some basic mathematical analyses.
We group our data by the drug regimen used and then find:
  mean, median, variance, standard deviation, and standard error of the mean
  for tumor volume, per each regimen
This is done twice, once using a groupby and again using aggregation.

Next we create some graphs.
First is a bar chart, showing the number of timepoints per regimen. 
This is accomplished by grouping the regimen and simply counting the number of timepoints per each.
This graph shows a combination of how many mice and how long each mouse lived. I don't like the analysis, personally, because it's not clear. 
  Capomulin and Ramicane both are the highest, but we don't know if it's because they tested more mice or the mice lived longer.
The bar chart was repeated twice, once using Pandas, the other using pyplot.

Second is a pie chart (again repeated using Pandas and pyplot).
This shows a comparison of the male v. female mice in the study.
It is accomplished by again grouping the data by gender and counting the number of each.
This data could be very useful to show how the regimens affect each gender (if at all), however, that analysis is not done in this assignment.

Third is a box plot. This graph is very comprehensive because it shows a lot of information.
The box plot only includes data from four drug regimens: Capomulin, Ramicane, Infubinol, and Ceftamin
    In order to do this, group our data by individual mouse, find each one's max timepoint, and create a dataframe from this data.
    Next, we create another dataframe that include this "max timepoint" and the other info per each mouse.
    
    Then we loop through this data and accrue our quartile numbers. 
    For each of the four drugs, we find the final tumor volumes of each mouse treated and divide that data into quartiles.
    From there we calculate the lower and upper quartiles, the IQR, lower and upper bounds, and outliers.
    These results are printed by code for viewing.

    Then we generate the box plots all together, showing the final tumor volume data per regimen.


Fourth is a line graph. This graph is based on the data of a single (randomly selected) mouse treated with Capomulin.
To do this, we create a new df using .loc to find all data associated with our mouse (i738).
Then we plot using the 'Timepoint' data and 'Tumor Volume' data. 
Boom, done.


Praise the good Lord, lastly, we create a scatter plot and regression line.
  We create a dataframe for all Capomulin data by using .loc to find where the 'Drug Regimen' = Capomulin.
  Then we find the average tumor volume for each mouse treated and merge that data into our Capomulin dataframe.
  Next, we create one final dataframe that includes only the weight in grams and the avg tumor vol, with no duplicates.
  We set our x and y coordinates to the weight and volume, respectively, and create the scatter plot.

  To find the correlation we use scipy and pearson regression with our previous x and y coordinates.
  We create our linear regression and plot the data.
  To add some last pizzazz, we add the intercept line formula as a string onto the graph.
  
Thank you for reading (or skimming), this was a LOT and I'm proud of how it all turned out! 

fin.



