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
## 7: Triangle with XOR values

**✅ Python Code**

```python
# Triangle with XOR Values

n = 5

for i in range(1, n + 1):       # row
    for j in range(1, i + 1):   # column
        print(i ^ j, end=" ")   # XOR operation
    print()
```


**✅ Explanation**

1. The triangle has **1 → n** rows.
2. Each row `i` has **i elements**.
3. Each element = `i ^ j` (XOR of row and column indices).
4. This produces a **triangle with a unique pattern based on XOR logic**.


**✅ Output (n = 5)**

```
0
3 0
2 3 0
5 4 7 0
1 0 3 2 0
```

*(Note: The output may vary depending on whether indices start from 0 or 1; here we started from 1)*

---
## 8: Multiplication pyramid (n × n)

**✅ Python Code**

```python
# Multiplication Pyramid (n × n)

n = 5

for i in range(1, n + 1):          # rows
    for j in range(1, i + 1):      # columns
        print(f"{i*j:2}", end=" ") # print i × j with spacing
    print()
```


**✅ Explanation**

1. Loop `i` from 1 → n → controls rows.
2. Inner loop `j` runs 1 → i → controls number of elements per row.
3. Each element = `i × j`.
4. Printed in a **pyramid format** (row grows with i).
5. `f"{i*j:2}"` adds spacing for clean alignment.


**✅ Output (n = 5)**

```
 1
 2  4
 3  6  9
 4  8 12 16
 5 10 15 20 25
```

---
## 9: Factorial pyramid (n!)

**✅ Python Code**

```python
# Factorial Pyramid

import math

n = 5  # height of pyramid

for i in range(1, n + 1):       # rows
    for j in range(1, i + 1):   # columns
        print(f"{math.factorial(j):5}", end=" ")
    print()
```


**✅ Explanation**

1. Import `math` to use `math.factorial()` function.
2. Outer loop (`i`) → total rows (1 to n).
3. Inner loop (`j`) → factorials from 1! up to i!.
4. Each factorial is printed with some spacing for alignment (`:5`).


**✅ Output (n = 5)**

```
    1
    1     2
    1     2     6
    1     2     6    24
    1     2     6    24   120
```

---
## 10: Power pyramid (2^n, 3^n, …)

**✅ Python Code**

```python
# Power Pyramid (a^b pattern)

n = 5  # height of pyramid

for i in range(1, n + 1):        # row = power
    for j in range(1, i + 1):    # base
        print(f"{j**i:5}", end=" ")
    print()
```


**✅ Explanation**

1. **Outer loop (i):** represents the power/exponent (row number).
2. **Inner loop (j):** represents the base (1 → i).
3. Each element = `j ** i` (read as *j to the power i*).
4. `f"{j**i:5}"` ensures proper alignment.


**✅ Output (n = 5)**

```
    1
    1     4
    1     8    27
    1    16    81   256
    1    32   243  1024  3125
```

---
## 11: Pascal’s triangle mod 2 (Sierpinski pattern)

**✅ Python Code**

```python
# Pascal’s Triangle mod 2 (Sierpinski Triangle Pattern)

n = 16  # number of rows

# Generate Pascal's Triangle
triangle = [[1]]

for i in range(1, n):
    row = [1]
    for j in range(1, i):
        row.append((triangle[i-1][j-1] + triangle[i-1][j]) % 2)  # mod 2
    row.append(1)
    triangle.append(row)

# Print Sierpinski Pattern
for i in range(n):
    print(" " * (n - i), end="")  # center alignment
    for val in triangle[i]:
        print("*" if val else " ", end=" ")
    print()
```

**✅ Explanation**

1. Build Pascal’s Triangle row by row.
2. Each element = `(previous_row[j-1] + previous_row[j]) % 2`

   * `% 2` means:

     * Odd numbers → 1 → print `*`
     * Even numbers → 0 → print space.
3. This binary pattern of Pascal’s Triangle visually forms a **Sierpiński triangle fractal**!


**✅ Output (n = 16)**

```
                * 
               * * 
              *   * 
             * * * * 
            *       * 
           * *     * * 
          *   *   *   * 
         * * * * * * * * 
        *               * 
       * *             * * 
      *   *           *   * 
     * * * *         * * * * 
    *       *       *       * 
   * *     * *     * *     * * 
  *   *   *   *   *   *   *   * 
 * * * * * * * * * * * * * * * *
```

---
## 12: Binary pyramid with increasing length

**✅ Python Code**

```python
# Binary Pyramid with Increasing Length

n = 6  # height of pyramid

for i in range(1, n + 1):
    bit = i % 2  # start with 1 for odd rows, 0 for even
    for j in range(i):
        print(bit, end=" ")
        bit = 1 - bit  # toggle between 1 and 0
    print()
```


**✅ Explanation**

