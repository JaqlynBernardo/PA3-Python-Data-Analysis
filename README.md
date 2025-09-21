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
* (b) Display the first five and last five rows of the resulting cars

**Solution A**
```
# Part A
cars = pd.read_csv('cars.csv')
cars
```
<br>
First, the variable 'cars' was declared. Inside the variable is the pd.read_csv calling the file 'cars.csv'. Then the cars dataframe was called to be printed.
<br><br>

**Results**
<br><br>
![alt text][P1A]

[P1A]: Results/Results-P1-A.png

**Solution B**
```
#Part B
B = cars.loc[(cars.index < 5) | (cars.index > 26), ['Model','mpg','cyl','disp','drat','wt','qsec','vs','am','gear','carb']]
B
```
<br>
First, the variable 'B' was declared. To get the first and last 5 rows of the dataframe, the .loc syntax was used. To specify this, for the rows, the expressions: "(cars.index < 5) | (cars.index > 26)" were used. These located the indices that are less than 5 (i.e., 0, 1, 2, 3, 4) and the indices that are more than 26 (i.e., 27, 28, 29, 30, 31), which are the respective heads and tails of this specific dataframe. For the columns, all the columns in the dataframe were listed. The variable 'B' was then displayed.
<br><br>

**Results**
<br><br>
![alt text][P1B]

[P1B]: Results/Results-P1-B.png

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
<br>
First, the variable 'A' was declared. Inside the variable is a .loc syntax. In the rows selector, the first five indices were called using the expression: "(cars.index < 5)". For the columns selector, the odd-numbered columns were called using the expression: "(cars.columns[1::2])". The .columns syntax called the columns of the dataframe. "[1::2]" was the slicing used to specify which columns were to be shown; it means the columns that will be shown start at column 1, then it will increment by 2 until there are no more columns to be shown. The variable 'A' is then displayed.
<br><br>

**Results**
<br><br>

![alt text][P2A]

[P2A]: Results/Results-P2-A.png

**Solution B**
```
# Part B
B = cars.loc[(cars['Model'] == 'Mazda RX4')]
B
```
<br>
First, the variable 'B' was declared. Inside the variable is a .loc syntax. In the row selector, it searches for 'Mazda RX4' under the 'Model' column. Since the column wasn't specified, it shows the entire row. The variable 'B' is then displayed.
<br><br>

**Results**
<br><br>
![alt text][P2B]

[P2B]: Results/Results-P2-B.png

**Solution C**
```
# Part C
C = cars.loc[(cars['Model']=='Camaro Z28'), ['Model','cyl']]
C
```
<br>
First, the variable 'C' was declared. Inside the variable is a .loc syntax. In the row selector, it searches for 'Camaro Z28' under the 'Model' column. In the column selector, it specifies both 'Model' and 'cyl', so only those two columns appear. The variable 'C' is then displayed.
<br><br>

**Results**
<br><br>
![alt text][P2C]

[P2C]: Results/Results-P2-C.png

**Solution D**
```
# Part D
D = cars.loc[(cars['Model']=='Mazda RX4 Wag') | 
            (cars['Model']=='Ford Pantera L') | 
            (cars['Model']=='Honda Civic'), 
            ['Model','cyl','gear']]
D
```
<br>
First, the variable 'D' was declared. Inside the variable is a .loc syntax. In the row selector, it searches for 'Camaro Z28', 'Ford Pantera L', and 'Honda Civic' under the 'Model' column. In the column selector, it specifies both 'Model', 'cyl', and 'gear', so only those three columns appear. The variable 'D' is then displayed.
<br><br>

**Results**
<br><br>
![alt text][P2D]

[P2D]: Results/Results-P2-D.png

## Author
Bernardo, Jaqlyn Trazy B.
* Section: 2ECE-C
* Student No.: 2024198347
