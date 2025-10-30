
# 🧠 NumPy Complete Cheat Sheet for Data Analysis & Gen AI

---

## 1️⃣ Importing NumPy

**Input:**
```python
import numpy as np
```
**Output:**
No output (imports the library).

**Explanation:**
`np` is the standard alias used for NumPy. It allows you to access all its functions easily.

---

## 2️⃣ Creating Arrays

**Input:**
```python
arr = np.array([1, 2, 3, 4])
arr2d = np.array([[1, 2], [3, 4]])
```
**Output:**
```
[1 2 3 4]
[[1 2]
 [3 4]]
```

**Explanation:**
`np.array()` converts a list into a NumPy array (1D or 2D).

---

## 3️⃣ Using arange and linspace

**Input:**
```python
np.arange(0, 10, 2)
np.linspace(0, 1, 5)
```
**Output:**
```
[0 2 4 6 8]
[0.   0.25 0.5  0.75 1.  ]
```

**Explanation:**
- `arange(start, stop, step)` creates sequences.
- `linspace(start, stop, num)` creates evenly spaced values.

---

## 4️⃣ Array Information

**Input:**
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
arr.shape, arr.ndim, arr.size, arr.dtype
```
**Output:**
```
((2, 3), 2, 6, dtype('int64'))
```

**Explanation:**
Shows the shape, dimensions, total size, and data type of the array.

---

## 5️⃣ Reshaping Arrays

**Input:**
```python
arr = np.arange(6)
arr.reshape(2, 3)
```
**Output:**
```
[[0 1 2]
 [3 4 5]]
```

**Explanation:**
`reshape()` changes the structure of the array.

---

## 6️⃣ Basic Mathematical Operations

**Input:**
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b, a - b, a * b, a / b, a ** 2
```
**Output:**
```
(array([5, 7, 9]), array([-3, -3, -3]), array([ 4, 10, 18]), array([0.25, 0.4 , 0.5 ]), array([1, 4, 9]))
```

**Explanation:**
Performs element-wise operations between arrays.

---

## 7️⃣ Aggregate Functions

**Input:**
```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
np.sum(arr), np.mean(arr), np.std(arr), np.min(arr), np.max(arr)
```
**Output:**
```
(21, 3.5, 1.707825127659933, 1, 6)
```

**Explanation:**
Statistical functions to summarize data.

---

## 8️⃣ Axis Operations

**Input:**
```python
np.sum(arr, axis=0), np.sum(arr, axis=1)
```
**Output:**
```
(array([5, 7, 9]), array([ 6, 15]))
```

**Explanation:**
`axis=0` → column-wise, `axis=1` → row-wise operation.

---

## 9️⃣ Array Indexing & Slicing

**Input:**
```python
arr = np.array([10, 20, 30, 40, 50])
arr[1:4], arr[-1]
```
**Output:**
```
(array([20, 30, 40]), 50)
```

**Explanation:**
Select specific elements or ranges from arrays.

---

## 🔟 Boolean Indexing

**Input:**
```python
arr = np.array([10, 25, 30, 45])
arr[arr > 20]
```
**Output:**
```
array([25, 30, 45])
```

**Explanation:**
Filters elements based on conditions.

---

## 11️⃣ Copy vs View

**Input:**
```python
a = np.array([1, 2, 3])
b = a.copy()
c = a.view()
a[0] = 100
(b, c)
```
**Output:**
```
(array([1, 2, 3]), array([100, 2, 3]))
```

**Explanation:**
`copy()` → creates new memory, `view()` → shares same data.

---

## 12️⃣ Stacking Arrays

**Input:**
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
np.hstack((a, b)), np.vstack((a, b))
```
**Output:**
```
(array([1, 2, 3, 4, 5, 6]),
 array([[1, 2, 3],
        [4, 5, 6]]))
```

**Explanation:**
Stacks arrays horizontally or vertically.

---

## 13️⃣ Matrix Operations

**Input:**
```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])
np.dot(A, B), np.transpose(A), np.linalg.inv(A)
```
**Output:**
```
(array([[19, 22],
       [43, 50]]), 
array([[1, 3],
       [2, 4]]), 
array([[-2. ,  1. ],
       [ 1.5, -0.5]]))
```

**Explanation:**
Matrix operations are crucial in Gen AI (used in neural networks).

---

## 14️⃣ Random Numbers

**Input:**
```python
np.random.seed(42)
np.random.rand(2, 3)
```
**Output:**
```
array([[0.37454012, 0.95071431, 0.73199394],
       [0.59865848, 0.15601864, 0.15599452]])
```

**Explanation:**
Generates random numbers (used for weight initialization).

---

## 15️⃣ Flattening Arrays

**Input:**
```python
arr = np.array([[1, 2], [3, 4]])
arr.flatten()
```
**Output:**
```
array([1, 2, 3, 4])
```

**Explanation:**
Converts multi-dimensional array to 1D.

---

## 16️⃣ Broadcasting

**Input:**
```python
a = np.array([[1, 2, 3], [4, 5, 6]])
b = np.array([10, 20, 30])
a + b
```
**Output:**
```
array([[11, 22, 33],
       [14, 25, 36]])
```

**Explanation:**
NumPy automatically expands smaller arrays to match dimensions.

---

## 17️⃣ Save and Load Data

**Input:**
```python
arr = np.array([1, 2, 3])
np.save('data.npy', arr)
np.load('data.npy')
```
**Output:**
```
array([1, 2, 3])
```

**Explanation:**
You can save and reload NumPy arrays easily.

---

## 18️⃣ Handling Missing Values

**Input:**
```python
arr = np.array([1, np.nan, 3, 4])
np.isnan(arr), np.nanmean(arr)
```
**Output:**
```
(array([False,  True, False, False]), 2.6666666666666665)
```

**Explanation:**
Detects and handles NaN values (missing data).

---

## 19️⃣ Vectorization

**Input:**
```python
arr = np.arange(1, 6)
arr ** 2
```
**Output:**
```
array([ 1,  4,  9, 16, 25])
```

**Explanation:**
Performs fast, loop-free operations on arrays.

---

## 20️⃣ Normalizing Data

**Input:**
```python
data = np.array([10, 20, 30, 40])
(data - np.mean(data)) / np.std(data)
```
**Output:**
```
array([-1.34164079, -0.4472136 ,  0.4472136 ,  1.34164079])
```

**Explanation:**
Normalization scales data, used in ML & Gen AI models.

---
