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
  df3.info()
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
## Quary Practice Example:
- Create New DataFrame using the below code-
```
import pandas as pd

df = pd.DataFrame({
    "Date": ["01-01-2025", "02-01-2025", "03-01-2025", "04-01-2025", "05-01-2025", "06-01-2025", "07-01-2025", "08-01-2025", "09-01-2025", "10-01-2025", "11-01-2025", "12-01-2025", "13-01-2025", "14-01-2025", "15-01-2025", "16-01-2025", "17-01-2025", "18-01-2025", "19-01-2025", "20-01-2025", "21-01-2025", "22-01-2025", "23-01-2025", "24-01-2025", "25-01-2025", "26-01-2025", "27-01-2025", "28-01-2025", "29-01-2025", "30-01-2025", "31-01-2025", "01-02-2025", "02-02-2025", "03-02-2025", "04-02-2025", "05-02-2025", "06-02-2025", "07-02-2025", "08-02-2025", "09-02-2025", "10-02-2025", "11-02-2025", "12-02-2025", "13-02-2025", "14-02-2025", "15-02-2025", "16-02-2025", "17-02-2025", "18-02-2025", "19-02-2025", "20-02-2025", "21-02-2025", "22-02-2025", "23-02-2025", "24-02-2025", "25-02-2025", "26-02-2025", "27-02-2025", "28-02-2025", "01-03-2025", "02-03-2025", "03-03-2025", "04-03-2025", "05-03-2025", "06-03-2025", "07-03-2025", "08-03-2025", "09-03-2025", "10-03-2025", "11-03-2025", "12-03-2025", "13-03-2025", "14-03-2025", "15-03-2025", "16-03-2025", "17-03-2025", "18-03-2025", "19-03-2025", "20-03-2025", "21-03-2025", "22-03-2025", "23-03-2025", "24-03-2025", "25-03-2025", "26-03-2025", "27-03-2025", "28-03-2025", "29-03-2025", "30-03-2025", "31-03-2025", "01-04-2025", "02-04-2025", "03-04-2025", "04-04-2025", "05-04-2025", "06-04-2025", "07-04-2025", "08-04-2025", "09-04-2025", "10-04-2025"],
    "Temperature_C": [21.24, 38.52, 31.96, 27.96, 14.68, 14.68, 11.74, 35.99, 28.03, 31.24, 10.62, 39.1, 34.97, 16.37, 15.45, 15.5, 19.13, 25.74, 22.96, 18.74, 28.36, 14.18, 18.76, 20.99, 23.68, 33.56, 15.99, 25.43, 27.77, 11.39, 28.23, 15.12, 11.95, 38.47, 38.97, 34.25, 19.14, 12.93, 30.53, 23.2, 13.66, 24.86, 11.03, 37.28, 17.76, 29.88, 19.35, 25.6, 26.4, 15.55, 39.09, 33.25, 38.18, 36.84, 27.94, 37.66, 12.65, 15.88, 11.36, 19.76, 21.66, 18.14, 34.86, 20.7, 18.43, 26.28, 14.23, 34.07, 12.24, 39.61, 33.17, 15.96, 10.17, 34.46, 31.21, 31.87, 33.14, 12.22, 20.75, 13.48, 35.89, 28.7, 19.93, 11.91, 19.33, 19.76, 31.89, 29.13, 36.62, 24.17, 13.59, 31.4, 32.82, 26.84, 33.13, 24.81, 25.68, 22.83, 10.76, 13.24],
    "Humidity_%": [32.04, 71.37, 50.43, 63.06, 88.99, 46.2, 56.67, 79.11, 44.87, 35.0, 48.83, 40.48, 90.43, 82.53, 71.17, 86.64, 82.24, 42.13, 88.02, 65.06, 82.48, 88.25, 50.67, 37.15, 44.82, 57.76, 83.17, 85.95, 30.45, 63.2, 57.13, 44.44, 37.79, 51.94, 91.29, 51.01, 63.72, 75.7, 53.64, 93.17, 92.56, 46.37, 62.32, 49.56, 48.51, 32.4, 69.62, 62.67, 33.35, 48.11, 89.04, 45.57, 39.42, 61.81, 94.07, 45.73, 73.69, 79.51, 45.45, 77.33, 53.91, 71.1, 71.18, 64.83, 35.87, 84.29, 50.85, 42.12, 32.65, 68.41, 74.04, 31.08, 63.29, 44.72, 71.94, 41.33, 74.91, 55.14, 90.89, 38.94, 52.17, 37.38, 90.11, 87.03, 46.77, 72.9, 83.12, 66.09, 64.43, 45.72, 36.05, 88.32, 88.53, 71.15, 52.04, 52.7, 77.19, 88.31, 87.66, 80.69],
    "Wind_Speed_kmph": [25.68, 3.37, 6.47, 35.94, 24.26, 0.37, 4.06, 26.54, 0.2, 6.43, 21.95, 27.68, 26.08, 8.97, 28.49, 9.49, 13.02, 29.86, 25.99, 33.97, 26.3, 22.73, 3.75, 14.71, 10.61, 9.76, 38.92, 15.72, 35.68, 25.25, 31.79, 20.11, 23.08, 19.7, 7.81, 28.9, 11.23, 0.97, 25.82, 7.08, 37.62, 38.16, 36.59, 14.81, 0.62, 37.13, 17.13, 38.67, 38.54, 34.12, 11.78, 15.4, 34.05, 12.68, 6.78, 22.27, 37.45, 27.84, 22.8, 3.89, 24.6, 39.6, 5.6, 20.73, 35.09, 29.63, 27.88, 28.1, 14.38, 11.74, 32.37, 32.4, 34.68, 36.53, 20.45, 20.06, 31.93, 26.0, 28.08, 31.83, 35.6, 13.52, 15.02, 3.76, 23.13, 1.44, 18.62, 21.71, 11.46, 23.63, 1.22, 1.49, 32.9, 14.41, 5.08, 20.89, 30.8, 8.63, 24.92, 3.41],
    "Rainfall_mm": [2.58, 26.57, 27.03, 31.87, 36.3, 48.79, 25.82, 16.15, 39.76, 13.54, 21.95, 3.92, 1.27, 48.13, 41.8, 34.8, 20.45, 8.66, 7.82, 12.51, 27.46, 35.73, 33.01, 14.0, 47.74, 36.89, 27.72, 30.59, 20.98, 12.39, 17.8, 37.89, 0.72, 5.8, 2.3, 2.04, 42.77, 35.18, 23.71, 4.89, 24.58, 23.67, 8.66, 21.69, 19.93, 30.79, 31.75, 2.27, 18.73, 31.29, 25.16, 42.82, 32.93, 8.15, 3.53, 32.12, 1.33, 29.29, 47.01, 28.77, 19.41, 32.16, 22.91, 27.28, 47.07, 19.31, 48.06, 45.27, 9.79, 3.47, 5.04, 0.91, 4.72, 34.15, 3.56, 15.95, 42.24, 1.16, 40.72, 14.09, 5.91, 34.84, 31.45, 43.87, 36.75, 40.17, 14.1, 8.87, 37.53, 40.34, 49.53, 20.63, 18.6, 38.82, 17.04, 46.54, 42.92, 21.45, 37.54, 37.73],
    "Pressure_hPa": [987.22, 1043.18, 1015.37, 1037.85, 1002.4, 1042.69, 1007.24, 980.76, 1043.38, 986.39, 1002.35, 1046.5, 1046.54, 1020.14, 1024.23, 1011.39, 1000.52, 1003.01, 1027.08, 1032.67, 1035.41, 1035.27, 986.38, 1014.61, 984.03, 1018.47, 1010.91, 1042.14, 1004.56, 988.19, 990.01, 1033.31, 1023.28, 987.08, 985.89, 1029.07, 985.09, 1037.53, 1029.44, 985.69, 985.94, 1049.06, 1006.2, 1005.94, 1036.9, 1046.31, 1049.02, 1032.74, 1006.34, 985.85, 1034.4, 1019.09, 1009.7, 1043.44, 987.78, 1014.48, 980.79, 1012.81, 983.94, 988.32, 988.23, 1025.44, 1032.22, 1020.84, 1047.35, 1006.24, 1000.0, 1040.8, 995.65, 1047.43, 980.85, 1047.89, 983.02, 1042.38, 1016.94, 1049.51, 985.17, 1018.77, 1047.85, 1016.62, 1024.06, 1028.7, 1011.82, 1023.93, 1020.9, 1043.08, 983.18, 999.67, 1046.53, 1042.32, 1011.9, 1023.41, 999.42, 993.17, 1012.46, 1004.73, 1020.86, 985.44, 1048.21, 1049.03],
    "Dew_Point_C": [18.96, 15.72, 11.19, 21.28, 18.69, 8.25, 23.22, 21.45, 24.0, 19.51, 17.27, 13.36, 23.65, 22.32, 5.9, 5.53, 12.53, 21.21, 24.75, 8.01, 16.88, 12.62, 24.4, 21.84, 21.77, 14.37, 13.3, 10.47, 6.13, 22.29, 21.26, 24.99, 24.93, 16.11, 20.38, 23.9, 21.99, 9.95, 14.01, 7.58, 24.08, 17.12, 9.57, 18.43, 17.36, 12.16, 7.27, 18.43, 15.41, 20.45, 15.4, 22.04, 16.04, 16.22, 22.53, 13.07, 7.68, 5.58, 20.1, 17.41, 19.08, 9.26, 7.73, 5.29, 12.01, 16.8, 12.84, 13.75, 23.08, 11.97, 15.28, 20.67, 12.93, 17.44, 22.25, 23.99, 7.94, 23.53, 14.84, 10.16, 14.18, 24.6, 14.85, 11.58, 17.67, 9.8, 6.52, 7.58, 7.56, 8.04, 7.78, 17.82, 8.64, 11.91, 22.94, 14.48, 18.35, 8.45, 8.85, 5.82],
    "Solar_Radiation_W/m2": [285.83, 406.45, 294.71, 197.57, 232.7, 606.86, 326.97, 500.7, 653.76, 859.43, 143.24, 979.35, 790.69, 189.93, 1060.94, 1112.96, 167.19, 404.57, 986.82, 923.09, 302.97, 330.28, 507.52, 632.98, 780.08, 505.81, 608.79, 922.22, 140.35, 377.68, 884.68, 1084.73, 662.85, 685.32, 217.89, 592.15, 685.88, 366.72, 396.17, 515.01, 122.08, 454.29, 332.59, 460.25, 231.74, 1079.58, 752.95, 847.01, 968.09, 648.29, 195.61, 690.82, 745.53, 919.98, 574.83, 240.34, 412.15, 499.39, 810.51, 727.86, 491.71, 1185.17, 766.35, 360.95, 211.96, 268.15, 370.55, 276.75, 305.22, 413.6, 290.71, 1086.44, 188.26, 676.96, 551.44, 1180.62, 223.24, 537.64, 1166.42, 1052.06, 998.78, 383.69, 287.98, 835.51, 1122.31, 712.44, 728.77, 407.98, 946.44, 305.75, 456.05, 567.98, 658.37, 366.65, 226.32, 771.68, 417.49, 739.36, 269.8, 629.25],
    "Visibility_km": [5.79, 1.47, 4.03, 2.21, 1.57, 9.91, 3.9, 8.29, 3.29, 7.13, 7.84, 6.36, 5.24, 4.71, 4.14, 9.37, 8.48, 9.69, 2.12, 7.58, 9.45, 2.63, 1.6, 7.67, 6.17, 8.58, 2.26, 8.16, 2.81, 2.47, 2.48, 8.33, 6.99, 5.71, 4.23, 8.89, 4.53, 8.35, 4.95, 4.39, 5.16, 3.71, 7.73, 5.52, 3.09, 9.1, 4.46, 5.89, 9.16, 6.62, 2.05, 9.46, 6.65, 4.01, 2.25, 8.15, 6.58, 5.8, 9.05, 8.1, 2.37, 3.81, 3.24, 7.7, 1.3, 6.13, 7.86, 8.89, 4.08, 8.39, 2.0, 8.62, 2.15, 4.58, 8.18, 2.35, 3.06, 7.5, 7.48, 6.77, 7.25, 5.88, 3.27, 4.11, 2.63, 9.18, 6.25, 4.61, 5.16, 9.53, 2.38, 6.28, 5.55, 6.5, 1.16, 8.85, 9.39, 6.09, 7.27, 9.3],
    "Weather_Condition": ["Cloudy", "Sunny", "Stormy", "Cloudy", "Sunny", "Rainy", "Foggy", "Sunny", "Rainy", "Sunny", "Foggy", "Foggy", "Cloudy", "Stormy", "Sunny", "Sunny", "Rainy", "Foggy", "Sunny", "Foggy", "Sunny", "Cloudy", "Stormy", "Sunny", "Foggy", "Cloudy", "Sunny", "Rainy", "Stormy", "Sunny", "Cloudy", "Rainy", "Cloudy", "Cloudy", "Rainy", "Cloudy", "Rainy", "Sunny", "Rainy", "Rainy", "Stormy", "Rainy", "Rainy", "Sunny", "Stormy", "Foggy", "Sunny", "Sunny", "Foggy", "Rainy", "Cloudy", "Stormy", "Cloudy", "Foggy", "Sunny", "Sunny", "Stormy", "Sunny", "Sunny", "Stormy", "Stormy", "Foggy", "Sunny", "Sunny", "Foggy", "Rainy", "Rainy", "Rainy", "Foggy", "Sunny", "Foggy", "Foggy", "Rainy", "Cloudy", "Sunny", "Rainy", "Cloudy", "Cloudy", "Stormy", "Sunny", "Cloudy", "Rainy", "Stormy", "Sunny", "Foggy", "Rainy", "Cloudy", "Cloudy", "Rainy", "Cloudy", "Stormy", "Sunny", "Stormy", "Cloudy", "Foggy", "Sunny", "Sunny", "Rainy", "Rainy", "Foggy"],
})

```
- print it 
```
print(df)

```
- Perfrom the given quaries using this DataFrame df :
1. Load the dataset and print the first 5 rows. 
2. Show the last 3 rows of the dataset. 
3. Print the total number of rows and columns in the dataset. 
4. Display only the column names of the dataset. 
5. Select only the “Temperature” column and print it. 
6. Show all rows where Temperature is greater than 30°C. 
7. Show only the rows from index 5 to index 10 (inclusive). 
8. Add a new column named Temp_Fahrenheit based on Temperature. 
9. Replace missing humidity values with the value 50. 
10. Drop the column named "Air_Quality" from the dataset. 
11. Show the details of all days where the Temperature is higher than the average Temperature of the first 5 rows. 
12. Display only those rows where BOTH Temperature > 25 AND Air_Quality is missing (NaN). 
13. Add a new column called “TempPlusHumidity” = Temperature + Humidity, and display the last 5 updated rows. 
14. Select rows from index 3 to index 10 but show ONLY the columns Temperature and Humidity. 
15. Update the Humidity of the 2nd row to 50, then print the updated row. 
16. Drop the row where Temperature is the lowest in the dataset. 
17. Show all rows where any column has a missing value. 
18. Replace the missing values in the Humidity column with 0, then print the first 10 
19. Create a new column named “Category” such that: 
    - -  If Temperature > 30 → Category = "HOT" 
    - - Otherwise → Category = "NORMAL" 
20. Remove the column with the most missing values from the dataset. 

