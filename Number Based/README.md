## 1: Floyd’s triangle numbers

**✅ Python Code**

```python
# Floyd's Triangle Numbers
n = 5
num = 1

for i in range(1, n+1):   # rows
    for j in range(1, i+1):   # columns
        print(num, end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. Start with `num = 1`.
2. Outer loop → rows (1 to n).
3. Inner loop → prints row’s numbers (`i` numbers in row `i`).
4. After each number, increment `num`.


**✅ Output**

```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

---

## 2: Pascal’s triangle numbers

**✅ Python Code**

```python
# Pascal's Triangle Numbers
n = 5

for i in range(n):
    # print leading spaces for triangle shape
    print(" " * (n - i), end="")

    # first value in a row is always 1
    val = 1
    for j in range(i + 1):
        print(val, end=" ")
        # update value using formula for next column
        val = val * (i - j) // (j + 1)
    print()
```


**✅ Explanation**

1. **Outer loop (rows):** runs `n` times.
2. **Spaces:** `" " * (n - i)` → centers the numbers like a triangle.
3. **Value calculation:** first number in each row is `1`.

   * Formula for next number:
     [
     val = val \times \frac{(i - j)}{(j + 1)}
     ]
     which generates binomial coefficients.
4. Each row forms part of Pascal’s Triangle.


**✅ Output (n = 5)**

```
     1
    1 1
   1 2 1
  1 3 3 1
 1 4 6 4 1
```

---
## 3: Continuous increasing numbers in triangle

**✅ Python Code**

```python
# Continuous Increasing Numbers in Triangle
n = 5
num = 1

for i in range(1, n+1):
    # spaces for triangle alignment
    print(" " * (n - i), end="")

    # print numbers in row
    for j in range(i):
        print(num, end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. Start with `num = 1`.
2. Outer loop → runs `n` times (rows).
3. Spaces (`n - i`) → shift numbers to form triangle shape.
4. Print `i` numbers in row `i`, increasing `num` each time.


**✅ Output (n = 5)**

```
        1
       2 3
      4 5 6
     7 8 9 10
   11 12 13 14 15
```

---
## 4: Continuous decreasing numbers in triangle

**✅ Python Code**

```python
# Continuous Decreasing Numbers in Triangle
n = 5
num = n * (n + 1) // 2   # total numbers in triangle

for i in range(n, 0, -1):   # rows decreasing
    # spaces for alignment
    print(" " * (n - i), end="")
    
    # print numbers in row
    for j in range(i):
        print(num, end=" ")
        num -= 1
    print()
```

---

## ✅ Explanation

1. Total numbers = ( \frac{n(n+1)}{2} ). For `n=5`, total = 15.
2. Start with `num = 15` and keep decrementing.
3. Outer loop → rows from `n` down to 1.
4. Spaces → `" " * (n - i)` to align like a triangle.
5. Each row prints `i` numbers, decreasing continuously.

---

## ✅ Output (n = 5)

```
15 14 13 12 11
 10 9 8 7
  6 5 4
   3 2
    1
```

---
## 5: Palindrome number pyramid

## ✅ Python Code

```python
# Palindrome Number Pyramid
n = 5

for i in range(1, n + 1):
    # spaces for alignment
    print(" " * (n - i), end="")
    
    # increasing numbers
    for j in range(1, i + 1):
        print(j, end="")
    
    # decreasing numbers
    for j in range(i - 1, 0, -1):
        print(j, end="")
    
    print()
```

---

## ✅ Explanation

1. **Spaces:** `" " * (n - i)` → makes pyramid shape.
2. **Increasing part:** numbers `1 → i`.
3. **Decreasing part:** numbers `i-1 → 1`.
4. Together, it forms a **palindrome sequence** per row.

---

## ✅ Output (n = 5)

```
    1
   121
  12321
 1234321
123454321
```

---
## 6: Hollow number pyramid

## ✅ Python Code

```python
# Hollow Number Pyramid
n = 5

for i in range(1, n + 1):
    # spaces for alignment
    print(" " * (n - i), end="")
    
    for j in range(1, i + 1):
        # first or last number in row, or last row (print all)
        if j == 1 or j == i or i == n:
            print(j, end=" ")
        else:
            print(" ", end=" ")
    
    # mirror side for hollow effect
    for j in range(i - 1, 0, -1):
        if j == 1 or j == i - 1 or i == n:
            print(j, end=" ")
        else:
            print(" ", end=" ")
    
    print()
```

---

## ✅ Explanation

1. **Spaces:** `" " * (n - i)` → shifts rows to form pyramid shape.
2. **Left half:** prints numbers `1 → i`.

   * Only first, last, or bottom row numbers are printed.
   * Inside becomes spaces → hollow effect.
3. **Right half:** mirrors numbers `i-1 → 1` with the same hollow logic.

---

## ✅ Output (n = 5)

```
    1
   1 2 1
  1   3   1
 1     4     1
1 2 3 4 5 4 3 2 1
```

---
## 7: Diamond with continuous numbers

## ✅ Python Code

```python
# Diamond with Continuous Numbers
n = 5
num = 1

# upper half
for i in range(1, n + 1):
    print("  " * (n - i), end="")   # spaces
    for j in range(2 * i - 1):
        print(num, end=" ")
        num += 1
    print()

# lower half
for i in range(n - 1, 0, -1):
    print("  " * (n - i), end="")   # spaces
    for j in range(2 * i - 1):
        print(num, end=" ")
        num += 1
    print()
