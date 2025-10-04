## 1: Solid square star pattern

**✅ Python Code**

```python
# Solid Square Star Pattern
n = 5

for i in range(n):
    print("*" * n)
```

**✅ Explanation**

* We take `n = 5` (rows and columns).
* Outer loop → runs `n` times (rows).
* Each row prints `n` stars (`*`).

**✅ Output**

```
*****
*****
*****
*****
*****
```
---

## 2: Hollow square star pattern

**✅ Python Code**

```python
# Hollow Square Star Pattern
n = 5

for i in range(1, n + 1):      # Loop through rows
    for j in range(1, n + 1):  # Loop through columns
        if i == 1 or i == n or j == 1 or j == n:
            print("*", end="")
        else:
            print(" ", end="")
    print()  # Move to next line
```


**✅ Explanation**

1. **Outer loop (`i`)** → Controls rows from 1 to n.
2. **Inner loop (`j`)** → Controls columns from 1 to n.
3. **Condition**:

   * Print `*` if:

     * `i == 1` → first row
     * `i == n` → last row
     * `j == 1` → first column
     * `j == n` → last column
   * Else print space `" "` → creates the hollow effect.
4. `print()` → moves to the next line after each row.

**Logic:** Only border positions get a `*`, all inner positions get a space.


**✅ Output**

```
*****
*   *
*   *
*   *
*****
```

---

## 3: Border-only square star pattern

**✅ Python Code**

```python
# Border-Only Square Star Pattern
n = 5

for i in range(1, n + 1):      # Rows
    for j in range(1, n + 1):  # Columns
        if i == 1 or i == n or j == 1 or j == n:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Outer loop (`i`)** → controls rows (1 to n).
2. **Inner loop (`j`)** → controls columns (1 to n).
3. **Condition for border stars**:

   * `i == 1` → first row
   * `i == n` → last row
   * `j == 1` → first column
   * `j == n` → last column
4. **Else** → print space `" "` inside.
5. `print()` → moves to next line.

**Result:** Only the square’s border has `*`, inside is empty.


**✅ Output**

```
*****
*   *
*   *
*   *
*****
```

---

## 4: Cross/X star pattern

**✅ Python Code**

```python
# Cross/X Star Pattern
n = 5

for i in range(n):
    for j in range(n):
        if i == j or i + j == n - 1:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Outer loop (`i`)** → iterates through rows `0` to `n-1`.
2. **Inner loop (`j`)** → iterates through columns `0` to `n-1`.
3. **Condition for `*`**:

   * `i == j` → main diagonal
   * `i + j == n - 1` → secondary diagonal
4. **Else** → print space `" "`
5. `print()` → move to the next row.

**Logic:** Stars are printed only where the row and column indices meet diagonals.



**✅ Output**

```
*   *
 * * 
  *  
 * * 
*   *
```

---
## 5: Plus sign star pattern**

**✅ Python Code**

```python
# Plus Sign Star Pattern
n = 5
mid = n // 2  # Middle index

for i in range(n):
    for j in range(n):
        if i == mid or j == mid:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **Find the middle**: `mid = n // 2` → row & column where the plus intersects.
2. **Outer loop (`i`)** → iterates over rows.
3. **Inner loop (`j`)** → iterates over columns.
4. **Condition for stars**:

   * `i == mid` → center row
   * `j == mid` → center column
5. **Else** → print space `" "` inside.
6. `print()` → moves to the next row.

**Logic:** Stars are printed **only in the middle row and column** to form a plus sign.



**✅ Output**

```
  *  
  *  
*****
  *  
  *  
```

---

## 6: Hollow plus star pattern

**✅ Python Code**

```python
# Hollow Plus Star Pattern
n = 7
mid = n // 2  # Center row and column

for i in range(n):
    for j in range(n):
        if i == mid:  # Middle row
            if j == 0 or j == n - 1:
                print("*", end="")
            else:
                print(" ", end="")
        elif j == mid:  # Middle column
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **Outer loop (`i`)** → rows `0` to `n-1`.
2. **Inner loop (`j`)** → columns `0` to `n-1`.
3. **Middle row (`i == mid`)**:

   * Only print stars at the **first and last columns**.
4. **Middle column (`j == mid`)**:

   * Print stars for all rows.
5. **Else** → print space `" "`.
6. `print()` → move to next line.

**Logic:** Stars form a hollow plus: vertical line is full, horizontal line only at the ends.



**✅ Output**

```
   *   
   *   
*     *
   *   
   *   
```

---


## 7: Solid Diamond Star Pattern

**✅ Python Code**

```python
# Solid Diamond Star Pattern
n = 5

