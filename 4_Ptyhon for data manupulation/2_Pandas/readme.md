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