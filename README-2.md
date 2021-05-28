# DATA ANALYSIS ON ALL THREE MAJOR BRANCHES OF  COMPANY XYZ ACROSS THE COUNTRY.


## PROJECT DESCRIPTION:

    The kernel of this project is to run a deep data analysis on Company XYZ which owns a supermarket chain across the country, with each major branch located in 3 major cities namely Abuja, Lagos and Port Harcourt. 
    
    the analysis is based on recorded 3-month sales information. this analysis is to anable XYZ understand its growth trajectory, identify productivity loop holes to abate growth bottlenecks.

# Project Steps


### LOADING DATA SETS
- I imported *pandas* as pd and *datetime* as dt to enable me work with pandas DataFrame and Datetime data type.



- The goal is to run analysis on all the recoreds at once, so i opend the datasets download from the forked project from github as instructed and assing each of them to a variable. 



- I imported other variables such as numpy to handle mathematical evaluation, seaborn which is a visualization library, matplotlib.pyplot bacause seaborn is based on it, and warning to ignore warning prompts.



- I started the main work by first concatenating the variable in which the three records from the the major branches of XYZ were asigned to from the very start into one variable (**main_list**).


### Data exploration


- I ran main_list.head() to see the first 4 rows of the compiled data sets, starting from the top, to get an idea of what my dataset looks lik.



- I ran main_list.shape to see the shape of my dataset and the result was (1000, 17) meaning 1000 rows and 17 columns.



- i assigned mainlist.columns to a variable **column_list** to get a nice dataframe view of the list of columns available in mainlist.



- moving on, i used thwe main_list.describe() methond to run a complete mathematical estimate on the numerical values of the given records. these estimates are the count, mean, standard deviation(std), minimum(min), first quartile(25%), median(50%), third quartile(75%), and the maximum(max). the essence of this is to have evaluated figures to work with instead of having to work from row to row or column to column.



- Next, i stated the various observations i could draw from this estimated data.



- I used the isnull() function to check for empty rows and columns but the results were all False(bool) indicating there are no null values in the dataset 'main_list'.



- I used the .info() function to to get information about the index, name, non-null countn memory usage and datatype of each column. the 'Non-Null Count' for each column return a values of 1000 further affirming there are no null values or missing entries. I stated my observation as regards null values.


### Dealing with datetime feature

   It was observed after using the.info() method that the Date and Time columns were not of appropriate datatypes. hence the need for a conversion.
    
    
    
- the conversion was made using the to_datetime() function on the Date and Time columns using the following format:

    *main_list['column name'] = pd.to_datetime(main_list['column_name'])*
    


- I also checked the Date and Time columns datatypes using thev .info() method which i used earlier on to ensure they were converted succesfully.


### Extracting features from date and time

- Moving on, i used the following dt.day, dt.month, dt.year, dt.hour methods to extract the days, months, years and hours and assigned them new columns.



- After the previous step, i used the .nunique() function on the newly created HOUR column to get the number of unique hours(11). i also used the .unique() function on the same column to get a list of these unique hours.


### Getting unique values in columns

- I was able to obtain a list of categorical columns in the dataset *main_list* using an iterative approach(for loop) and assigned the list to a new variable *Categorical_columns*.



- After getting the categorical columns, the next step taken was to get a the lsits of the unique values of each categorical column using the compounded functions unique().to_list(). next, i printed out the number of these unique values present in each categorial column.



- Next, i used the value_counts() method to generate a series containing the counts of the unique values in each categorical column.


### Aggregating with GroupBy

- The first step here was creating a groupby object eith the City column and also experimented with aggregation functions of sum and mean on the 'Tax 5%' column.



- Next was to display a table which shows the gross income of each city and also determine the city with the highest total gross income. This was achived by getting the max. value of the gross income of each city from the group by object 'City_Column'. The result showed that Port Harcourt city has the highest total gross income.



- going further, results were obtain for the mean, maximun and sum of the values in 'the Unit prince' column using the aggregation function.


### Data Visualization

- recall how we used the value_counts() method to generate a series containing the counts of the unique values in each categorical column? Here we use the seaborn visualization library with the countplot to visualize these results.
    **countplot** uses bars to plot graphs of count against unique values of the categorical columns:
    this process was repeated for all the categorical columns in the order:
    
1. Branch
2. Payment
3. City
4. Product line


- I then went ahead to do a countplot with hues.
I plotted:

1. prduct line (hue= 'Payment')
2. Payment (hue= 'Branch')


NOTE: *the essence of hues is to divide each bar of into sections wch correspond to the number of unique variable in the categoricsl column used as hue parameter and assigns then distince colours(color combinations are consistent across bars) such that the sum of d magnitude of all the colored sections will equal the magnitude of the uniform unsectioned bar. This is done for more visual details and analytic purposes*



- To plot categorical columns against each other, i used the **catplot** to plot:

- ***Quantity against product line with Gender as hue***; gives the estimated of the quantity of prodcts purchased from each product line and compares the results of males and females purchases in each product line.



- ***Total against product line with Gender as hue***; gives the estimated of the Total of sales from each product line and compares the Total of males and females in each product line.



- ***Unit price against product line with Gender as hue***; gives the estimated of the Unit price of products purchased from each product line.



- ***Unit Quantity against product line with Gender as hue***; gives the estimated of the Quantity of products purchased from each product line and shared my observations. I also went ahead to run a catplot but this time kind was set to 'boxen'. altho it looks similar to a box plot, it shows outliers, shape of distribution and values density.



- my last Experimentation was with the pairplot() which compares every non-categorical column with the other non-categorical columns.





# Insights



- First, as a rule of thumb, 5% is a low margin, 10% is a healthy margin and 20% is a high margine. Company XYZ has a mean gross percentage margine less than 5% which it low and needs to be increadsed.


- All froms of payments are actively used for purchases in all branches.


- branch B(Abuja) has the lowest overall rating amongst the three branches.


- Females have make more purchases and generated more overall Total across the product lines.


- The min cogs is greater than the min Unit price


# Future work



- In my future work i will take a deeper dive into more visualization options to enhance the clarity of output and also help me answer more questions on the way forward.  


# StandOut Section


- I experimented with the pairplot.

- I added my preferred hues and 'kind' parameters to satisfy my curiousity

- I created a new file for my project without having to edit the forked ones with guides.

# Executive Summary


- Having a minimum cogs which is greater than the minimum unit price implies that certain products are sold at loss. These products' Unit prices have to be incresed.



- Abuja branch(B) has the lowest overall rating across the three branches. Therefore, there's a need to improve the quality of customer service in that branch. As always there's room for improvement. Hence, other branches must also do better to have a higher mean rating for all branches.



- It is clear that females make the most purchases across the product lines. This might be as a result of having more product which catches the interest of females than males. It could be as a result of having more feminin products. Getting the Males to buy more by giving them wahat they want will help boost the mean quantity of goods purchase. A survey could be carried out to find out their interests.


- Setting up little annaual rewards for the best performed branch would motivated employees to do better.
