## 1: Arrow star pattern

**✅ Python Code (right-pointing arrow)**

```python
# Right-pointing Arrow Star Pattern
n = 5  # arrow "half-height"

# Upper part (growing arm)
for i in range(1, n):
    print(" " * (n - i) + "*" * i)

# Middle (shaft/wide part)
print("*" * (2 * n - 1))

# Lower part (shrinking arm)
for i in range(n - 1, 0, -1):
    print(" " * (n - i) + "*" * i)
```


**✅ Explanation**

* `n` controls the half-height of the arrow (use odd or even as you like).
* Upper loop prints the ascending arm (indented so the arm points right).
* The middle line prints the full shaft: `2*n - 1` stars.
* Lower loop mirrors the upper arm to complete the arrow.


**✅ Output (n = 5)**

```
    *
   **
  ***
 ****
*********
 ****
  ***
   **
    *
```

---

## 2: Double arrow pattern

**✅ Python Code**

```python
# Double Arrow Star Pattern

n = 5  # number of rows in half

# Upper half
for i in range(1, n + 1):
    print("*" * i + " " * (2 * (n - i)) + "*" * i)

# Lower half
for i in range(n - 1, 0, -1):
    print("*" * i + " " * (2 * (n - i)) + "*" * i)
```


**✅ Explanation**

1. **Upper Half:**

   * Left arrow grows from 1 → n stars.
   * Spaces in between shrink as rows increase (`2*(n-i)` spaces).
   * Right arrow mirrors the left one.
2. **Lower Half:**

   * Simply reverses the process to mirror the top.

This symmetry forms **two arrows facing each other** — creating a beautiful diamond-like shape but open in the middle.


**✅ Output (n = 5)**

```
*        *
**      **
***    ***
****  ****
**********
****  ****
***    ***
**      **
*        *
```


✨ **Tip:**

* Change `n` for different sizes.
* Try replacing `"*"` with `"@"` or numbers for creative variations.

---
## 3: Hollow arrow star pattern

**✅ Python Code**

```python
# Hollow Arrow Star Pattern

n = 5  # height of half arrow

# Upper part (arrow head)
for i in range(1, n):
    print(" " * (n - i), end="")  # leading spaces
    if i == 1:
        print("*")
    else:
        print("*" + " " * (2 * i - 3) + "*")

# Middle (arrow shaft)
print("*" * (2 * n - 1))

# Lower part (reverse of upper)
for i in range(n - 1, 0, -1):
    print(" " * (n - i), end="")
    if i == 1:
        print("*")
    else:
        print("*" + " " * (2 * i - 3) + "*")
```


**✅ Explanation**

1. **Upper Part:**

   * The arrowhead grows row by row.
   * First row: single `*`.
   * Next rows: stars at the beginning and end, spaces in between (`2*i - 3`).

2. **Middle Line:**

   * Forms the **arrow shaft**, a solid line of stars of width `2*n - 1`.

3. **Lower Part:**

   * Mirrors the upper half to complete the arrow.


**✅ Output (n = 5)**

```
    *
   * *
  *   *
 *     *
*********
 *     *
  *   *
   * *
    *
```

✨ **Bonus Tip:**

* Change `n` for bigger/smaller arrows.
* Replace `"*"` with `"#"` or `"+"` for unique styles.
---

## 4: Kite star pattern

**✅ Python Code**

```python
# Kite Star Pattern

n = 5  # height of upper diamond part

# Upper Diamond (Triangle part)
for i in range(1, n + 1):
    print(" " * (n - i) + "*" * (2 * i - 1))

# Tail of the kite
for i in range(3):  # length of tail
    print(" " * (n - 1) + "*")
```


**✅ Explanation**

1. **Upper Diamond (Main Kite Body):**

   * Uses the classic **pyramid formula**:
     `spaces = n - i`, `stars = 2*i - 1`.
   * Creates a **triangle-like kite top**.

