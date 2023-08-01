# Data-Preprocessing

**Building Permit Applications Data - Data Preprocessing**

  This project involves preprocessing and cleaning the "Building Permit Applications Data" obtained from Kaggle https://www.kaggle.com/datasets/aparnashastry/building-permit-applications-data. The dataset contains information about building permit applications in a certain region. The goal of this project is to prepare the data for further analysis and modeling by handling missing values, data type conversions, and other necessary adjustments.

**Dataset Information**

  The dataset contains various columns providing details about building permits, such as existing and proposed use, construction types, location, and more. Some of the columns have missing values that need to be addressed.

**Steps Taken**

**Reading the Dataset:**

  
  The dataset was read into a pandas DataFrame using pd.read_csv() function.

**Handling Almost Empty Rows:**

  
  Rows with almost all missing values were dropped from the DataFrame using the dropna() function.

**Handling Mixed Data Types Warning:**

  
  A DtypeWarning regarding mixed data types in certain columns was addressed by specifying data types explicitly using the dtype parameter during CSV reading.

**Handling Missing Values:**


-Several columns with missing values were processed and filled appropriately:

-Filled missing 'Street Number Suffix' data using 'Street Number'.

-Columns with more than 85% of data missing were dropped, including 'Unit', 'Unit Suffix', 'Voluntary Soft-Story Retrofit', and 'TIDF Compliance'.

-Missing data in 'Site Permit' was assumed to be 'N' (no permit).

-Missing data in 'Issued Date' was filled using 'Filed Date'.

-Missing data in 'Completed Date' was filled using 'Issued Date' where the 'First Construction Document Date' matched 'Issued Date'.

-'First Construction Document Date' missing values were filled by adding the average difference between this date and 'Issued Date'.

-'Structural Notification' missing values were assumed to be 'N' (no notification).

-Remaining missing values in 'Permit Expiration Date' were replaced with NaT.

**Data Type Conversions:**

  Appropriate data type conversions were performed for columns like 'Estimated Cost', 'Revised Cost', 'Existing Units', 'Proposed Units', 'Existing Construction Type', 'Proposed Construction Type', and 'Zipcode'.

**Filling NaN Values based on Other Columns:**

  
  In some cases, missing values were filled based on related columns, such as 'Existing Use' and 'Proposed Use', 'Number of Existing Stories', and 'Number of Proposed Stories'.

**Imputing Missing Descriptions:**

  For columns like 'Existing Construction Type Description' and 'Proposed Construction Type Description', missing values were imputed based on the construction type.

**Handling Remaining Missing Values:**

  For the remaining missing values, appropriate assumptions were made and the NaNs were filled with relevant information or 'no info' values.

**Visualizations**
  
  A heatmap was used to visualize the locations of missing values in the dataset.

  **Conclusion**
  
  The dataset was successfully preprocessed and cleaned, with missing values handled, data type conversions performed, and appropriate filling strategies applied. The data is now ready for further analysis, modeling, and insights extraction.
