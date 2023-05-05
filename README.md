# Titanic-Data

## Check the dataset against:
1. Outliers,
2. Duplicates,
3. Missing data,
4. NaNs,
5. Blanks (missing values),
6. Wrong/improper values,
7. Other data-related issues,
8. Clean & repair the dataset.
-----------------------------

Code Explanation
The script is divided into the following sections:
<pre>
1. Read the data from the file
Reads the Titanic dataset from a TSV file using the read_csv() function from the pandas library. The separator is set to \t since it is a TSV file.

2. Check for outliers
Converts the Fare column to numeric using the to_numeric() function from pandas with the errors='coerce' parameter to convert any non-numeric values to NaN. Outliers are defined as values greater than 500 and are stored in a new dataframe called outliers.

3. Check for duplicates and missing values
Checks for duplicates using the duplicated() function from pandas and stores them in a new dataframe called duplicates. Checks for missing values using the isnull() function from pandas and stores them in a new dataframe called missing_data. The number of missing values for each column is stored in a series called missing_values. The names of columns with missing values are stored in a list called nan_cols_list. Checks for blank values using the isin() function from pandas and stores them in a new dataframe called blanks. The number of blank values for each column is stored in a series called blank_values.

4. Check for wrong/improper values
Checks for wrong/improper values in the Sex and Embarked columns and stores them in new dataframes called wrong_sex_values and wrong_embarked_values, respectively. Checks for other data-related issues in the Survived and Pclass columns and stores them in new dataframes called wrong_survived_values and wrong_pclass_values, respectively.

5. Fix some data issues
Fixes some data issues in the Sex, Survived, Pclass, and Embarked columns using the replace() function from pandas.

6. Drop some columns and rows with missing values
Drops the Cabin and Age columns using the drop() function from pandas. Drops any rows with missing values in the Ticket, Fare, and Embarked columns using the dropna() function from pandas. Resets the index of the dataframe using the reset_index() function from pandas.

7. Remove existing PassengerId column
Removes the existing PassengerId column using the drop() function from pandas.

8. Add a new column with sequential passenger IDs
Adds a new column called PassengerId using the insert() function from pandas. The values in this column are a sequential range of integers starting from 1 and ending at the length of the dataframe.

9. Save the cleaned data to a new file
Saves the cleaned data to a new TSV file called Titanic_cleaned.tsv using the to_csv()