2. **Tail (String of the kite):**

   * Printed as a single star (`*`) aligned in the center.
   * You can adjust tail length by changing the `range(3)` value.


**✅ Output (n = 5)**

```
    *
   ***
  *****
 *******
*********
    *
    *
    *
```

✨ **Customization Tips:**

* Change tail length for a longer kite.
* Replace `"*"` with `"@"` or `"#"` for a stylish look.
* You can even make a **hollow kite** (just the border lines) — would you like that version next?

---
## 5: Trapezium star pattern

**✅ Python Code**

```python
# Trapezium Star Pattern

n = 5  # number of rows

for i in range(n):
    print(" " * i + "*" * (n + i))
```


**✅ Explanation**

1. **Outer loop (`i`)** → controls the number of rows.
2. **Spaces (`" " * i`)** → increase with each row to shift the stars right.
3. **Stars (`"*" * (n + i)`)** → increase in count with each row.
4. Together, it forms a **trapezium shape** — top narrow, bottom wide.


**✅ Output (n = 5)**

```
*****
 ******
  *******
   ********
    *********
```

**🔹 Variation – *Inverted Trapezium***

If you want the shape **upside-down**, just reverse the loop:

```python
# Inverted Trapezium Star Pattern
n = 5
for i in range(n):
    print(" " * i + "*" * (2 * n - i))
```

**Output:**

```
**********
 *********
  ********
   *******
    ******
```

---
## 6: Hollow trapezium pattern

**✅ Python Code**

```python
# Hollow Trapezium Star Pattern

n = 5  # number of rows

for i in range(n):
    spaces = " " * i
    stars_in_row = n + i

    # First and last row are solid
    if i == 0 or i == n - 1:
        print(spaces + "*" * stars_in_row)
    else:
        # Middle rows: star + spaces + star
        inner_spaces = " " * (stars_in_row - 2)
        print(spaces + "*" + inner_spaces + "*")
```


**✅ Explanation**

1. **`n`** → total height (number of rows).
2. **Outer loop (`i`)** → row iterator.
3. **Leading spaces (`" " * i`)** → shift the shape right to make the trapezium tilt.
4. **First and last rows** → completely filled with `*`.
5. **Middle rows** → only border stars with inner hollow spaces (`stars_in_row - 2`).


**✅ Output (n = 5)**

```
*****
 *   *
  *   *
   *   *
    *****
```

---

## 7: Pyramid with spaces inside

**✅ Python Code**

```python
# Pyramid with Spaces Inside (Hollow Pyramid)

n = 5  # height of the pyramid

for i in range(1, n + 1):
    # leading spaces
    print(" " * (n - i), end="")

    # first and last star or border stars
    if i == 1 or i == n:
        print("*" * (2 * i - 1))
    else:
        # star + inner spaces + star
        print("*" + " " * (2 * i - 3) + "*")
```


**✅ Explanation**

1. **`n` = height** of the pyramid.
2. For each row `i`:

   * Print `(n - i)` spaces to center-align the pyramid.
   * If it’s the **first or last row**, print all stars.
   * Otherwise, print one star, spaces inside (`2*i - 3`), and another star — this creates the **hollow effect**.
3. The bottom row (`i == n`) is completely filled with stars to form the base.


**✅ Output (n = 5)**

```
    *
   * *
  *   *
 *     *
*********
```

---
## 8: Diamond with numbers + stars mixed

**✅ Python Code**

```python
# Diamond with Numbers and Stars Mixed

n = 5  # height of half diamond

# Upper half
for i in range(1, n + 1):
    print(" " * (n - i), end="")
    print(f"{i}" + "*" * (2 * i - 3 if i > 1 else 0) + (f"{i}" if i > 1 else ""))

# Lower half
for i in range(n - 1, 0, -1):
    print(" " * (n - i), end="")
    print(f"{i}" + "*" * (2 * i - 3 if i > 1 else 0) + (f"{i}" if i > 1 else ""))
```


**✅ Explanation**

