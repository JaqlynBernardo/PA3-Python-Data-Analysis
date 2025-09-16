# PA3-Python-Data-Analysis
This repository serves as a submission. This program was made and written in partial fulfillment of the requirements for Advanced Computer Programming and Algorithms (ECE2112).

## Description
This program shows different demonstrations of generating, subsetting, slicing, and indexing dataframes, using the Python Data Analysis library (PANDAS).

## Instructions
Write a Python script/code in the Jupyter Notebook to do the given problems.

### Importing PANDAS Library
```
import pandas as pd
```
Before writing the code, the Pandas Library was imported. This grants access to the dataframe object and its associated operations and functions.

### Problem #1
Using knowledge obtained from the experiment and demonstrations: <br> 
* (a) Load the corresponding .csv file into a data frame named cars using pandas <br>
* Display the first five and last five rows of the resulting cars

**Solution A**
```
# Part A
cars = pd.read_csv('cars.csv')
cars
```
<br>

<br><br>
**Results**

<br><br>

**Solution B**
```
#Part B
B = cars.loc[(cars.index < 5) | (cars.index > 26), ['Model','mpg','cyl','disp','drat','wt','qsec','vs','am','gear','carb']]
B
```

<br><br>
**Results**
<br><br>

### Problem #2
Using the dataframe cars in problem 1, extract the following information using subsetting, slicing and indexing operations. <br> 
* (a) Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7…) of cars. <br>
* (b) Display the row that contains the ‘Model’ of ‘Mazda RX4’. <br>
* (c) How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? <br>
* (d) Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have. <br> 

**Solution A**
```
# Part A 
A = cars.loc[(cars.index < 5), # Get first 5 rows
            (cars.columns[1::2])] # Slice columns - starting at 1 with an increment of 2 
A
```
<br><br>
**Results**
<br><br>

**Solution B**
```
# Part B
B = cars.loc[(cars['Model'] == 'Mazda RX4')]
B
```
<br><br>
**Results**
<br><br>

**Solution C**
```
# Part C
C = cars.loc[(cars['Model']=='Camaro Z28'), ['Model','cyl']]
C
```
<br><br>
**Results**
<br><br>

**Solution D**
```
# Part D
D = cars.loc[(cars['Model']=='Mazda RX4 Wag') | 
            (cars['Model']=='Ford Pantera L') | 
            (cars['Model']=='Honda Civic'), 
            ['Model','cyl','gear']]
D
```
<br><br>
**Results**
<br><br>



## Author
Bernardo, Jaqlyn Trazy B.
* Section: 2ECE-C
* Student No.: 2024198347