# Upper half
for i in range(1, n + 1):
    print(" " * (n - i) + "*" * (2*i - 1))

# Lower half
for i in range(n-1, 0, -1):
    print(" " * (n - i) + "*" * (2*i - 1))
```



**✅ Explanation**

1. **Upper half:**

   * Rows: `1` to `n`
   * Spaces: `n - i` → to center the stars
   * Stars: `2*i - 1` → odd number of stars per row

2. **Lower half:**

   * Rows: `n-1` down to `1`
   * Spaces: `n - i`
   * Stars: `2*i - 1`

3. `print()` → moves to the next line.

**Logic:** Diamond = upper pyramid + inverted pyramid.



**✅ Output**

```
    *    
   ***   
  *****  
 ******* 
*********
 ******* 
  *****  
   ***   
    *    
```

---

## 8: Hollow diamond star pattern**

**✅ Python Code**

```python
# Hollow Diamond Star Pattern
n = 5

# Upper half
for i in range(1, n + 1):
    for j in range(1, 2*n):
        if j == n - i + 1 or j == n + i - 1:
            print("*", end="")
        else:
            print(" ", end="")
    print()

# Lower half
for i in range(n-1, 0, -1):
    for j in range(1, 2*n):
        if j == n - i + 1 or j == n + i - 1:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **Upper half:**

   * Rows: `1` to `n`
   * Columns: `1` to `2*n - 1`
   * Print `*` at positions:

     * `j == n - i + 1` → left diagonal
     * `j == n + i - 1` → right diagonal

2. **Lower half:**

   * Rows: `n-1` down to `1`
   * Columns: `1` to `2*n - 1`
   * Print `*` at positions: same as above for inverted pyramid

3. **Else:** print space `" "`

4. `print()` → move to next line

**Logic:** Only the borders of the diamond are stars; inside is hollow.



**✅ Output**

```
    *    
   * *   
  *   *  
 *     * 
*       *
 *     * 
  *   *  
   * *   
    *    
```

---

## 9: Butterfly star pattern

**✅ Python Code**

```python
# Butterfly Star Pattern
n = 5

# Upper half
for i in range(1, n+1):
    print("*"*i + " "*(2*(n-i)) + "*"*i)

# Lower half
for i in range(n, 0, -1):
    print("*"*i + " "*(2*(n-i)) + "*"*i)
```



**✅ Explanation**

1. **Upper half (top wings):**

   * Rows: `1` to `n`
   * Left stars: `i`
   * Spaces in middle: `2*(n-i)`
   * Right stars: `i`

2. **Lower half (bottom wings):**

   * Rows: `n` down to `1`
   * Same logic as upper half, inverted

3. `print()` → moves to the next line

**Logic:** Two triangles of stars expand outward from top to bottom forming a butterfly shape.



**✅ Output**

```
*        *
**      **
***    ***
****  ****
**********
**********
****  ****
***    ***
**      **
*        *
```

---

## 10: Hollow butterfly star pattern

**✅ Python Code**

```python
# Hollow Butterfly Star Pattern
n = 5

# Upper half
for i in range(1, n+1):
    for j in range(1, i+1):  # Left stars
        if j == 1 or j == i:
            print("*", end="")
        else:
            print(" ", end="")
    print(" " * (2*(n-i)), end="")  # Middle spaces
    for j in range(1, i+1):  # Right stars
        if j == 1 or j == i:
            print("*", end="")
        else:
            print(" ", end="")
    print()

# Lower half
for i in range(n, 0, -1):
    for j in range(1, i+1):
        if j == 1 or j == i:
            print("*", end="")
        else:
            print(" ", end="")
    print(" " * (2*(n-i)), end="")
    for j in range(1, i+1):
        if j == 1 or j == i:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **Outer loop:**

   * Upper half: `i = 1` to `n`
   * Lower half: `i = n` down to `1`

2. **Left wing stars:**

   * Loop `j = 1` to `i`
   * Print `*` **only for first and last positions** (`j == 1 or j == i`)
   * Inner positions → spaces

3. **Middle space:**

   * `" " * (2*(n-i))` → separates left and right wings

4. **Right wing stars:**

   * Same logic as left wing

5. `print()` → move to next line

**Logic:** Only the edges of the wings are stars; inside is hollow, forming a butterfly shape.



**✅ Output**

```
*        *
**      **
* *    * *
*  *  *  *
*   **   *
*   **   *
*  *  *  *
* *    * *
**      **
*        *
```

---

## 11: Sandglass star pattern

**✅ Python Code**

```python
# Sandglass Star Pattern
n = 5

