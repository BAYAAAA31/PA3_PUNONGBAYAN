# PA3 | ECE2112 | EXPERIMENT 3 | PUNONGBAYAN
---
### **PANDAS**
#### Submitted by Punongbayan, AJ Andriz J | 2ECE-A | 09.15.2026
---
### **Objectives**
---
At the end of this laboratory activity, the student should be able to:

1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

The students are also expected to use the same cars.csv dataset supplied for Experiment 3. Write the solutions in one Jupyter Notebook and import Pandas as pd. The dataset contains the Model column together with the vehicle variables used in the original experiment.

- Load the CSV file into a DataFrame named cars.
- Use Pandas subsetting, slicing, indexing, and Boolean conditions. Do not manually type any requested table or answer.
- Do not modify values in cars; create a new DataFrame or Series for each requested subset.
- Preserve the row order of the source dataset unless stated otherwise.
- Display every requested result in an executed notebook cell.


---
### **Programming Problems**
---
#### **A. POSITIONAL AND LABEL-BASED SLICING**

After loading cars, complete the following operations.

a. Display the shape and complete list of column names of cars.
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

**Requirement**: The row selection in part (b) must use iloc; the column selection in part (c) must use column labels.

**CODE**
```
import pandas as pd //this syntax downloads the library "pandas" as pd

cars = pd.read_csv('cars (1).csv') // the code recognizes "cars" as the dataframe of the csv file
cars // typing car displays the dataframe

print("Shape of cars:", cars.shape)
print("Column names:", cars.columns.tolist())

cars_6_to_10 = cars.iloc[5:10] // selects rows 6 to 10 from the data frame
cars_6_to_10

result = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']] // this then sorts the selected rows, leaving only the given labels
result
```

**OUTPUT**
```
'cars' displays the data frame

Shape of cars: (32, 12)
Column names: ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']

'cars_6_to_10' displays the row 6-10 of the data frame

'result' displays the row 6-10 of the data frame but only columns, "Model", "mpg", "cyl", "hp", "gear"
```

  
---
#### **B. MODEL LOOKUP**

Use Boolean indexing on the Model column to answer both requests.

a. Display the complete row for Toyota Corolla.
b. For Pontiac Firebird, display only Model, mpg, hp, and wt.

Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to locate either model.

**CODE**
```
toyota = cars[cars['Model'] == 'Toyota Corolla'] sets a variable for a given row in a data set.
toyota

pontiac = cars[cars['Model']=='Pontiac Firebird'][['Model', 'mpg', 'hp', 'wt']] // the same case as the variable "toyota", specific labels are used to filter out the row.
pontiac
```

**OUTPUT**
```
'Toyota' prints the row 'Toyota Corolla' only

'pontiac' prints the row 'Pontiac Firebird' with columns 'Model', 'mpg', 'hp', 'wt' only
```

---
#### **C. MULTI-MODEL SUBSETTING**

Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.

For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.

**Required check**: The final DataFrame must contain exactly three rows and five columns.

**CODE**
```
selected_cars = cars[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino')]
[['Model', 'mpg', 'cyl', 'hp', 'gear']] // assigns different rows of car models to a single variable

selected_cars

print ("Selected Car Shape", selected_cars.shape)
```

**OUTPUT**
```
'selected_cars' displays the data frame of the selected cars with the selected columns

Selected Car Shape (3, 12)
```
---
### **END OF NOTEBOOK**
