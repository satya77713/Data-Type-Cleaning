# Data Type Cleaning Using Python & Pandas

## 📌 Project Overview

This project focuses on identifying and correcting data types in an Employee dataset using Python and Pandas.

The main objective is to convert categorical columns into appropriate data types, verify numerical columns, inspect missing values, and prepare a clean dataset for further data analysis and machine learning.

This project was completed as **Task 24 (Day 24)** of the Veda Technology AI & ML Internship.

## 🎯 Objectives

- Load and explore an Employee dataset.
- Inspect the original data types.
- Identify categorical and numerical columns.
- Convert object columns into category data types.
- Verify numerical data types.
- Check missing values.
- Compare original and corrected data types.
- Export the cleaned dataset as a CSV file.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Google Colab
- Jupyter Notebook
- CSV Dataset

## 📂 Dataset Information

**Dataset Name:** Employee.csv

**Dataset Size:**
- Total Records: 4,653
- Total Columns: 9
- Missing Values: 0

### Dataset Columns

| Column Name | Description |
|---|---|
| Education | Employee education level |
| JoiningYear | Year of joining |
| City | Employee city |
| PaymentTier | Employee payment tier |
| Age | Employee age |
| Gender | Employee gender |
| EverBenched | Whether employee was ever benched |
| ExperienceInCurrentDomain | Experience in current domain |
| LeaveOrNot | Employee leaving status |

## ⚙️ Project Workflow

### 1. Import Libraries

```python
import pandas as pd
import numpy as np
```

### 2. Load Dataset

```python
df = pd.read_csv('Employee.csv')
```

### 3. Explore Dataset

```python
display(df.head())
df.info()
```

### 4. Check Original Data Types

```python
print(df.dtypes)
```

### 5. Identify Unique Values

```python
for column in df.columns:
    print(f"\n{column}:")
    print(df[column].unique())
```

### 6. Convert Data Types

Converted categorical columns using `astype('category')`.

```python
categorical_columns = [
    'Education',
    'City',
    'Gender',
    'EverBenched'
]

for column in categorical_columns:
    df[column] = df[column].astype('category')
```

Verified numerical columns using `pd.to_numeric()`.

```python
numerical_columns = [
    'JoiningYear',
    'PaymentTier',
    'Age',
    'ExperienceInCurrentDomain',
    'LeaveOrNot'
]

for column in numerical_columns:
    df[column] = pd.to_numeric(
        df[column], errors='raise'
    )
```

### 7. Compare Original and Corrected Data Types

Created a comparison between the original and cleaned data types to understand the changes.

### 8. Check Missing Values

```python
print(df.isnull().sum())
```

### 9. Export Cleaned Dataset

```python
df.to_csv(
    'Cleaned_Employee_Dataset.csv',
    index=False
)
```

## 📊 Data Type Conversion Results

| Column | Original Type | Corrected Type |
|---|---|---|
| Education | object | category |
| JoiningYear | int64 | int64 |
| City | object | category |
| PaymentTier | int64 | int64 |
| Age | int64 | int64 |
| Gender | object | category |
| EverBenched | object | category |
| ExperienceInCurrentDomain | int64 | int64 |
| LeaveOrNot | int64 | int64 |

**Result:** Four categorical columns were converted from object to category. Five numerical columns were verified and retained their appropriate numerical data types.

## 📁 Project Structure

```text
Data-Type-Cleaning/
│
├── Employee.csv
├── Data_Type_Cleaning.ipynb
├── Cleaned_Employee_Dataset.csv
└── README.md
```

## 🚀 How to Run the Project

1. Clone this repository:

```bash
git clone https://github.com/satya77713/Data-Type-Cleaning.git
```

2. Navigate to the project folder:

```bash
cd Data-Type-Cleaning
```

3. Install the required libraries:

```bash
pip install pandas numpy
```

4. Open the notebook using Jupyter:

```bash
jupyter notebook Data_Type_Cleaning.ipynb
```

5. Make sure `Employee.csv` is available in the working directory.
6. Run all notebook cells.
7. The cleaned dataset will be exported as `Cleaned_Employee_Dataset.csv`.

Alternatively, upload both the notebook and Employee.csv to Google Colab and run the cells.

## 📚 Key Learnings

- Understanding Python data types.
- Exploring datasets using Pandas.
- Converting object columns into category types.
- Working with numerical data types.
- Checking missing values.
- Comparing original and corrected data types.
- Exporting cleaned datasets.

## 🎓 Internship Details

- **Organization:** Veda Technology
- **Program:** AI & ML Internship
- **Task Number:** 24
- **Task Name:** Data Type Cleaning
- **Day:** 24

## 👨‍💻 Author

**Satya**

GitHub: [@satya77713](https://github.com/satya77713)

## 📝 Conclusion

This project provided practical experience in data type cleaning and preprocessing using Python and Pandas. By converting categorical columns into appropriate data types and verifying numerical columns, the Employee dataset was prepared for further data analysis and machine learning applications.

---

⭐ If you find this project useful, feel free to star the repository!
