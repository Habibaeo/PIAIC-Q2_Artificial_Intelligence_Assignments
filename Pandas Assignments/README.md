	THIS ASSIGNMENT IS CONSIST OF TWO PARTS 

STEPS TO FOLLOW : 

1) Open a jupyter notebook file and load all the required csvs for corresponding tasks.
2) Complete all the tasks given below for each part.

3) Upload your jupyter notebook on github.

4) Submit your github link on the provided googleform link.

Google Form Link To Submit Your Assignment : https://forms.gle/cYuiw693hn76CL5y6

PART 

1: 

HOW TO CLEAN DATA WITH PYTHON
Cleaning US Census Data

You just got hired as a Data Analyst at the Census Bureau, 
which collects census data and creates interesting visualizations and insights from it.


The person who had your job before you left you all the data they had for the most recent census. 
It is in multiple csv files. They didn’t use pandas, they would just look through these csv files manually whenever they wanted to find something. 
Sometimes they would copy and paste certain numbers into Excel to make charts.


The thought of it makes you shiver. This is not scalable or repeatable.


Your boss wants you to make some scatterplots and histograms by the end of the day. 
Can you get this data into pandas and into reasonable shape so that you can make these histograms?




Inspect the Data!

1.
The first visualization your boss wants you to make is a scatterplot that shows average income in a state vs proportion of women in that state.


Open some of the census csv files in the navigator. How are they named? What kind of information do they hold? Will they help us make this graph?


2.
It will be easier to inspect this data once we have it in a DataFrame. You can’t even call .head() on these csvs! 
How are you supposed to read them?

Using glob, loop through the census files available and load them into DataFrames. 
Then, concatenate all of those DataFrames together into one DataFrame, called something like us_census.



3.
Look at the .columns and the .dtypes of the us_census DataFrame.
Are those datatypes going to hinder you as you try to make histograms?


4.
Look at the .head() of the DataFrame so that you can understand why some of these dtypes are objects instead of integers or floats.


Start to make a plan for how to convert these columns into the right types for manipulation.

Regex to the Rescue

5.
Use regex to turn the Income column into a format that is ready for conversion into a numerical type.



6.
Look at the GenderPop column. We are going to want to separate this into two columns, the Men column, and the Women column.


Split the column into those two new columns using str.split and separating out those results.


7.
Convert both of the columns into numerical datatypes.

There is still an M or an F character in each entry! We should remove those before we convert.



8.
Now you should have the columns you need to make the graph and make sure your boss does not slam a ruler angrily on your desk 
because you’ve wasted your whole day cleaning your data with no results to show!


Use matplotlib to make a scatterplot!

plt.scatter(the_women_column, the_income_column) 
Remember to call plt.show() to see the graph!


9.
Did you get an error? These monstrous csv files probably have nan values in them! 
Print out your column with the number of women per state to see.

We can fill in those nans by using pandas’ .fillna() function.


You have the TotalPop per state, and you have the Men per state. 
As an estimate for the nan values in the Women column, you could use the TotalPop of that state minus the Men for that state.


Print out the Women column after filling the nan values to see if it worked!

10.
We forgot to check for duplicates! 
Use .duplicated() on your census DataFrame to see if we have duplicate rows in there.


11.
Drop those duplicates using the .drop_duplicates() function.



12.
Make the scatterplot again. Now, it should be perfect! Your job is secure, for now.

Histograms of Races

13.
Now, your boss wants you to make a bunch of histograms out of the race data that you have. Look at the .columns again to see what the race categories are.


14.
Try to make a histogram for each one!

You will have to get the columns into numerical format, and those percentage signs will have to go.


Don’t forget to fill the nan values with something that makes sense! 
You probably dropped the duplicate rows when making your last graph, but it couldn’t hurt to check for duplicates again.

Get Creative

15.
Phew. You’ve definitely impressed your boss on your first day of work.


But is there a way you really convey the power of pandas and Python over the drudgery of csv and Excel?


Try to make some more interesting graphs to show your boss, and the world! 
You may need to clean the data even more to do it, or the cleaning you have already done may give you the ease of manipulation you’ve been searching for.



PART 2:

LEARN DATA ANALYSIS WITH PANDAS 
Petal Power Inventory

You’re the lead data analyst for a chain of gardening stores called Petal Power. Help them analyze their inventory!


Answer Customer Emails

1.
Data for all of the locations of Petal Power is in the file inventory.csv. Load the data into a DataFrame called inventory.


2.
Inspect the first 10 rows of inventory.


3.
The first 10 rows represent data from your Staten Island location. Select these rows and save them to staten_island.


4.
A customer just emailed you asking what products are sold at your Staten Island location. 
Select the column product_description from staten_island and save it to the variable product_request.


5.
Another customer emails to ask what types of seeds are sold at the Brooklyn location.


Select all rows where location is equal to Brooklyn and product_type is equal to seeds and save them to the variable seed_request



Inventory

6.
Add a column to inventory called in_stock which is True if quantity is greater than 0 and False if quantity equals 0.


7.
Petal Power wants to know how valuable their current inventory is.

Create a column called total_value that is equal to price multiplied by quantity.


8.
The Marketing department wants a complete description of each product for their catalog.


The following lambda function combines product_type and product_description into a single 
string:

combine_lambda = lambda row: \
'{} - {}'.format(row.product_type,
row.product_description)
Paste this function into script.py.


9.
Using combine_lambda, create a new column in inventory called full_description that has the complete description of each product.
