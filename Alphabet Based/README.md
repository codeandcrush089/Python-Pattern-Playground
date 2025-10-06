## 1: Alphabet triangle (A, B, C, …)

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
