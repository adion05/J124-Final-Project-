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
1. On original page (without having anything selected) go to data and select 'create pivot table' in a new sheet.
2. Set rows as 'archive year'. 
3. Set values as 'archive year' as well.
4. On values change 'summarize by' to COUNTA.
    1. This will provide a count of how many fires there were in any given year.
5. From there you simply look at all the 7 years and determine which one has the most fires.

Answer:

2017| 438
----|---- 
<br>

__Question Two__: What are the top 5 counties with the most fires in all years? <br>
Process: 
1. On original page (without having anything selected) go to data and select 'create pivot table' in a new sheet.
2. Set rows as 'counties'.
3. Set values as 'archive year'.
4. On values change 'summarize by' to COUNTA.
    1. This will give you the count of every fire for all 7 years for each county.
   
5. Copy the pivot table excluding the last line which is the grand total. 
6. On a new sheet right click on to 'paste special' -> 'paste values only' or command + shift + v. 
    1. This will paste only the values and not the formatting of the pivot table. 
    
7. Highlight the 1st row which should be the headers of each column and go to 'view' -> 'freeze' -> '1 row'.
8. From there sort column b or COUNTA of Archive year Z -> A
    1. This will sort both colum's from the highest to lowest which will give you the answer. 
    

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
2. Filter by 'archive year' and uncheck all years except 2015.
    1.This will only show the fires for the year 2015.
    
3. Higlight row B or the 'Acres Burned' Column.
    1. This will give you a little drop down menu at the bottom of the page, next to the Explore button.
    
4. If it is not already on sum you can click on the dropdown menu and select sum to get the sum of all acres burned for 2015. 

Answer:
Acres burned in 2015|574,503
----|----
<br>

__Question Four__: What is the sum of acres burned for each year?
Process:
1. On original page (without having anything selected) go to data and select 'create pivot table' in a new sheet.
2. Set rows as 'archive year'.
3. Set values as 'acres burned'.
4. On values change 'summarize by' to SUM.
    1. This will give you a count of all acres burned by year.
    

Answer:

ArchiveYear	|SUM of AcresBurned
------------|------------------
2013 | 527,745
2014 | 448,715
2015 | 574,503
2016 | 505,927
2017 | 1,793,915
2018 | 3,358,049
2019 | 285,708
Grand Total | 7,494,562

This also confirms the previous answer we got for question three

<br>

__Question Five__: Which fire had the most fatalities? 
Process:
1. Sort Fatalities column in descending order from Z -> A.
2. Notice that there are some repeated numbers.
3. Do some further digging and find that there are duplicates of some rows. 
4. Even though there were only slight variations in the information they need to be removed.
5. To find all the duplicates in the data make a conditional format. 
6. Highlight all of column 'UniqueId'. This column provides the unique ID given to every fire which will help find the duplicates.
7. While highlighting column go to 'Format' -> 'Conditional Formatting'.
    1. This will bring up a window.

9. The first item 'Apply to range' should already be filled out with the range you highlighted.
10. Click on the '+ Add another rule' option in menu.
11. Change 'Format Cells if...' to 'Custom formula is'.
12. Enter the duplicate check formula which for our data is “=countif($A$2:$A$15,A2)>1”. 
13. In 'Formatting Style' change the bucket icon to yellow so that it will highlight the duplicates.
14. Hit 'done' to return a 'true/false' response.
    1. This will highlight all the duplicates in the data set by their ID number.
 
16. Make a copy of this data so as to be able to refer to the original one at any time. 
17. In the copy create a filter.
18. Filter the 'UniqueId' column by 'Filter by color' -> 'Fill color' -> yellow.
    1. This will only show the duplicates which had been highlighted by the conditional formatting.

20. Select all of the values and delete them in the copy set.
21. Create a pivot table from the copy of the data set.
22. Set rows as 'UniqueId'.
23. Set values as 'Fatalities'
24. On values change 'summarize by' to SUM.
    1. While this gave us the fires with the most fatalities. We are unable to further identify them besides their Unique ID. So we need to join this information to the original data set.

26. To do this we first need to copy the pivot table information onto another sheet. 
27. Copy the pivot table excluding the last line which is the grand total. 
28. On a new sheet right click on to 'paste special' -> 'paste values only' or command + shift + v. 
    1. This will paste only the values and not the formatting of the pivot table. 

30. Sort both 'UniqueId' from the sheet with the fatalities and the copy of the data sheet from A -> Z
31. On the copy data sheet create a blank column next to UniqueId where we can use vlookup.
32. Type in '=VLOOKUP(A2,Sheet1!A725:B2333,2,false)'
    1. A2 is the values you are searching for 
    2. Sheet1!A725:B2333 is the range of what we are importing from
    3. 2 is the column being matched from
    4. and false indicates that the column is unsorted
34. Now all you need to do is sort column 'Total Fatalities' from Z -> A to get the fires with the highest fatalities. 

Answer:

Total Fatalites | Name
---------------|-------
85 | Camp Fire
44 | Border 10 Fire
12 | Jerusalem Fire




