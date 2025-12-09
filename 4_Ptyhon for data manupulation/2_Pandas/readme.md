## 1. Definition of Pandas :  
- Pandas is an open-source Python library used for data analysis, data manipulation,and data cleaning. 
- It provides fast and flexible tools to work with structured data, especially in tabular form (rows and columns), similar to Excel or SQL tables. 
- DataFrame : A DataFrame is a two-dimensional, tabular data structure similar to an Excel sheet or SQL table.It contains rows and columns, where:
       - Rows represent records (observations)
       - Columns represent fields (attributes)


## 2.What is Dataset :
- A dataset is a collection of related data that is organized in a structured way so it can be easily accessed, managed, and understood.

## 3. Basic Functions for dataframe creation:  
- a. Creating DataFrames manually –  
   ```
   import pandas as pd
   df1=pd.DataFrame({
      'Name':['A','B','C'],
      'Age':[23,25,21]
   })
   print(df1)
  ```
- b. Creating DataFrames CSV -
  syntax:
   ```
   df_name=pd.read_csv("data set path")
  ```
  Example:
  ```
  import pandas as pd
  df2=pd.read_csv("kaggle/input/studentdata/data.csv")
  print(df2)

  ```
## 4. Manually created DataFrame to perfrom some operation 
```
import pandas as pd

df3 = pd.DataFrame({
    "Student_ID": [101, 102, 103, 104, 105],
    "Name": ["Amit", "Riya", "Sohan", "Priya", "Rahul"],
    "Age": [18, 19, 20, 18, 21],
    "Gender": ["Male", "Female", "Male", "Female", "Male"],
    "Department": ["CSE", "ECE", "ME", "CSE", "IT"],
    "Semester": [1, 3, 5, 1, 2],
    "CGPA": [8.2, 8.8, 7.5, 9.1, 7.9],
    "Contact_No": [9876543210, 9123456780, 9998887776, 7894561230, 9870012345],
    "Email": [
        "amit@example.com",
        "riya@example.com",
        "sohan@example.com",
        "priya@example.com",
        "rahul@example.com"
    ],
    "Address": ["Kolkata", "Delhi", "Mumbai", "Chennai", "Pune"]
})

print(df3)

```
## 5. View Data:
- head()- print First 5 row.
```
df3.head()
```
- tail()- print last 5 row
```
df3.tail()
```
- info() - commumn types and summary
  ```
- shape - used know total number of row and collumn
```
df3.shape
```
## 6. Selecting Data : 
- a. Select column-
Example 1- 
``` 
df4=df3['Name'] 
print(df4) 
```
Example 2
```
df5=df3[‘Name’,’Age’] 
print(df4) 
```
- b. Select Rows-  
Example 1 
```
df3.iloc[2] # selecting By index
```
Example 2
```
df3.loc[2:4] # By Range 
```
- c. Row filtering – 
Example1 - suppose I want to show  student details whose Age have ( 20>Age>25) 
``` 
df6=df7[(df3['Age'] > 20) & (df3['Age']<25)] 
print(df6) 
```
## 7. Adding / Updating Data 
- a. Add a new column - 
Example 1
```
df8["new_col"] = df3["Age"] + 5 
print(df8) 
```
- b. Update a specific value - 
Example 2 
```
df3.loc[0, "Age"] = 30     # Update Amit’s age to 30 
print(df3) 
```
## 8. Removing Data 
- a. Drop a column - 
Example 1
```
df3.drop("new_col", axis=1, inplace=True) 
print(df3) 
```  
- b.Drop specific rows -  
Example 2 
```
df6 = df3.copy()   # copy all the values df3 to df6.
print(df6)
df6.drop([0, 3], axis=0, inplace=True) #Drop rows 0 to 3
print(df6)
```

## 9. Handling Missing Values 
- a. Check missing - checks every value in the DataFrame and returns:  
- - True → if the value is missing (NaN / None / Blank) 
- - False → if the value is present (not missing) 
Example 
```
df3.head() 
df3.isnull() # check missing data 
```
Now we can create a null value at 3rd row and name column
```
import numpy as np 
df3.loc[3, "Name"] = np.nan # replace with NaN for verifying  
df3.head() 
df3.isnull()#verifying 
```
- b. dropna() – remove complete missing rows 
```
df8=df3.copy()# copy data 
print(df8) 
df8.dropna()#drop row 
print(df8) 
```
- c. fillna(value)-Replace missing values 
- - Ex1- all the missing missing value replace with same value - 
```
df3.fillna(“Subha”) 
```
- - Ex2- For a particular column -  
```
df3.loc[2, "Department"] = np.nan # just create a nan value 
print(df3) 
df3["Department"].fillna("CSE")# for specific department column
print(df3)
```