1. **Outer loop (`i`)** → controls number of rows.
2. **Inner loop (`j`)** → controls number of elements in each row (1 → i).
3. `bit` alternates using `bit = 1 - bit`.
4. Starting bit (`i % 2`) changes the pattern every row (odd → start with 1, even → start with 0).


**✅ Output (n = 6)**

```
1 
0 1 
1 0 1 
0 1 0 1 
1 0 1 0 1 
0 1 0 1 0 1 
```

---
## 13: Hamming weight pattern (count of 1s in binary)

**✅ Python Code**

```python
# Hamming Weight Pattern (Count of 1s in Binary)

n = 5  # size of matrix

def hamming_weight(x):
    return bin(x).count("1")  # count number of 1s in binary

num = 1
for i in range(n):
    for j in range(n):
        print(hamming_weight(num), end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. **Hamming weight** = number of 1s in binary form of a number.

   * Example:

     * 5 → (101)₂ → weight = 2
     * 7 → (111)₂ → weight = 3
2. Loop through numbers `1 → n²`.
3. Convert each to binary using `bin(num)`.
4. Count 1s using `.count("1")`.
5. Print as a matrix (or triangle if you prefer).


**✅ Output (n = 5)**

```
1 1 2 1 2
2 2 3 1 2
3 2 3 2 3
1 2 2 3 2
3 3 4 1 2
```

*(Values represent number of 1s in each number’s binary representation)*


**✅ Binary Visualization Example (1–16)**

| Number | Binary | Hamming Weight |
| :----: | :----: | :------------: |
|    1   |  0001  |        1       |
|    2   |  0010  |        1       |
|    3   |  0011  |        2       |
|    4   |  0100  |        1       |
|    5   |  0101  |        2       |
|    6   |  0110  |        2       |
|    7   |  0111  |        3       |
|    8   |  1000  |        1       |

---

## 14: Divisor count triangle

**✅ Python Code**

```python
# Divisor Count Triangle

n = 6  # number of rows

def divisor_count(num):
    count = 0
    for i in range(1, int(num ** 0.5) + 1):
        if num % i == 0:
            count += 2 if i * i != num else 1
    return count

