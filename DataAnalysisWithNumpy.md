=== Shape and Dimensions ===

Gives the number of rows and columns of an array.

Example
```
import numpy as np
arr = np.random.randint(1, 100, size=(10, 5))
print(arr.shape)

```
=== Reshape ===

Used to change the shape of an array without changing its data.

Example:
```
b = arr.reshape(5, 10)
print(b.shape, b.ndim)
print(b)

```

=== Flatten and Ravel ===

flatten() returns a copy.

ravel() returns a view (changes affect the original array).

Example:
```
flatten = b.flatten()
print(flatten.ndim)
print(flatten)

column_wise_flattening = np.ravel(b, order='C')
print(column_wise_flattening)

```

=== Concatenate (Row-wise & Column-wise) ===

Join two arrays either vertically (rows) or horizontally (columns).

Example:
```
a = np.random.randint(1, 10, size=(2, 3))
b = np.random.randint(20, 30, size=(2, 3))

# Row-wise concatenation
con_row = np.concatenate((a, b), axis=0)
print(con_row)

# Column-wise concatenation
con_col = np.concatenate((a, b), axis=1)
print(con_col)

```

=== Transpose ===

Swaps rows and columns.

Example:
```
mat = np.array([[10, 20, 30],
                [30, 40, 50]])
print(mat.T)

```

=== Array Split ===

Split arrays into equal or unequal parts.

Example:
```
x = np.arange(12)
print(np.split(x, 3))        # equal parts
print(np.array_split(x, 5))  # unequal parts

```

=== Arithmetic Operations ===

Perform element-wise operations.

Example:
```
x = np.array([10, 8, 30, 100])
y = np.array([2, 3, 4, 5])

print(np.add(x, y))
print(x - y)
print(x * y)
print(x / y)
print(x % y)

```

=== Trigonometric Functions ===

Example:
```
print(np.sin(x))
print(np.cos(x))
print(np.rad2deg(x))

```

=== Logarithmic and Root Functions ===

Example:
```
x = np.array([10, 8, 16, 100])
print(np.log10(x))
print(np.log2(x))
print(np.sqrt(x))

```

=== Sum and Cumulative Sum ===

Example:

```
print(np.sum(x))
print(np.cumsum(x))

```

=== Broadcasting ===

Allows operations between arrays of different shapes.

Example:

```
matrix = np.array([[10, 20, 30],
                   [30, 40, 50]])
vector = np.array([1, 2, 3])

print(matrix + vector)

```

=== Logical Functions ===

Used for element-wise logical comparison.

Example:

```
x = np.array([10, 8, 16, 100])
y = np.array([2, 3, 16, 5])

print(x > y)
print(x == y)
print(np.all(x > y))
print(np.any(x == y))

```

=== Sorting (inplace and copy) ===

Example:
```
z = x.copy()
z.sort()
print(z)            # inplace sorted
print(np.sort(x))   # returns a new sorted array

```

=== 2D Array Sorting ===

Example:

```
arr2d = np.array([[10, 3, 5],
                  [8, 4, 9]])

print(np.sort(arr2d, axis=1))  # sort by row
print(np.sort(arr2d, axis=0))  # sort by column

```

=== Searching (Condition-based) ===

Example:

```
print(np.where(x == 8))
print(np.where(x > 8, x, 0))

mat = np.array([[10, 3, 5],
                [8, 4, 9]])

print(np.where(mat > 8))
print(np.where(mat > 8, mat, 0))

```

=== argmax & argmin ===

Example:

```
print(np.argmax(x))  # index of max element
print(np.argmin(x))  # index of min element

```

=== Random Numbers (randint) ===

Example:

```
r = np.random.randint(1, 10, size=(3, 3))
print(r)

```
=== Reading from CSV (genfromtxt) ===

Example:

```
# Suppose data.csv has numeric data
data = np.genfromtxt('data.csv', delimiter=',', skip_header=1)
print(data)

```

=== Mean, Standard Deviation, Correlation Coefficient ===

Example:

```
arr = np.array([1, 2, 3, 4, 5])
print(np.mean(arr))
print(np.std(arr))
print(np.corrcoef(arr))

```

=== Matrix Dot Product and Trace ===

Example:
```
a = np.array([[1, 2],
              [3, 4]])
b = np.array([[5, 6],
              [7, 8]])

print(np.dot(a, b))  # matrix multiplication
print(np.trace(a))   # sum of diagonal elements

```

