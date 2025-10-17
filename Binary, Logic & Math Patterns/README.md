## 1: Binary triangle (1-0 pattern)

**✅ Python Code**

```python
# Binary Triangle Pattern (1-0 Pattern)

n = 5

for i in range(1, n + 1):
    for j in range(1, i + 1):
        # Alternate 1 and 0 based on position
        if (i + j) % 2 == 0:
            print("1", end=" ")
        else:
            print("0", end=" ")
    print()
```

**✅ Explanation**

1. The triangle grows with **1, 2, 3, … n** elements per row.
2. The **sum of row and column indices `(i + j)`** decides whether to print **1 or 0**:

   * If even → `1`
   * If odd → `0`
3. This creates a **binary checker-like pattern** inside a triangle.


**✅ Output (n = 5)**

```
1
0 1
1 0 1
0 1 0 1
1 0 1 0 1
```

---

## 2: Alternating binary square (like chessboard)

**✅ Python Code**

```python
# Alternating Binary Square (Chessboard Pattern)

n = 6  # size of square

for i in range(n):
    for j in range(n):
        # alternate 1 and 0
        if (i + j) % 2 == 0:
            print("1", end=" ")
        else:
            print("0", end=" ")
    print()
```


**✅ Explanation**

1. **Grid size = n × n**.
2. Use **(row + column) % 2** to decide value:

   * Even → `1`
   * Odd → `0`
3. This creates a **checkerboard/chessboard effect**.


**✅ Output (n = 6)**

```
1 0 1 0 1 0
0 1 0 1 0 1
1 0 1 0 1 0
0 1 0 1 0 1
1 0 1 0 1 0
0 1 0 1 0 1
```

---

## 3: Checkerboard pattern with stars

**✅ Python Code**

```python
# Checkerboard Pattern with Stars

n = 6  # size of the square

for i in range(n):
    for j in range(n):
        if (i + j) % 2 == 0:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

**✅ Explanation**

1. **Grid size = n × n**.
2. Use `(row + column) % 2` to alternate:

   * Even → `*`
   * Odd → space `" "`
3. This produces a **checkerboard effect** with stars.


**✅ Output (n = 6)**

```
*   *   *  
  *   *   *
*   *   *  
  *   *   *
*   *   *  
  *   *   *
```

---

## 4: Magic square matrix

**✅ Python Code**

```python
# Magic Square Matrix (Odd Order)
n = 3  # size (odd number)

magic_square = [[0] * n for _ in range(n)]

i, j = 0, n // 2  # start position (first row, middle column)

for num in range(1, n*n + 1):
    magic_square[i][j] = num

    # Move up and right
    new_i = (i - 1) % n
    new_j = (j + 1) % n

    if magic_square[new_i][new_j]:  # already filled
        i = (i + 1) % n
    else:
        i, j = new_i, new_j

# Print the magic square
for row in magic_square:
    print(row)
```


**✅ Explanation**

1. Works for **odd-order magic squares**.
2. Start at **first row, middle column**.
3. Place numbers **1 → n²**:

   * Move **up and right**.
   * If the cell is filled → move **down instead**.
4. All rows, columns, and diagonals sum to **n*(n²+1)/2**.


## ✅ Output (3×3 Magic Square)

```
[8, 1, 6]
[3, 5, 7]
[4, 9, 2]
```

---
## 5: Prime-check matrix (star if prime)

**✅ Python Code**

```python
# Prime-Check Matrix with Stars

n = 5  # size of matrix

def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            return False
    return True

num = 1
for i in range(n):
    for j in range(n):
        if is_prime(num):
            print("*", end=" ")
        else:
            print(num, end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. Create a **function `is_prime`** to check if a number is prime.
2. Fill the matrix with numbers **1 → n²**.
3. If the number is prime → print `*`, else print the number.
4. This produces a **prime-checked star matrix**.


**✅ Output (n = 5)**

```
1 * * 4 * 
6 * 8 9 * 
11 * 13 14 15 
16 * 18 19 20 
* 22 23 24 25 
```

*(Stars `*` replace primes: 2, 3, 5, 7, 11, 13, 17, 19, 23…)*

---
## 6: Spiral binary filling

**✅ Python Code**

```python
# Spiral Binary Filling

n = 5  # size of matrix
matrix = [[0 for _ in range(n)] for _ in range(n)]

top, bottom, left, right = 0, n - 1, 0, n - 1
binary = 1  # start with 1

while top <= bottom and left <= right:
    # Left → Right
    for i in range(left, right + 1):
        matrix[top][i] = binary
        binary = 1 - binary  # alternate 0 ↔ 1
    top += 1

    # Top → Bottom
    for i in range(top, bottom + 1):
        matrix[i][right] = binary
        binary = 1 - binary
    right -= 1

    # Right → Left
    for i in range(right, left - 1, -1):
        matrix[bottom][i] = binary
        binary = 1 - binary
    bottom -= 1

    # Bottom → Top
    for i in range(bottom, top - 1, -1):
        matrix[i][left] = binary
        binary = 1 - binary
    left += 1

# Print the matrix
for row in matrix:
    print(' '.join(map(str, row)))
```


**✅ Explanation**

1. Create an `n × n` matrix initialized with 0.
2. Use **four boundaries** (`top`, `bottom`, `left`, `right`) to control the spiral.
3. Fill the matrix in **clockwise spiral order**, alternating `1` and `0` using `binary = 1 - binary`.
4. Continue until all cells are filled.


**✅ Output (n = 5)**

```
1 0 1 0 1
0 0 1 1 0
1 1 0 0 1
0 0 1 1 0
1 0 1 0 1
```

---

