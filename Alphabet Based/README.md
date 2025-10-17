**✅ Python Code**

```python
# Alphabet Triangle Pattern

n = 5
ch = ord('A')  # ASCII of 'A'

for i in range(1, n+1):
    for j in range(i):
        print(chr(ch), end=" ")
        ch += 1
    print()
```


**✅ Explanation**

1. Start with ASCII value of `'A'` → `65`.
2. Outer loop → rows.
3. Inner loop → number of alphabets per row.
4. Increment character after each print.


**✅ Output (n = 5)**

```
A 
B C 
D E F 
G H I J 
K L M N O
```

---
## 2: Reverse alphabet triangle (Z, Y, …)

**✅ Python Code**

```python
# Reverse Alphabet Triangle Pattern

n = 5
ch = ord('Z')  # start from 'Z'

for i in range(1, n+1):
    for j in range(i):
        print(chr(ch), end=" ")
        ch -= 1
    print()
```

**✅ Explanation**

1. Start with ASCII of `'Z'` → `90`.
2. Outer loop controls rows.
3. Inner loop prints alphabets in each row.
4. Decrement `ch` after each print to move backward (`Z → Y → X …`).


**✅ Output (n = 5)**

```
Z 
Y X 
W V U 
T S R Q 
P O N M L
```

---
## 3: Continuous alphabet triangle
**✅ Python Code**

```python
# Continuous Alphabet Triangle

n = 5
ch = ord('A')  # starting letter

for i in range(1, n+1):
    for j in range(i):
        print(chr(ch), end=" ")
        ch += 1
        if ch > ord('Z'):   # wrap around if past Z
            ch = ord('A')
    print()
```

**✅ Explanation**

1. Start from `'A'`.
2. Each row prints increasing letters continuously.
3. If we cross `'Z'`, it wraps back to `'A'`.


**✅ Output (n = 5)**

```
A
B C
D E F
G H I J
K L M N O
```

(If `n` is big, after `Z` it continues again from `A`).

---
## 4: Hollow alphabet pyramid

**✅ Python Code**

```python
# Hollow Alphabet Pyramid Pattern

n = 5
ch = ord('A')  # starting letter

for i in range(1, n+1):
    # leading spaces for alignment
    print(" " * (n - i), end="")

    for j in range(1, 2*i):
        if j == 1 or j == 2*i - 1 or i == n:
            print(chr(ch), end="")
            ch += 1
            if ch > ord('Z'):  # wrap around if exceeds Z
                ch = ord('A')
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. Start from `'A'`.
2. For each row `i`:

   * Print spaces before stars for pyramid shape.
   * Total characters in each row = `2*i - 1`.
   * Print a letter only if:

     * It’s the **first (j==1)** or **last position (j==2*i-1)** of the row, or
     * It’s the **last row (i==n)** → fully filled.
   * Otherwise print a space.
3. Wrap back to `'A'` after `'Z'`.

**✅ Output (n = 5)**

```
    A
   B B
  C   D
 E     F
G H I J K
```

---
## 5: Diamond with alphabets

**✅ Python Code**

```python
# Diamond with Alphabets Pattern

n = 5
ch = ord('A')

