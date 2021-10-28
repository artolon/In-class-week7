# In-class-week7

### 1. Create an account on lucidchart.com and create an ERD diagram for the following scenario:

A grocery store owner would like to store all their data in a database. Some important facts you need to include are

1) The owner has multiple stores
2) The owner has multiple employees and the managers report to him, but all other employees report to store managers
3) The store has a membership program, but not all customers need to be members

Aside from this, use what you know about grocery stores to create a logical data model.

![Blank diagram](https://user-images.githubusercontent.com/59490033/139170632-0314d86f-c279-4eea-aef7-3fa703862da1.png)


### 2. With your group, create a list of at least 5 and no more than 10 ways data can be “dirty”. Perhaps think back to some data sets we have used that have had weird stuff in them. Discuss how you would resolve each of these and briefly explain.

How data can be dirty:
1) Some variables are in the wrong format. For example, dates as strings or when dates have time stamps that you want removed
   - There are lots of ways you could handle this. One way is to convert the string object into a date, using a date function and specifying the date format you    want. For example, doing something like datetime.strptime(your_date_string, '%d/%m/%y %H:%M:%S')
2) You might have some symbols in the data that make things more difficult to process (like a $ sign)
   - For this, we could use a for loop to iterate through the column and replace('$','') to replace with nothing. If needed, we could then convert the value to a float and/or integer, depending on what is needed.
3) You might have unwanted spaces, like extra spaces in column names and you would need to remove them
   - Similar to the dollar sign, we could use a replace function to remove spaces, like df.columns.str.replace(' ','')
4) Different variables might be spelled and/or abbreviated differently. For example, "St. Louis" could be St Louis, St. Louis or Saint Louis
   - We could use a for loop and conditional if/else statements to ensure that all instances are spelled the same way.
5) Handeling of null values: Sometimes null values are written 'NULL', sometimes they are coded 0, and sometimes they are just blank
   - We could use conditional if/else statements here as well. For example, we might write something like, "IF NULL column = 0" (if we wanted to replace all null values with 0. We could also search for blank/missing values, and make them 0 as well.

### 3. Look at the requirements for the exploratory data analysis project. List at least 2 APIs that have data interesting to you. Please pick at least one API that’s not listed in the project instructions.
1) FBI Crime Data API - https://crime-data-explorer.fr.cloud.gov/api
   - Would be interesting to visualize crime density, number/types of crimes, and trends over time
2) Soundcloud: http://developers.soundcloud.com/docs/api/guide#playing
   - Would be interesting to look at number of streams, top genres, artist age, etc.
