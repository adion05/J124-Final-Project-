# J124 Final Project: California Wildfires
## By Ashley Dionicio

### Part One: The Data 
For my project I chose to use the California Wildfires Data. It includes information from 2013 through 2020. 
Link for the data on [Kaggle](https://www.kaggle.com/ananthu017/california-wildfire-incidents-20132020)
* Disclaimer: throughout this file I will be using wildfires and fire interchangeably


**Getting Started**
1. Download the Kaggle data as a csv file. 
2. Open a google sheets document and import the data. 
3. Using pivot tables, the refine tool, and sorting clean up the data provided. <br> 

_I was not able to find anything wrong with the data at **First**_ 

<br>

### Part Two: The Questions and Answers 
__Question One__: What is the year with the most fires? <br>
Process:
1. On original page (without having anything selected) go to data and select create pivot table in a new sheet.
2. Set rows as archive year. 
3. Set values as archive year as well.
4. On values change summarize by to COUNTA.
5. This will provide a count of how many fires there were in any given year. 
6. From there you simply look at all the 7 years and determine which one has the most fires.

Answer:

2017| 438
----|---- 
<br>

__Question Two__: What are the top 5 counties with the most fires in all years? <br>
Process: 
1. On original page (without having anything selected) go to data and select create pivot table in a new sheet.
2. Set rows as counties.
3. Set values as archive year.
4. On values change summarize by to COUNTA.
5. This will give you the count of every fire for all 7 years for each county.
6. Copy the pivot table excluding the last line which is the grand total. 
7. On a new sheet paste special -> paste values only or command + shift + v. 
8. This will paste only the values and not the formatting of the pivot table. 
9. Highlight the 1st row which should be the headers of each column and go to view -> freeze -> 1 row.
10. From there sort column b or COUNTA of Archive year Z -> A
11. This will sort both colum's from the highest to lowest which will give you the answer. 

Answer:
County | # of fires
----------|----
Riverside |146
San Diego | 89
Butte | 66
San Luis Obispo | 64
Shasta | 64
<br>

__Question Three__: How many acres were burned during the 2015 year? <br>
Process:
1. On the main page create a filter.
2. Filter by archive year 2015.
3. This will only show the fires for the year 2015.
4. Higlight row B or the Acres Burned Column.
5. This will give you a little drop down menu at the bottom of the page, next to the Explore button.
6. If it is not already on sum you can click on the dropdown menu and select sum to get the sum of all acres burned for 2015. 

Answer:
Acres burned in 2015|574,503
----|---- 