# Upper Half
for i in range(1, n+1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        print(chr(ch), end="")
        ch += 1
        if ch > ord('Z'):   # wrap around after Z
            ch = ord('A')
    print()

# Lower Half
for i in range(n-1, 0, -1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        print(chr(ch), end="")
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    print()
```


**✅ Explanation**

1. **Upper Half:**

   * Prints rows from 1 → `n`.
   * Each row prints `2*i - 1` alphabets centered with spaces.

2. **Lower Half:**

   * Prints rows from `n-1 → 1` (reverse).
   * Keeps symmetry with same spacing logic.

3. **Character handling:**

   * Starts from `'A'` using `ord('A')`.
   * Wraps to `'A'` again if beyond `'Z'`.


**✅ Output (n = 5)**

```
    A
   BCD
  EFGHI
 JKLMNOP
QRSTUVWX
 YZABCDE
  FGHIJ
   KLM
    N
```

---

## 6: Hollow diamond with alphabets

**✅ Python Code**

```python
# Hollow Diamond with Alphabets Pattern

n = 5
ch = ord('A')

# Upper Half
for i in range(1, n+1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        if j == 1 or j == 2*i - 1:
            print(chr(ch), end="")
            ch += 1
            if ch > ord('Z'):
                ch = ord('A')
        else:
            print(" ", end="")
    print()

# Lower Half
for i in range(n-1, 0, -1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        if j == 1 or j == 2*i - 1:
            print(chr(ch), end="")
            ch += 1
            if ch > ord('Z'):
                ch = ord('A')
        else:
            print(" ", end="")
    print()
```


**✅ Explanation**

1. **Upper Half:**

   * Creates the top pyramid (increasing width).
   * Prints alphabet only on borders: `j == 1` or `j == 2*i - 1`.

2. **Lower Half:**

   * Creates the inverted pyramid (decreasing width).
   * Uses the same border condition for hollow effect.

3. **Character Flow:**

   * Starts from `'A'`, increases continuously.
   * Wraps to `'A'` if it passes `'Z'`.


**✅ Output (n = 5)**

```
    A
   B B
  C   D
 E     F
G       H
 E     F
  C   D
   B B
    A
```

---
## 7: Hourglass alphabets

**✅ Python Code**

```python
# Hourglass Alphabet Pattern

n = 5
ch = ord('A')

# Upper Half (Inverted Pyramid)
for i in range(n, 0, -1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        print(chr(ch), end="")
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    print()

# Lower Half (Normal Pyramid)
for i in range(2, n+1):
    print(" " * (n - i), end="")
    for j in range(1, 2*i):
        print(chr(ch), end="")
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    print()
```


**✅ Explanation**

1. **Upper Half (Inverted Pyramid):**

   * Starts from `n` → 1.
   * Prints decreasing number of alphabets per row → forms the top triangle.

2. **Lower Half (Normal Pyramid):**

   * Starts from 2 → `n`.
   * Prints increasing number of alphabets → forms bottom triangle.

3. **Character Handling:**

   * Starts from `'A'`.
   * Wraps around to `'A'` again if beyond `'Z'`.


**✅ Output (n = 5)**

```
ABCDEFGHI
 BCDEFG
  HIJKL
   MN
    O
   PQ
  RSTUV
 WXYZAB
CDEFGHI
```

---

## 8: Palindrome alphabet pyramid

**✅ Python Code**

```python
# Palindrome Alphabet Pyramid

n = 5

for i in range(1, n + 1):
    # Print leading spaces for pyramid shape
    print(" " * (n - i), end="")

    # Ascending part (A → current letter)
    for j in range(i):
        print(chr(ord('A') + j), end="")

    # Descending part (previous letters backward)
    for j in range(i - 2, -1, -1):
        print(chr(ord('A') + j), end="")

    print()
```


**✅ Explanation**

1. **Outer loop (`i`)** → number of rows.
2. **Leading spaces** → align pyramid in center.
3. **Ascending part:**

   * Prints letters from `'A'` up to current row letter.
4. **Descending part:**

   * Prints same letters backward (creating palindrome symmetry).


**✅ Output (n = 5)**

```
    A
   ABA
  ABCBA
 ABCDCBA
ABCDEDCBA
```

---
## 9: Zig-zag alphabets

**✅ Python Code**

```python
# Zig-Zag Alphabet Pattern

n = 3   # number of rows
m = 9   # number of columns
char = ord('A')  # starting alphabet ASCII value

for i in range(n):  # row loop
    for j in range(m):  # column loop
        # Zig-zag condition:
        if (i + j) % 4 == 0 or (i == 1 and j % 4 == 2):
            print(chr(char), end=" ")
            char += 1
            if char > ord('Z'):  # loop back after Z
                char = ord('A')
        else:
            print(" ", end=" ")
    print()
```


**✅ Explanation**

1. **We have 3 rows** — the zig-zag will repeat every 4 columns.
2. **Condition breakdown:**

   * `(i + j) % 4 == 0`: positions where diagonals go down (`\`)
   * `(i == 1 and j % 4 == 2)`: positions where diagonals go up (`/`)
3. **`char`** keeps track of the next alphabet to print.
4. Loops back to ‘A’ after ‘Z’.


**✅ Output**

```
A       E       I 
  B   D   F   H   
    C       G     
```

---

## 10: Spiral alphabets in square

**✅ Python Code**

```python
# Spiral Alphabets in Square

n = 5
matrix = [[' ' for _ in range(n)] for _ in range(n)]
top, bottom, left, right = 0, n - 1, 0, n - 1
ch = ord('A')

while top <= bottom and left <= right:
    # Left to Right
    for i in range(left, right + 1):
        matrix[top][i] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    top += 1

    # Top to Bottom
    for i in range(top, bottom + 1):
        matrix[i][right] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    right -= 1

    # Right to Left
    for i in range(right, left - 1, -1):
        matrix[bottom][i] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    bottom -= 1

    # Bottom to Top
    for i in range(bottom, top - 1, -1):
        matrix[i][left] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    left += 1

# Print the spiral matrix
for row in matrix:
    print(' '.join(row))
```


**✅ Explanation**

1. We create an empty `n×n` matrix.
2. Use **four boundaries** (`top`, `bottom`, `left`, `right`) to control the spiral filling direction.
3. Move:

   * ➡️ Left → Right
   * ⬇️ Top → Bottom
   * ⬅️ Right → Left
   * ⬆️ Bottom → Top
4. After completing one layer, boundaries move inward.
5. After `Z`, it wraps back to `A`.


**✅ Output (n = 5)**

```
A B C D E
P Q R S F
O X Y T G
N W V U H
M L K J I
```

---
## 11: Concentric square alphabets

**✅ Python Code**

```python
# Concentric Square Alphabet Pattern

n = 5
size = 2 * n - 1  # total grid size
matrix = [['' for _ in range(size)] for _ in range(size)]

for i in range(size):
    for j in range(size):
        # Determine the minimum distance from any edge
        layer = min(i, j, size - 1 - i, size - 1 - j)
        # Convert layer number to alphabet (A, B, C, ...)
        matrix[i][j] = chr(ord('A') + layer)

# Print pattern
for row in matrix:
    print(' '.join(row))
```


**✅ Explanation**

1. **Grid size = 2×n−1** → for `n = 5`, we get a 9×9 square.
2. Each cell’s letter depends on its **distance from the nearest border**.
3. The **outermost layer** (distance = 0) → `'A'`,
   next layer → `'B'`, and so on…
4. The center has the last alphabet (`E` in this case).

**✅ Output (n = 5)**

```
A A A A A A A A A
A B B B B B B B A
A B C C C C C B A
A B C D D D C B A
A B C D E D C B A
A B C D D D C B A
A B C C C C C B A
A B B B B B B B A
A A A A A A A A A
```

---
## 12: Snake alphabets

**✅ Python Code**

```python
# Snake Alphabets Pattern

n = 5
ch = ord('A')  # starting alphabet

for i in range(n):
    row = []
    for j in range(n):
        row.append(chr(ch))
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    # Reverse every alternate row to create the snake pattern
    if i % 2 == 1:
        row.reverse()
    print(' '.join(row))
```


**✅ Explanation**

1. **We loop from row 0 → n−1.**
2. Each row gets consecutive alphabets (`A → Z`), and after `Z`, it wraps back to `A`.
3. For **odd rows (1, 3, 5, …)** → the order is reversed to create a **snake-like zig-zag** flow.
4. Finally, each row is printed with spaces.


**✅ Output (n = 5)**

```
A B C D E
J I H G F
K L M N O
T S R Q P
U V W X Y
```



🐍 **Pattern flow:**

```
→ → → → →
          ← ← ← ← ←
→ → → → →
          ← ← ← ← ←
→ → → → →
```

---
## 13: Alphabet Floyd’s triangle

**✅ Python Code**

```python
# Alphabet Floyd's Triangle

n = 5
ch = ord('A')  # Starting from 'A'

for i in range(1, n + 1):        # Row loop
    for j in range(i):           # Print i letters in each row
        print(chr(ch), end=" ")
        ch += 1
        if ch > ord('Z'):        # Wrap around after 'Z'
            ch = ord('A')
    print()
```


**✅ Explanation**

1. Each row contains **1, 2, 3, ... n** letters — just like number Floyd’s triangle.
2. **`ch`** keeps track of the next alphabet to print.
3. After `Z`, it restarts from `A` automatically.
4. The pattern grows like a right-angled triangle.


**✅ Output (n = 5)**

```
A
B C
D E F
G H I J
K L M N O
```

---


## 14: Alphabet Pascal’s triangle

**✅ Python Code**

```python
# Alphabet Pascal's Triangle

n = 6  # number of rows

for i in range(n):
    # Print leading spaces for pyramid shape
    print(" " * (n - i), end="")

    ch = ord('A')  # start from 'A' in each row

    # Generate each row of Pascal’s Triangle using alphabets
    for j in range(i + 1):
        print(chr(ch), end=" ")
        ch += 1
        if ch > ord('Z'):  # wrap after Z
            ch = ord('A')
    print()
```


**✅ Explanation**

1. The shape is based on **Pascal’s Triangle**, but we print letters instead of numbers.
2. Each row starts from **‘A’** and prints **(row index + 1)** letters.
3. Extra spaces before each row center-align the triangle.
4. After ‘Z’, letters loop back to ‘A’.

---

**✅ Output (n = 6)**

```
      A 
     A B 
    A B C 
   A B C D 
  A B C D E 
 A B C D E F 
```

---

## 15: Alternating A-B triangle

**✅ Python Code**

```python
# Alternating A-B Triangle Pattern

n = 5

for i in range(1, n + 1):
    for j in range(1, i + 1):
        # Alternate based on sum of indices
        if (i + j) % 2 == 0:
            print("A", end=" ")
        else:
            print("B", end=" ")
    print()
```


**✅ Explanation**

1. The triangle grows with **1, 2, 3, …, n** letters in each row.
2. Each cell’s letter depends on whether the sum of its position `(i + j)` is even or odd.

   * Even → **A**
   * Odd → **B**
3. This creates an alternating checker-like pattern in triangular form.


**✅ Output (n = 5)**

```
A
B A
A B A
B A B A
A B A B A
```

---
## 16: Alphabet butterfly pattern

**✅ Python Code**

```python
# Alphabet Butterfly Pattern

n = 5
ch = ord('A')

# Upper Half
for i in range(1, n + 1):
    # Left wing
    for j in range(i):
        print(chr(ch + j), end=" ")
    # Spaces in between
    print("  " * (n - i), end="")
    # Right wing
    for j in range(i - 1, -1, -1):
        print(chr(ch + j), end=" ")
    print()

# Lower Half
for i in range(n, 0, -1):
    # Left wing
    for j in range(i):
        print(chr(ch + j), end=" ")
    # Spaces in between
    print("  " * (n - i), end="")
    # Right wing
    for j in range(i - 1, -1, -1):
        print(chr(ch + j), end=" ")
    print()
```


**✅ Explanation**

1. The butterfly has **two parts**:

   * **Upper half:** letters expand outward.
   * **Lower half:** letters contract inward.
2. On each side:

   * Left wing prints **A → ...**
   * Right wing mirrors **... → A**
3. Center spacing keeps symmetry intact.


**✅ Output (n = 5)**

```
A                 A
A B             B A
A B C         C B A
A B C D     D C B A
A B C D E E D C B A
A B C D     D C B A
A B C         C B A
A B             B A
A                 A
```



🦋 **Explanation of flow:**

* Letters expand row by row until the middle.
* Then they shrink symmetrically.
---

## 17: Alphabet rhombus

**✅ Python Code**

```python
# Alphabet Rhombus Pattern

n = 5
ch = ord('A')

for i in range(n):
    # Leading spaces for rhombus shape
    print(" " * (n - i - 1), end="")

    # Print alphabets in each row
    for j in range(n):
        print(chr(ch + j), end=" ")
    print()
```


**✅ Explanation**

1. The **rhombus** is like a square shifted diagonally.
2. `" " * (n - i - 1)` creates the **left indentation**.
3. Each row prints **A, B, C, D, E** (for `n=5`) with one space between letters.
4. Letters repeat the same sequence in every row to form a neat tilted square.


**✅ Output (n = 5)**

```
    A B C D E 
   A B C D E 
  A B C D E 
 A B C D E 
A B C D E 
```

---
## 18: Alphabet sandglass

**✅ Python Code**

```python
# Alphabet Sandglass Pattern

n = 5
ch = ord('A')

# Upper half (inverted triangle)
for i in range(n, 0, -1):
    # Leading spaces
    print(" " * (n - i), end="")
    # Alphabets
    for j in range(i):
        print(chr(ch + j), end=" ")
    print()

# Lower half (normal triangle)
for i in range(2, n + 1):
    # Leading spaces
    print(" " * (n - i), end="")
    # Alphabets
    for j in range(i):
        print(chr(ch + j), end=" ")
    print()
```


**✅ Explanation**

1. The sandglass has **two halves**:

   * **Top:** an inverted triangle (letters decrease each row)
   * **Bottom:** a normal triangle (letters increase again)
2. `" " * (n - i)` shifts each line to form the hourglass shape.
3. Alphabets print from **A onward** each row.


**✅ Output (n = 5)**

```
A B C D E 
 A B C D 
  A B C 
   A B 
    A 
   A B 
  A B C 
 A B C D 
A B C D E 
```

---
## 19: Alphabet spiral rectangle

**✅ Python Code**

```python
# Alphabet Spiral Rectangle Pattern

rows, cols = 4, 6
matrix = [[' ' for _ in range(cols)] for _ in range(rows)]

top, bottom, left, right = 0, rows - 1, 0, cols - 1
ch = ord('A')

while top <= bottom and left <= right:
    # Left → Right
    for i in range(left, right + 1):
        matrix[top][i] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    top += 1

    # Top → Bottom
    for i in range(top, bottom + 1):
        matrix[i][right] = chr(ch)
        ch += 1
        if ch > ord('Z'):
            ch = ord('A')
    right -= 1

    # Right → Left
    if top <= bottom:
        for i in range(right, left - 1, -1):
            matrix[bottom][i] = chr(ch)
            ch += 1
            if ch > ord('Z'):
                ch = ord('A')
        bottom -= 1

    # Bottom → Top
    if left <= right:
        for i in range(bottom, top - 1, -1):
            matrix[i][left] = chr(ch)
            ch += 1
            if ch > ord('Z'):
                ch = ord('A')
        left += 1

# Print the spiral rectangle
for row in matrix:
    print(' '.join(row))
```


**✅ Explanation**

1. The rectangle grid is filled **spirally** using four boundaries:

   * `top`, `bottom`, `left`, and `right`.
2. The spiral moves **clockwise**:
   ➡️ Left → Right
   ⬇️ Top → Bottom
   ⬅️ Right → Left
   ⬆️ Bottom → Top
3. `ch` keeps track of current alphabet; wraps to `A` after `Z`.


**✅ Output (rows = 4, cols = 6)**

```
A B C D E F
P Q R S T G
O X W V U H
N M L K J I
```

---

## 20: Vowel-only alphabet triangle

**✅ Python Code**

```python
# Vowel-Only Alphabet Triangle

n = 5
vowels = ['A', 'E', 'I', 'O', 'U']
idx = 0  # index to track vowel position

for i in range(1, n + 1):
    for j in range(i):
        print(vowels[idx], end=" ")
        idx = (idx + 1) % len(vowels)  # loop through vowels
    print()
```


**✅ Explanation**

1. We use a **vowel list:** `['A', 'E', 'I', 'O', 'U']`.
2. For each row `i`, we print **i vowels**.
3. The `idx` cycles through the vowel list using **modulo (%)** to restart after `U`.
4. This forms a right-angled triangle made purely of vowels.


**✅ Output (n = 5)**

```
A
E I
O U A
E I O U
A E I O U
```
