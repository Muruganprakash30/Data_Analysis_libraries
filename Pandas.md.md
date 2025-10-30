
# 🐼 Pandas Cheat Sheet with Examples, Input & Output

A complete reference for **Pandas** — essential for **Data Analysis** and **Gen AI data preprocessing**.

---

## 📦 1. Importing Pandas

```python
import pandas as pd
```
**Output:**  
(No output — imports pandas library)

---

## 📋 2. Creating Data Structures

### 🧱 Series
```python
s = pd.Series([10, 20, 30, 40])
print(s)
```
**Output:**
```
0    10
1    20
2    30
3    40
dtype: int64
```

---

### 🧱 DataFrame
```python
data = {'Name': ['John', 'Anna', 'Sam'],
        'Age': [28, 24, 35]}
df = pd.DataFrame(data)
print(df)
```
**Output:**
```
   Name  Age
0  John   28
1  Anna   24
2   Sam   35
```

---

## 📂 3. Reading & Writing Data

### Read CSV
```python
df = pd.read_csv('data.csv')
```

### Write CSV
```python
df.to_csv('output.csv', index=False)
```

---

## 🔍 4. Data Exploration

```python
df.head()      # First 5 rows
df.tail()      # Last 5 rows
df.info()      # Summary of data
df.describe()  # Statistical summary
df.shape       # (rows, columns)
df.columns     # Column names
```

---

## 🧹 5. Data Cleaning

```python
df.isnull().sum()
df.fillna(0, inplace=True)
df.dropna(inplace=True)
df.rename(columns={'Age': 'Years'}, inplace=True)
df.drop_duplicates(inplace=True)
```

---

## 🔢 6. Selecting Data

```python
df['Name']
df[['Name','Age']]
df.iloc[0]
df.loc[1]
df.iloc[0:2]
```

---

## 🎯 7. Conditional Filtering

```python
df[df['Age'] > 25]
```
**Output:**
```
   Name  Age
0  John   28
2   Sam   35
```

---

## 🔄 8. Sorting Data

```python
df.sort_values(by='Age', ascending=False)
```

---

## 🧮 9. Aggregation & Grouping

```python
df.groupby('Name')['Age'].mean()
```
**Output:**
```
Name
Anna    24.0
John    28.0
Sam     35.0
Name: Age, dtype: float64
```

---

## 📊 10. Adding & Modifying Columns

```python
df['Age_in_10yrs'] = df['Age'] + 10
```
**Output:**
```
   Name  Age  Age_in_10yrs
0  John   28            38
1  Anna   24            34
2   Sam   35            45
```

---

## 🧾 11. Merging & Joining DataFrames

```python
df1 = pd.DataFrame({'ID':[1,2,3],'Name':['A','B','C']})
df2 = pd.DataFrame({'ID':[1,2,4],'Score':[90,80,70]})
merged = pd.merge(df1, df2, on='ID', how='inner')
print(merged)
```
**Output:**
```
   ID Name  Score
0   1    A     90
1   2    B     80
```

---

## 📆 12. Working with Dates

```python
df['Date'] = pd.to_datetime(['2025-01-01','2025-02-01','2025-03-01'])
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
```

---

## 📈 13. Basic Statistics

```python
df['Age'].mean()
df['Age'].median()
df['Age'].std()
```
**Output Example:**
```
mean = 29.0
median = 28.0
std = 5.6
```

---

## 📊 14. Data Visualization

```python
import matplotlib.pyplot as plt

df['Age'].plot(kind='bar')
plt.show()
```

---

## 🤖 15. Useful in Gen AI Data Processing

| Task | Pandas Usage |
|------|---------------|
| Text preprocessing | Clean text data, remove nulls, apply string operations |
| Dataset merging | Combine multiple CSVs or JSONs for fine-tuning data |
| Data summarization | Compute statistics (mean, std, etc.) for embeddings |
| Filtering noisy data | Remove irrelevant or outlier data points |

---

## 🧾 Summary Table

| Function | Purpose |
|-----------|----------|
| `read_csv()` | Load data from CSV |
| `head()` | View top records |
| `isnull()` | Check missing data |
| `fillna()` | Replace missing values |
| `dropna()` | Remove null rows |
| `groupby()` | Group and aggregate data |
| `sort_values()` | Sort dataset |
| `merge()` | Join DataFrames |
| `to_csv()` | Save data to file |

---

✅ **Pandas helps you clean, process, and prepare data before feeding it into ML or Gen AI models.**