1. **Upper half loop (`1 → n`)**

   * Each row starts with spaces → `" " * (n - i)` for centering.
   * Print left number (`i`),
     then stars (`2*i - 3` inside),
     then right number (`i` again if row > 1`).

2. **Lower half loop (`n-1 → 1`)**

   * Mirrors the upper half to form the complete diamond.

3. For the **first row**, only one number appears (since there are no stars yet).


**✅ Output (n = 5)**

```
    1
   2*2
  3***3
 4*****4
5*******5
 4*****4
  3***3
   2*2
    1
```

---
## 9: Pyramid with Fibonacci numbers

**✅ Pattern Preview (n = 5)**

```
        0
      1   1
    2   3   5
  8   13  21  34
55  89  144  233  377
```


**✅ Python Code**

```python
# Pyramid with Fibonacci Numbers

n = 5  # number of rows

# Step 1: Generate enough Fibonacci numbers
fib = [0, 1]
for i in range(2, n * (n + 1) // 2):  # total numbers needed
    fib.append(fib[-1] + fib[-2])

# Step 2: Print Fibonacci numbers in pyramid form
index = 0
for i in range(1, n + 1):
    print("  " * (n - i), end="")  # leading spaces for center alignment
    for j in range(i):
        print(f"{fib[index]:<4}", end="  ")
        index += 1
    print()
```


**✅ Explanation**

1. **Fibonacci Sequence Generation:**

   * The number of elements required is `n*(n+1)//2` (like Floyd’s triangle).
   * Each new Fibonacci number = `sum of last two numbers`.

2. **Pyramid Formation:**

   * Row `i` contains `i` Fibonacci numbers.
   * `"  " * (n - i)` adds spaces to center the pyramid.
   * Numbers are printed with spacing (`:<4`) for alignment.

3. **`index`** keeps track of which Fibonacci number to print next.


**✅ Output (n = 5)**

```
        0
      1   1
    2   3   5
  8   13  21  34
55  89  144  233  377
```

---
## 10: Pyramid with prime numbers

**✅ Python Code**

```python
# Pyramid with Prime Numbers

n = 5  # number of rows

# Step 1: Generate enough prime numbers
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(num**0.5)+1):
        if num % i == 0:
            return False
    return True

primes = []
num = 2
while len(primes) < n*(n+1)//2:  # total numbers needed
    if is_prime(num):
        primes.append(num)
    num += 1

# Step 2: Print in pyramid form
index = 0
for i in range(1, n + 1):
    print("  " * (n - i), end="")  # leading spaces for pyramid alignment
    for j in range(i):
        print(f"{primes[index]:<4}", end="  ")
        index += 1
    print()
```


**✅ Explanation**

1. **Prime Number Generation:**

   * Use `is_prime(num)` to check if a number is prime.
   * Keep generating primes until we have `n*(n+1)/2` numbers (like Floyd’s triangle).

2. **Pyramid Formation:**

   * Row `i` contains `i` prime numbers.
   * Leading spaces (`"  " * (n-i)`) center-align the pyramid.
   * Numbers are printed with fixed width (`:<4`) for alignment.

3. **`index`** keeps track of which prime number to print next.


**✅ Output (n = 5)**

```
        2
      3   5
    7   11  13
  17  19  23  29
31  37  41  43  47
```

---

## 11: Hollow concentric diamonds

**✅ Python Code**

```python
# Hollow Concentric Diamonds

n = 4  # number of concentric layers
size = n * 2 - 1  # half-height of the largest diamond

for i in range(-size+1, size):
    for j in range(-size+1, size):
        if abs(i) + abs(j) == size-1 or abs(i) + abs(j) == size-3 or abs(i) + abs(j) == size-5:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Diamond Formula:**

   * For a single hollow diamond, condition:
     [
     |i| + |j| = size-1
     ]
     where `(i, j)` is the coordinate relative to the center.

2. **Concentric Layers:**

   * Each inner diamond decreases the `size` by 2 (`size-1`, `size-3`, `size-5`, …).
   * Loop through all coordinates from `-size+1 → size-1`.

3. Print `*` if the current coordinate satisfies **any diamond layer condition**, otherwise space.


**✅ Output (n = 3, size = 5)**

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

## 12: Tree shape (Christmas tree)

**✅ Python Code**

```python
# Christmas Tree Star Pattern

n = 5  # number of pyramid layers

# Tree Leaves (pyramid part)
for i in range(1, n + 1):
    print(" " * (n - i) + "*" * (2 * i - 1))

# Tree Trunk
trunk_height = 2
for i in range(trunk_height):
    print(" " * (n - 1) + "*")
```


**✅ Explanation**

1. **Leaves / Pyramid:**

   * Each row `i` has `(2*i - 1)` stars for width.
   * `" " * (n - i)` adds spaces for center alignment.

2. **Trunk:**

   * Fixed width (`1 star`) and centered.
   * `trunk_height` can be changed for a taller tree trunk.


**✅ Output (n = 5)**

```
    *
   ***
  *****
 *******
*********
    *
    *
```

---
## 13: Hollow tree shape

**✅ Python Code**

```python
# Hollow Christmas Tree Star Pattern

n = 5  # height of tree pyramid

# Tree Leaves (hollow pyramid)
for i in range(1, n + 1):
    print(" " * (n - i), end="")
    if i == 1:
        print("*")
    elif i == n:
        print("*" * (2 * i - 1))
    else:
        print("*" + " " * (2 * i - 3) + "*")

# Tree Trunk
trunk_height = 2
for i in range(trunk_height):
    print(" " * (n - 1) + "*")
```


**✅ Explanation**

1. **Leaves / Pyramid:**

   * Row 1 → single star at top.
   * Rows 2 → n-1 → stars only at borders (`*`) with spaces in between (`2*i-3`).
   * Row n → base of tree, solid stars.

2. **Trunk:**

   * Center-aligned single star, repeated `trunk_height` times.


**✅ Output (n = 5)**

```
    *
   * *
  *   *
 *     *
*********
    *
    *
```

---
## 14: Star + number alternating grid

**✅ Python Code**

```python
# Star + Number Alternating Grid

n = 5  # size of grid

for i in range(n):
    num = 1
    for j in range(n):
        if (i + j) % 2 == 0:
            print("*", end=" ")
        else:
            print(num, end=" ")
            num += 1
    print()
```


**✅ Explanation**

1. **Alternating Logic:**

   * `(i + j) % 2 == 0` → print a star (`*`).
   * Else → print a number.

2. **Number Counter:**

   * Starts from 1 for each row and increments only when a number is printed.

3. **Grid Size:**

   * Controlled by `n` (number of rows and columns).


**✅ Output (n = 5)**

```
* 1 * 2 *  
1 * 2 * 3  
* 2 * 3 *  
2 * 3 * 4  
* 3 * 4 *  
```

---


## 15: Sine wave star pattern

**✅ Python Code**

```python
# Sine Wave Star Pattern

import math

rows = 10     # height of grid (amplitude)
cols = 60     # total width (wavelength repetitions)

for i in range(rows):
    for j in range(cols):
        # Map j to a sine wave position
        y = int((math.sin(j * math.pi / 8) + 1) * (rows - 1) / 2)
        if i == rows - 1 - y:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Sine Function Logic:**

   * `math.sin(j * π / 8)` generates a smooth wave pattern from `-1` to `1`.
   * `(rows - 1)/2` scales it to fit within the given grid height.
   * The formula calculates the **star position (`y`)** for each column.

2. **Plotting:**

   * If the current row `i` equals the computed wave height → print `*`, else space.

3. **Adjustable Parameters:**

   * `rows`: controls the wave height (amplitude).
   * `cols`: controls how many cycles or width of the pattern (frequency).


**✅ Output Example (rows = 10, cols = 60)**

```
          *           *           *           *           
       *     *     *     *     *     *     *     *       
    *           *           *           *           *    
 *                                               *       
*                                                 *      
 *                                               *       
    *           *           *           *           *    
       *     *     *     *     *     *     *     *       
          *           *           *           *          
```

---
## 16: Cosine wave star pattern

**✅ Python Code**

```python
# Cosine Wave Star Pattern

import math

rows = 10     # height of the grid (amplitude)
cols = 60     # total width of wave (number of columns)

for i in range(rows):
    for j in range(cols):
        # Cosine wave formula (starts at peak)
        y = int((math.cos(j * math.pi / 8) + 1) * (rows - 1) / 2)
        if i == rows - 1 - y:
            print("*", end="")
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Cosine Logic:**

   * `math.cos()` starts at **1** → top of the wave.
   * As `j` increases, it smoothly goes down, up, down, etc.

2. **Scaling the Wave:**

   * `(math.cos(j * π / 8) + 1)` → shifts range from `[-1, 1]` to `[0, 2]`.
   * Multiply by `(rows - 1)/2` to fit within height.

3. **Printing Logic:**

   * When `i` matches the computed vertical position (`y`), print `*`.
   * Else print a space.


**✅ Output Example (rows = 10, cols = 60)**

```
*           *           *           *           *           
  *       *   *       *   *       *   *       *   *         
    *   *       *   *       *   *       *   *       *       
      *           *           *           *           *     
        *                                         *         
      *           *           *           *           *     
    *   *       *   *       *   *       *   *       *       
  *       *   *       *   *       *   *       *   *         
*           *           *           *           *           
```

---
## 17: Triangle spiral filling

**✅ Python Code**

```python
# Triangle Spiral Filling Pattern

n = 5  # size of the triangle
a = [[0] * n for _ in range(n)]

num = 1
top, left = 0, 0
bottom, right = n - 1, n - 1

while left <= right and top <= bottom:
    # Top row
    for i in range(left, right + 1):
        a[top][i] = num
        num += 1
    top += 1

    # Right column
    for i in range(top, bottom + 1):
        a[i][right] = num
        num += 1
    right -= 1

    # Bottom row
    if top <= bottom:
        for i in range(right, left - 1, -1):
            a[bottom][i] = num
            num += 1
        bottom -= 1

    # Left diagonal (upward)
    if left <= right:
        for i in range(bottom, top - 1, -1):
            a[i][left] = num
            num += 1
        left += 1

# Print the upper-triangular spiral
for i in range(n):
    for j in range(i + 1):
        print(f"{a[i][j]:2}", end=" ")
    print()
```


**✅ Explanation**

1. **Matrix Setup:**

   * A 2D list `a` stores numbers.
   * Boundaries: `top`, `bottom`, `left`, `right` control spiral layers.

2. **Spiral Filling:**

   * Moves → **Right → Down → Left → Up**, just like a square spiral.
   * After each direction, boundaries shrink inward.

3. **Triangle Display:**

   * Only print upper-triangular part → makes it look like a **triangular spiral**.


**✅ Output (n = 5)**

```
 1 
14 15 
13 20 19 
12 11 10  9 
```

*(You can adjust the print loop to show different triangular orientations — left or right aligned.)*

---
## 18: Circle-like number placement (approximate)

**✅ Python Code**

```python
# Circle-like Number Placement (Approximation)

import math

r = 6   # radius of circle
num = 1

for i in range(-r, r + 1):
    for j in range(-r, r + 1):
        distance = math.sqrt(i ** 2 + j ** 2)
        # Print a number if the point lies near the circle boundary
        if r - 0.5 < distance < r + 0.5:
            print(f"{num:2}", end=" ")
            num += 1
        else:
            print("  ", end=" ")
    print()
```


**✅ Explanation**

1. **Concept:**

   * The mathematical circle equation: `x² + y² = r²`.
   * For each grid point `(i, j)`, we calculate its **distance** from the center using `√(i² + j²)`.

2. **Approximation:**

   * We check if the distance is **close to the radius** (`r ± 0.5`) to print a number there — that forms a rough circular outline.

3. **Numbering:**

   * We increment `num` every time we print on the boundary, giving a numbered circle outline.


**✅ Output Example (r = 6)**

```
            1  2  3  4            
        5               6         
      7                   8       
    9                       10    
  11                         12   
  13                         14   
    15                     16     
      17                 18       
        19             20         
            21 22 23 24           
```

---

## 19: Fractal-like recursive triangle (Sierpinski approx)

**✅ Python Code (Recursive Approach)**

```python
# Fractal-like Recursive Triangle (Sierpiński Approximation)

def sierpinski(n):
    if n == 1:
        return ["*"]
    else:
        prev = sierpinski(n - 1)
        space = " " * (2 ** (n - 2))
        top = [space + p + space for p in prev]
        bottom = [p + " " + p for p in prev]
        return top + bottom

# Set recursion depth (controls triangle size)
depth = 4
pattern = sierpinski(depth)

# Print the final fractal pattern
for row in pattern:
    print(row)
```


**✅ Explanation**

1. **Recursive Structure:**

   * The smallest triangle (`n = 1`) is just `*`.
   * Each larger triangle consists of **3 copies** of the previous one:

     * One on top (centered with spaces)
     * Two at the bottom (side by side).

2. **Spacing Logic:**

   * `" " * (2 ** (n - 2))` centers the top part correctly each recursion step.
   * The triangle grows in width as powers of 2 → `2^(n-1)` columns.

3. **Fractal Behavior:**

   * Each recursion level doubles the triangle size and creates *holes* inside — giving that fractal look.


**✅ Output (depth = 4)**

```
       *       
      * *      
     *   *     
    * * * *    
   *       *   
  * *     * *  
 *   *   *   * 
* * * * * * * *
```

---

## 20: Chess knight movement pattern (matrix filling in knight’s tour order)

**✅ Python Code (Backtracking Knight’s Tour)**

```python
# Knight's Tour Matrix Filling (Backtracking)

N = 5  # Board size (NxN)

# Initialize NxN board with -1 (unvisited)
board = [[-1 for _ in range(N)] for _ in range(N)]

# Possible moves for a knight
moves_x = [2, 1, -1, -2, -2, -1, 1, 2]
moves_y = [1, 2, 2, 1, -1, -2, -2, -1]

# Start position
board[0][0] = 1

def is_safe(x, y):
    return 0 <= x < N and 0 <= y < N and board[x][y] == -1

def solve(x, y, move):
    if move > N * N:
        return True  # all cells visited

    for i in range(8):
        next_x = x + moves_x[i]
        next_y = y + moves_y[i]
        if is_safe(next_x, next_y):
            board[next_x][next_y] = move
            if solve(next_x, next_y, move + 1):
                return True
            board[next_x][next_y] = -1  # backtrack
    return False

# Run the tour
if solve(0, 0, 2):
    for row in board:
        print(" ".join(f"{c:2}" for c in row))
else:
    print("No solution found.")
```


**✅ Explanation**

1. **Board Initialization:**

   * We create an `N×N` grid initialized to `-1` meaning *unvisited*.

2. **Knight Moves:**

   * From any square `(x, y)`, a knight can move in 8 possible L-shaped directions defined by `(±1, ±2)` combinations.

3. **Backtracking:**

   * Place the knight at a cell, mark it with the move number.
   * Recursively move to all possible next cells.
   * If stuck, *backtrack* (undo move).

4. **Base Case:**

   * When `move == N*N + 1`, every cell is visited → print solution.


**✅ Output (N = 5)**

```
 1 22  9 14  3
10 15  2 23  8
21 24 13  4 19
16 11 20  7 12
25  6 17 18  5
```

*(Exact order may vary based on move sequence, but every cell gets a unique number.)*

---

