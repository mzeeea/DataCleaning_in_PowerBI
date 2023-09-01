# DataCleaning_in_PowerBI

![](PowerBI.jfif)

## Task

Extensively clean the **Employee.csv**, **Department.csv**, and **Salary.csv** datasets provided under the Dirty Datasets folder in the drive. Merge all three datasets together.


## Data Cleaning

### Department table

- I changed the data type for DeptID column from _Whole Number_ to _text_ because it is not going to be aggregated.
- I renamed _DeptID_ column to _Department ID_
- To get rid of the _null_ rows, I kept the top 11 rows.

### Employee table

- I changed the data type for the following columns from _Whole Number_ to _text_ because the columns are not going to be aggregated: _EmpID_, _aadhar_, _pincode_, _phone_.
- I renamed the following columns:

From      | To
----------|-------------
EmpID     | Employee ID
name      | First Name
fname     | Last Name
dob       | Date of Birth
DeptID    | Department ID

- The _dob_ now _Date of Birth_ column is not properly formatted and also has the wrong data type. To correct this, I first changed the formatting by making the date separator uniform. I replaced the _/_ character with _-_ character.
Because changing the data type from text to date gives an error due to the improper order of the date which Power BI does not recognize, I need to split the columns and then rearrange them in the order Power BI will recognize.
I split the columns into year, month, and day and then merged them in the order Year/Month/Day and named the new column _Date of Birth_.

### Salary table

- The salary table has almost 100 empty rows. I used the "keep top row" tab and kept the top 100 rows because they are the ones that contain information.
- I changed the data type of the _empID_ column from **Whole Number** to **Text** because the column will not be aggregated.
- I renamed the following columns:

From      | To
----------|-------------
EmpID     | Employee ID
Base      | Salary

## Table Merging
I merged the **Salary** and **Employee** tables using the _full inner join_ on the **Employee ID** column. I merged the resulting table with the **Department** table on the _Department ID_ column.