# Upper half (inverted pyramid)
for i in range(n, 0, -1):
    print(" " * (n - i) + "*" * (2*i - 1))

# Lower half (normal pyramid)
for i in range(2, n + 1):
    print(" " * (n - i) + "*" * (2*i - 1))
```



**✅ Explanation**

1. **Upper half (inverted pyramid):**

   * Rows: `n` down to `1`
   * Spaces: `n - i` → indent to center the stars
   * Stars: `2*i - 1` → odd number decreasing

2. **Lower half (normal pyramid):**

   * Rows: `2` to `n`
   * Spaces: `n - i` → indent to center the stars
   * Stars: `2*i - 1` → odd number increasing

3. `print()` → moves to next line

**Logic:** Top is an inverted pyramid, bottom is a normal pyramid → forms a sandglass.



**✅ Output**

```
*********
 ******* 
  *****  
   ***   
    *    
   ***   
  *****  
 ******* 
*********
```

---
## 12: Hourglass star pattern


**✅ Python Code**

```python
# Hourglass Star Pattern
n = 5

# Upper half
for i in range(n):
    for j in range(n*2-1):
        if j == i or j == (2*n - 2 - i):
            print("*", end="")
        else:
            print(" ", end="")
    print()

# Lower half
for i in range(n-2, -1, -1):
    for j in range(n*2-1):
        if j == i or j == (2*n - 2 - i):
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **Outer loop:**

   * Upper half: `i = 0` to `n-1`
   * Lower half: `i = n-2` down to `0`

2. **Inner loop:**

   * Columns: `j = 0` to `2*n-2`
   * Print `*` **only at edges**:

     * `j == i` → left diagonal
     * `j == 2*n - 2 - i` → right diagonal

3. **Else** → print space `" "`

4. `print()` → moves to next line

**Logic:** Stars form the edges of an hourglass; spaces fill the interior.



**✅ Output**

```
*       *
 *     * 
  *   *  
   * *   
    *    
   * *   
  *   *  
 *     * 
*       *
```

---

## 13: Hollow hourglass star pattern

**✅ Python Code**

```python
# Hollow Hourglass Star Pattern
n = 5

# Upper half
for i in range(n):
    for j in range(2*n - 1):
        if i == 0:  # first row full of stars
            print("*", end="")
        elif j == i or j == (2*n - 2 - i):  # diagonals
            print("*", end="")
        else:
            print(" ", end="")
    print()

# Lower half
for i in range(n-2, -1, -1):
    for j in range(2*n - 1):
        if i == 0:  # last row full of stars
            print("*", end="")
        elif j == i or j == (2*n - 2 - i):  # diagonals
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

1. **First & Last rows:**

   * Completely filled with `*`

2. **Other rows:**

   * Print `*` at **left diagonal** (`j == i`)
   * Print `*` at **right diagonal** (`j == 2*n - 2 - i`)
   * Else → print `" "`

3. **Upper half:** `i = 0 → n-1`

4. **Lower half:** `i = n-2 → 0`



**✅ Output**

```
*********
 *     * 
  *   *  
   * *   
    *    
   * *   
  *   *  
 *     * 
*********
```

---

## 14: Rhombus star pattern

**✅ Python Code**

```python
# Rhombus Star Pattern
n = 5

for i in range(n):
    print(" " * i + "*" * n)
```



**✅ Explanation**

1. **Outer loop:** runs `n` times → for each row.
2. **Spaces:** `" " * i` → increases each row to shift stars to the right.
3. **Stars:** `"*" * n` → each row always has `n` stars.
4. Output looks like a parallelogram → called **Rhombus pattern**.



**✅ Output**

```
*****
 *****
  *****
   *****
    *****
```

---

## 15: Hollow rhombus star pattern

**✅ Python Code**

```python
# Hollow Rhombus Star Pattern
n = 5

for i in range(n):
    for j in range(n + i):
        if j < i:  # leading spaces
            print(" ", end="")
        else:
            # border conditions
            if i == 0 or i == n-1 or j == i or j == n+i-1:
                print("*", end="")
            else:
                print(" ", end="")
    print()
```



**✅ Explanation**

1. **Outer loop (i):** runs for rows `0 → n-1`.
2. **Spaces:** first `i` spaces to shift the rhombus.
3. **Stars:**

   * First row (`i == 0`) → all stars
   * Last row (`i == n-1`) → all stars
   * For middle rows → star only at **first** and **last** position in that row (`j == i` or `j == n+i-1`).
4. **Else → space**



**✅ Output**

```
*****
 *   *
  *   *
   *   *
    *****