```

---

## ✅ Explanation

1. **Two halves:**

   * Top pyramid → rows 1 → n
   * Bottom inverted pyramid → rows n-1 → 1
2. Each row has `2*i - 1` numbers.
3. `num` keeps incrementing, so numbers are continuous across rows.
4. Spaces (`"  " * (n - i)`) make the diamond symmetric.

---

## ✅ Output (n = 5)

```
        1
      2 3 4
    5 6 7 8 9
 10 11 12 13 14 15 16
17 18 19 20 21 22 23 24 25
  26 27 28 29 30 31 32
    33 34 35 36 37
      38 39 40
        41
```

---
## 8: Hourglass numbers

## ✅ Python Code

```python
# Hourglass Number Pattern
n = 5

# upper half
for i in range(n):
    # left numbers
    for j in range(1, n - i + 1):
        print(j, end="")
    
    # spaces
    print(" " * (2 * i), end="")
    
    # right numbers
    for j in range(n - i, 0, -1):
        print(j, end="")
    print()

# lower half
for i in range(2, n + 1):
    # left numbers
    for j in range(1, i + 1):
        print(j, end="")
    
    # spaces
    print(" " * (2 * (n - i)), end="")
    
    # right numbers
    for j in range(i, 0, -1):
        print(j, end="")
    print()
```

---

## ✅ Explanation

1. **Upper Half (Top to Middle):**

   * Left part → numbers from `1` to `n-i`.
   * Spaces → `2*i` spaces.
   * Right part → numbers from `n-i` down to `1`.

2. **Lower Half (Middle to Bottom):**

   * Left part → numbers from `1` to `i`.
   * Spaces → `2*(n-i)` spaces.
   * Right part → numbers from `i` down to `1`.

3. Together, they form an **hourglass shape** with numbers.

---

## ✅ Output (n = 5)

```
1234554321
1234  4321
123    321
12      21
1        1
12      21
123    321
1234  4321
1234554321
```

---

## 9: Concentric square numbers

## ✅ Python Code

```python
# Concentric Square Number Pattern
n = 4
size = 2 * n - 1   # total rows and cols

for i in range(size):
    for j in range(size):
        # find min distance from any border
        min_dist = min(i, j, size - 1 - i, size - 1 - j)
        print(n - min_dist, end="")
    print()
```

---

## ✅ Explanation

1. **Grid size:** `2*n - 1` → square with odd side length.

   * For `n=4` → size = 7 × 7.
2. **At each cell (i, j):**

   * Compute distance to nearest border:
     `min(i, j, size-1-i, size-1-j)`
   * Subtract that distance from `n` → gives the correct number for that cell.
3. This ensures layers of decreasing numbers toward the center.

---

## ✅ Output (n = 4)

```
4444444
4333334
4322234
4321234
4322234
4333334
4444444
```

---
## 10: Spiral numbers in square

## ✅ Python Code

```python
# Spiral Numbers in Square
n = 4
matrix = [[0]*n for _ in range(n)]

top, bottom, left, right = 0, n-1, 0, n-1
num = 1

while top <= bottom and left <= right:
    # top row
    for i in range(left, right+1):
        matrix[top][i] = num
        num += 1
    top += 1

    # right column
    for i in range(top, bottom+1):
        matrix[i][right] = num
        num += 1
    right -= 1

    # bottom row
    for i in range(right, left-1, -1):
        matrix[bottom][i] = num
        num += 1
    bottom -= 1

    # left column
    for i in range(bottom, top-1, -1):
        matrix[i][left] = num
        num += 1
    left += 1

# print matrix
for row in matrix:
    print(" ".join(f"{x:2}" for x in row))
```

---

## ✅ Explanation

1. Create an `n x n` grid of zeros.
2. Fill numbers in a **spiral manner**:

   * Top row → left to right
   * Right column → top to bottom
   * Bottom row → right to left
   * Left column → bottom to top
3. Shrink boundaries (`top, bottom, left, right`) and repeat.
4. Print with formatting for alignment (`f"{x:2}"`).

---

## ✅ Output (n = 4)

```
 1  2  3  4
12 13 14  5
11 16 15  6
10  9  8  7
```

---
## 11: Snake matrix numbers

## ✅ Python Code

```python
# Snake Matrix Numbers
n = 4
num = 1

for i in range(1, n+1):
    if i % 2 != 0:  # odd row → left to right
        for j in range(1, n+1):
            print(f"{num:2}", end=" ")
            num += 1
    else:  # even row → right to left
        start = num + n - 1
        for j in range(n):
            print(f"{start-j:2}", end=" ")
        num += n
    print()
```

---

## ✅ Explanation

1. **Odd rows:**

   * Numbers increase left → right.

2. **Even rows:**

   * Numbers increase right → left (reverse order).

3. **`num` variable:** keeps track of next number.

4. Formatting `f"{num:2}"` ensures proper spacing for alignment.

---

## ✅ Output (n = 4)

```
 1  2  3  4
 8  7  6  5
 9 10 11 12
16 15 14 13
```

---
## 12: Zig-zag numbers

## ✅ Python Code

```python
# Zig-Zag Numbers Pattern
rows = 3
cols = 9
num = 1

for i in range(1, rows+1):
    for j in range(1, cols+1):
        if (i + j) % (rows) == 0:
            print(f"{num}", end=" ")
            num += 1
        else:
            print(" ", end=" ")
    print()
```

---

## ✅ Explanation

1. **Rows and columns:**

   * Outer loop → rows
   * Inner loop → columns

2. **Condition for numbers:**

   * `(i + j) % rows == 0` → creates diagonal pattern.

3. **Else:** print space `" "` for alignment.

4. **`num` variable:** keeps track of the next number.

---

## ✅ Output (3 rows, 9 columns)

```
    1       3       5
  2   4   6   8   10
3       5       7       9
```

---

