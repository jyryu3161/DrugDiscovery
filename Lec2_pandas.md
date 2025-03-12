Here's the comprehensive pandas review notes translated clearly and neatly into English:

---

# 🐼 **Pandas Core Syntax & Examples**

## ✅ **Step 1: Importing pandas Library**

```python
import pandas as pd
```

---

## ✅ **Step 2: Loading External Dataset (CSV file)**

We'll use the **Titanic dataset** as an example.

```python
url = "https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv"

# Read CSV data
df = pd.read_csv(url)

# Check first 5 rows
print(df.head())
```

### **Main Columns Explained:**
- **PassengerId:** Passenger identifier
- **Survived:** Survival status (0 = died, 1 = survived)
- **Pclass:** Passenger class (1 = First class, 2 = Second class, 3 = Third class)
- **Name:** Passenger’s name
- **Sex:** Gender
- **Age:** Age of passenger
- **Fare:** Ticket fare
- **Embarked:** Port of embarkation

---

## ✅ **Step 3: Basic Data Exploration**

```python
# Check dataset shape (rows, columns)
print(df.shape)

# Column info and data types
print(df.info())

# Basic statistics of numeric columns
print(df.describe())
```

---

## ✅ **Step 4: Selecting Data (Basic)**

### Selecting columns
```python
# Select a single column
print(df['Name'])

# Select multiple columns
print(df[['Name', 'Age', 'Survived']].head())
```

### Selecting rows
```python
# Select first row
print(df.iloc[0])

# Select first 5 rows
print(df.head())
```

### Slicing rows and columns
```python
# First 10 rows
print(df[:10])

# Specific rows and columns
print(df.loc[0:5, ['Name', 'Age', 'Sex']])
```

---

## ✅ **Step 5: Filtering Data by Conditions**

### Single condition
```python
# Passengers younger than 20
young_passengers = df[df['Age'] < 20]
print(young_passengers.head())
```

### Multiple conditions
```python
# Passengers older than 60 OR fare greater than $100 (OR condition)
special_passengers = df[(df['Age'] >= 60) | (df['Fare'] >= 100)]
print(special_passengers.head())
```

---

## ✅ **Step 6: Adding and Removing Columns**

### Adding new column
```python
# Add "FamilySize" column
df['FamilySize'] = df['SibSp'] + df['Parch'] + 1
print(df[['Name', 'FamilySize']].head())
```

### Removing a column
```python
# Remove "PassengerId" column
df.drop('PassengerId', axis=1, inplace=True)
print(df.head())
```

---

## ✅ **Step 7: Handling Missing Values**

### Checking missing values
```python
print(df.isnull().sum())
```

### Filling missing values
```python
# Fill missing "Age" values with mean
mean_age = df['Age'].mean()
df['Age'].fillna(mean_age, inplace=True)

```

---

## ✅ **Step 8: Groupby Analysis**

`groupby` allows grouping data based on one or more categories to perform statistical analysis.

### Basic syntax:
```python
# df.groupby(['Column(s)'])['Target Column'].aggregation()
```

### **Example 1: Survival Rate by Gender**
```python
sex_survival_rate = df.groupby('Sex')['Survived'].mean()
print(sex_survival_rate)
```

### **Example 2: Average Fare by Passenger Class**
```python
class_fare = df.groupby('Pclass')['Fare'].mean()
print(class_fare)
```

### **Example 3: Survival Rate by Class and Gender (Multi-level Groupby)**
```python
class_sex_survival = df.groupby(['Pclass', 'Sex'])['Survived'].mean()
print(class_sex_survival)
for each_class, each_df in df.groupby('Pclass'):
    print(each_class)
    print(each_df)
```

---

## ✅ **Step 9: Converting Groupby Result to DataFrame**
```python
result_df = class_sex_survival.reset_index()
print(result_df)
```

---

## ✅ **Step 10: Exporting Results to CSV**
```python
result_df.to_csv('titanic_groupby_result.csv', index=False)
```