```

---
## 16: Zig-zag star pattern

**✅ Python Code**

```python
# Zig-Zag Star Pattern
n = 9   # width

for i in range(3):   # only 3 rows needed for zig-zag
    for j in range(1, n+1):
        # Conditions for stars
        if (i + j) % 4 == 0 or (i == 1 and j % 4 == 0):
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

* We need **3 rows** to create the zig-zag wave.
* Conditions for stars:

  * `(i + j) % 4 == 0` → handles diagonals slanting down-left.
  * `(i == 1 and j % 4 == 0)` → handles diagonals slanting down-right.
* Everything else is space `" "`.



**✅ Output**

```
    *       *       *
   * *     * *     * *
  *   *   *   *   *   *
```

---

## 17 Spiral star pattern (inside square)

**✅ Python Code**

```python
# Spiral Star Pattern inside a Square
n = 5
matrix = [[" " for _ in range(n)] for _ in range(n)]

top, bottom, left, right = 0, n-1, 0, n-1

while top <= bottom and left <= right:
    # Top row
    for i in range(left, right+1):
        matrix[top][i] = "*"
    top += 1

    # Right column
    for i in range(top, bottom+1):
        matrix[i][right] = "*"
    right -= 1

    # Bottom row
    if top <= bottom:
        for i in range(right, left-1, -1):
            matrix[bottom][i] = "*"
        bottom -= 1

    # Left column
    if left <= right:
        for i in range(bottom, top-1, -1):
            matrix[i][left] = "*"
        left += 1

# Print matrix
for row in matrix:
    print("".join(row))
```



**✅ Explanation**

1. We create a 2D **matrix of spaces**.
2. Then we fill it layer by layer like a spiral:

   * **Top row** → left to right
   * **Right column** → top to bottom
   * **Bottom row** → right to left
   * **Left column** → bottom to top
3. Shrink the boundaries (`top, bottom, left, right`) and repeat until filled.



**✅ Output (n = 5)**

```
*****
    *
*** *
*   *
*** *
```

(for larger `n`, the spiral keeps continuing inward 🔄)

---
## 18 Concentric squares star pattern

**✅ Python Code**

```python
# Concentric Squares Star Pattern
n = 7
for i in range(n):
    for j in range(n):
        # find minimum distance from any border
        min_dist = min(i, j, n-1-i, n-1-j)
        # if min_dist is even, print star else space
        if min_dist % 2 == 0:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

* A point `(i, j)` belongs to some "layer" depending on how close it is to the nearest border.
* `min_dist = min(i, j, n-1-i, n-1-j)` → distance from nearest edge.
* If that distance is **even** → print `*`.
* If odd → print space.
* This creates alternating square borders.



**✅ Output (n = 7)**

```
*******
*     *
* *** *
* * * *
* *** *
*     *
*******
```

---

## 19 Star circle approximation

**✅ Python Code – Circle Approximation**

```python
# Star Circle Approximation
n = 15   # diameter (size of grid)
r = n // 2   # radius

for i in range(n):
    for j in range(n):
        # equation of circle (with tolerance)
        dist = ((i - r)**2 + (j - r)**2)**0.5
        if abs(dist - r) < 0.7:   # tolerance controls thickness
            print("*", end="")
        else:
            print(" ", end="")
    print()
```



**✅ Explanation**

* We take an `n x n` grid.
* Compute distance of each point `(i, j)` from the center `(r, r)`.
* If distance ≈ radius → print `*`.
* Else → print space `" "`.
* The tolerance (`0.7`) makes the circle visible (thickness of border).



**✅ Output (n = 15, approx circle)**

```
      *****      
    *       *    
   *         *   
  *           *  
  *           *  
   *         *   
    *       *    
      *****      
```

---
## 20 Heart star pattern

**✅ Python Code**

```python
# Heart Star Pattern
n = 6

for i in range(n//2, n, 2):
    # left spaces
    for j in range(1, n-i, 2):
        print(" ", end="")
    # left stars
    for j in range(i):
        print("*", end="")
    # middle spaces
    for j in range(1, n-i+1):
        print(" ", end="")
    # right stars
    for j in range(i):
        print("*", end="")
    print()

# lower part
for i in range(n, 0, -1):
    for j in range(n-i):
        print(" ", end="")
    for j in range(2*i-1):
        print("*", end="")
    print()
```



**✅ Explanation**

1. The **upper part** of the heart is made of two connected semi-circles (two triangles).
2. The **lower part** is an inverted pyramid of stars.
3. Careful spacing makes it symmetric.



**✅ Output (n = 6)**

```
 **   **
*  * *  *
*   *   *
 *     * 
  *   *  
   * *   
    *    
```