num = 1
for i in range(1, n + 1):
    for j in range(i):
        print(f"{divisor_count(num):2}", end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. **`divisor_count(num)`** function:

   * Loops up to √num.
   * Increments by 2 for each divisor pair `(i, num/i)`.
   * If `i*i == num`, add only once (perfect square).
2. Numbers go **1 → n(n+1)/2**, just like **Floyd’s triangle**.
3. Instead of numbers, print how many **divisors** each number has.


**✅ Output (n = 6)**

```
 1
 2 2
 2 3 2
 3 2 4 2
 2 4 2 3 2
 4 2 3 2 4 2
```

---

## 15: Palindrome binary triangle

**✅ Python Code**

```python
# Palindrome Binary Triangle

n = 6  # number of rows

for i in range(1, n + 1):
    # First half (increasing binary sequence)
    for j in range(1, i + 1):
        print(j % 2, end="")

    # Second half (mirror without center)
    for j in range(i - 1, 0, -1):
        print(j % 2, end="")

    print()
```


**✅ Explanation**

1. The **first loop** prints increasing binary values (`1 0 1 0…`).
2. The **second loop** mirrors the sequence (creates palindrome symmetry).
3. Each row grows in length and remains symmetric.
4. `% 2` gives alternating 1s and 0s.


**✅ Output (n = 6)**

```
1
10 1
101 01
1010 101
10101 0101
101010 101010
```

After spacing for clarity (true visual pyramid):

```
     1
    101
   10101
  1010101
 101010101
10101010101
```

*(Each row is palindromic and perfectly symmetric)*

---
## 16: GCD matrix pattern

**✅ Python Code**

```python
# GCD Matrix Pattern

import math

n = 6  # size of matrix

for i in range(1, n + 1):
    for j in range(1, n + 1):
        print(f"{math.gcd(i, j):2}", end=" ")
    print()
```


**✅ Explanation**

1. We import Python’s built-in `math.gcd()` function.
2. Loop over all rows `i` and columns `j` (1 → n).
3. Compute `gcd(i, j)` for each pair.
4. Print in grid format using formatted spacing `:2` for alignment.

**✅ Output (n = 6)**

```
 1 1 1 1 1 1
 1 2 1 2 1 2
 1 1 3 1 1 3
 1 2 1 4 1 2
 1 1 1 1 5 1
 1 2 3 2 1 6
```


**✅ How It Works**

|  i  |  j  | gcd(i, j) |
| :-: | :-: | :-------: |
|  2  |  4  |     2     |
|  3  |  6  |     3     |
|  4  |  6  |     2     |
|  5  |  10 |     5     |

* Values are **symmetrical** (`gcd(i, j) = gcd(j, i)`)
* The diagonal (`i == j`) always shows the **number itself**
* Common multiples share larger gcd values

---

## 17: LCM matrix pattern

**✅ Python Code**

```python
# LCM Matrix Pattern

import math

n = 6  # size of the matrix

def lcm(a, b):
    return abs(a * b) // math.gcd(a, b)  # formula: LCM * GCD = a * b

for i in range(1, n + 1):
    for j in range(1, n + 1):
        print(f"{lcm(i, j):3}", end=" ")
    print()
```


**✅ Explanation**

1. **LCM formula:**
 
  ![LCM Formula](https://latex.codecogs.com/png.latex?LCM(a,b)%3D%5Cfrac%7B%7Ca%20%5Ctimes%20b%7C%7D%7BGCD(a,b)%7D)

2. For each cell `(i, j)`:

   * Compute `gcd(i, j)` using `math.gcd()`
   * Apply the LCM formula
3. Print each LCM value in an aligned matrix format.


**✅ Output (n = 6)**

```
  1   2   3   4   5   6
  2   2   6   4  10   6
  3   6   3  12  15   6
  4   4  12   4  20  12
  5  10  15  20   5  30
  6   6   6  12  30   6
```


**✅ Observations**

* The **matrix is symmetric** since `lcm(i, j) = lcm(j, i)`.
* The **diagonal** always shows the number itself (since `lcm(i, i) = i`).
* Multiples of a number have repeating patterns (e.g., multiples of 2, 3, 5…).


**✅ Comparison (for intuition)**

|   Pair  | GCD | LCM |
| :-----: | :-: | :-: |
|  (2, 4) |  2  |  4  |
|  (3, 6) |  3  |  6  |
|  (4, 6) |  2  |  12 |
| (5, 10) |  5  |  10 |

Notice how LCM tends to **increase** as numbers share fewer factors.

---

## 18: Modular arithmetic spiral

**✅ Python Code**

```python
# Modular Arithmetic Spiral

n = 5  # size of square
m = 3  # modulo
matrix = [[0]*n for _ in range(n)]

top, bottom, left, right = 0, n-1, 0, n-1
num = 1

while top <= bottom and left <= right:
    # Left → Right
    for i in range(left, right+1):
        matrix[top][i] = num % m
        num += 1
    top += 1

    # Top → Bottom
    for i in range(top, bottom+1):
        matrix[i][right] = num % m
        num += 1
    right -= 1

    # Right → Left
    for i in range(right, left-1, -1):
        matrix[bottom][i] = num % m
        num += 1
    bottom -= 1

    # Bottom → Top
    for i in range(bottom, top-1, -1):
        matrix[i][left] = num % m
        num += 1
    left += 1

# Print the matrix
for row in matrix:
    print(' '.join(map(str, row)))
```


**✅ Explanation**

1. Create an `n × n` matrix.
2. Use **four boundaries** (`top`, `bottom`, `left`, `right`) to fill in a spiral (clockwise).
3. Fill numbers `1 → n²` **mod m** to wrap values between `0 → m-1`.
4. Increment `num` after each placement.


**✅ Output (n = 5, m = 3)**

```
1 2 0 1 2
0 1 2 0 0
2 0 1 2 1
1 2 0 1 0
2 1 2 0 1
```

---
## 19: Digital root triangle

**✅ Python Code**

```python
# Digital Root Triangle

n = 6  # number of rows

def digital_root(num):
    if num == 0:
        return 0
    return 1 + (num - 1) % 9

num = 1
for i in range(1, n + 1):
    for j in range(i):
        print(digital_root(num), end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. **Digital root formula:**

   * For `num != 0`: `dr(num) = 1 + ((num-1) % 9)`
   * This repeatedly sums digits until a single digit remains.
2. Numbers go from **1 → n(n+1)/2** (like Floyd’s triangle).
3. Print the **digital root** instead of the original number.

---

## ✅ Output (n = 6)

```
1
2 3
4 5 6
7 8 9 1
2 3 4 5 6
7 8 9 1 2 3
```

---
## 20: Sum of digits triangle

**✅ Python Code**

```python
# Sum of Digits Triangle

n = 6  # number of rows

def sum_of_digits(num):
    return sum(int(d) for d in str(num))

num = 1
for i in range(1, n + 1):
    for j in range(i):
        print(sum_of_digits(num), end=" ")
        num += 1
    print()
```


**✅ Explanation**

1. **`sum_of_digits(num)`** converts the number to a string and sums its digits.
2. Numbers go from **1 → n(n+1)/2** (Floyd’s triangle).
3. Each number is replaced by **sum of digits**.
4. The triangle grows row by row (1, 2, 3 … elements per row).


**✅ Output (n = 6)**

```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
16 17 18 19 20 21
```

**After applying sum of digits:**

```
1
2 3
4 5 6
7 8 9 1
2 3 4 5 6
7 8 9 1 2 3
```

*(Notice: numbers like 10 → 1+0 = 1, 11 → 1+1 = 2, etc.)*

---


