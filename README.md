# 🧹 Data Cleaning & Preprocessing — Assignment 03

This project focuses on cleaning and preprocessing a **dirty employee dataset** using Python and Pandas.

The goal was to identify common data quality issues, clean the dataset, validate the results, and prepare a more consistent dataset for further analysis or machine learning.

## 📌 Dataset

**Input file:** `dirty_dataset.csv`

The dataset contains employee-related information such as:

* Employee ID
* Name
* Age
* Salary
* Join Date
* Department
* Gender
* Country
* City
* Weight
* Active Status
* Review
* Price
* Target

## 🛠️ Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn / imbalanced-learn

## 🧹 Data Cleaning Tasks

### 1. Missing Values

* Identified missing values using `isnull()`
* Numeric columns → Median
* Categorical columns → Mode
* `join_date` → Forward Fill
* `review` → `No Review`
* `is_active` → False

### 2. Duplicate Rows

* Identified duplicate records
* Removed unnecessary duplicate rows
* Verified the dataset after cleaning

### 3. Duplicate Employee IDs

* Identified duplicate `employee_id`
* Kept the first occurrence
* Verified that duplicate IDs were removed

### 4. Wrong Date Formats

* Converted `join_date` into datetime format
* Handled invalid date values
* Standardized date representation

### 5. Numeric Stored as String

Converted numeric values stored as text into numeric format:

* `salary`
* `weight_kg`
* `price`

Also removed symbols such as `$` and `kg` where necessary.

### 6. Inconsistent Labels

Standardized inconsistent values in:

* `country`
* `gender`
* `department`

### 7. Spelling Mistakes

Identified and corrected spelling inconsistencies in categorical values such as city and department names.

### 8. Outliers

* Explored numeric distributions using `describe()`
* Used Box Plot for visualization
* Calculated IQR
* Identified outliers
* Used clipping to control extreme values

### 9. Invalid Values

Handled invalid values such as:

* Age below 18 or above 65
* Negative prices

Invalid values were replaced with `NaN` and handled using appropriate methods.

### 10. Noisy Reviews

Cleaned noisy and meaningless review values such as:

* `ok`
* `bad`
* `na`
* `n/a`
* `fine`
* `not bad`

These values were replaced with `NaN` and then filled with `No Review`.

### 11. Boolean as String

Converted different representations of `is_active` into standard Boolean values:

`True / False`

### 12. Data Type Issues

Checked and corrected data types for different columns, including:

* Numeric columns → `float`
* `join_date` → `datetime`
* `is_active` → `bool`

### 13. Range Violations

Defined and validated acceptable ranges for:

* `age` → 18–65
* `price` → 0–10,000
* `salary` → 15,000–500,000

### 14. Class Imbalance

Checked the distribution of the `target` variable and visualized the imbalance.

Used **Random Oversampling** to balance the classes for potential machine learning use.

### 15. Schema / Column Validation

* Checked missing-value percentages
* Removed columns with more than 50% missing values
* Validated expected columns
* Verified the final dataset schema

## 📊 Final Output

After completing the cleaning process, the cleaned dataset was exported as:

`Cleaned_dataset.csv`

```python
df.to_csv('Cleaned_dataset.csv', index=False)
```

## 📓 Notebook

The complete data cleaning process is available in:

`Assignment-03.ipynb`
