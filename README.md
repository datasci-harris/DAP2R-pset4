# Data Skills 2 - R
## Winter Quarter 2024

## Homework 4
## Due: Monday March 6 before midnight on GitHub Classroom

__Question 1 (60%):__ Big Data: 

From [ProPublica](https://projects.propublica.org/nursing-homes/), download the unredacted version of nursing home inspection reports (link at bottom of page). It should download a zip file named "nursing-homes-unredacted-April2019.zip." 
1. Unzip the files (this can be done manually or in R) in a folder __outside__ of the one you will upload to Github. Your code should allow the user to input the name of the path where the unzipped CSV files are.
2. Load the CSVs together as one parquet. The code to do this should be generalized so that if the folder of CSVs is updated with more files, the code will be able to handle this. 
3. Then partition the data by state, and write the partitioned dataset to disk as a series of parquets. Again, save this to a folder  __outside__ of the one you will upload to Github. Load the partitioned datasets as a new parquet.
4. Write a function that takes as input a state name, and then times how long it takes to do the following: filter data by state, then create a summary table with the number of deficiencies for each severity level. The function will measure how long it takes to run it using the non-partitioned data loaded from CSV vs. the partitioned data loaded from the parquets you saved in step 3. (Hint: look into how to use Sys.time() to measure how long code takes to run). This function will print the time elapsed with and without partitioning, as well as the difference between the two.
5. Make a scatter plot of the time saved by using partitioning, where each state is one point on the scatter plot. Let the x-axis be the total number of observations in the dataset after filtering for that state. Then create a plot depicting how many times faster working with the partitioned data is as opposed to the non-partitioned data. Is there a relationship with the size of the filtered data? Note that this might take awhile to run! Save the scatter plot as a .png.

Then let the y-axis include the total time without partitioning, total time elapsed with partitioning, and the difference in time between the two.  What is the relationship between the time saved by using parquets and the size of the filtered data? 

__Question 2 (40%):__ Python: 
Combine your answers to the following 3 questions into one .py file.

  1. Write code that begins with a Python list, containing some number of integers or floats. From the original list, perform each of these separately:
     * Multiply each value by 2. (Hint: look up *list comprehensions*)
     * Remove all odd numbers
     * Print a random value from the list. (Hint: look up the _random_ standard Python library, or the _random_ section of the NumPy library.)
  2. Write a Python **function** that takes a string as an argument, then returns a modified string.  Your function should:
     * First, test that the argument is a string, and that its length is at least 15 words. (Hint: look up the _assert_, _isinstance_, and _len_ standard Python functions.)
     * Second, split the string on any periods.  The result will be a list with strings in it.
     * Third, make each string in the list begin with a capital letter, with all other letters lowercase.
     * Fourth, join the strings back together into one string with the newline character ("\n") between each
     * Return the resulting string, then display it with a _print_ function.
    
 3. The first day of class was January 4, 2024.  Write code that shows how many days have elapsed between then and now, where "now" is the date someone runs your code. (Hint: look up the _datetime_ standard Python library.)
