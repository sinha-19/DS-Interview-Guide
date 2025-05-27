# 14. Bit Manipulation & Bitwise Tricks

---

## Introduction

Bit manipulation is the direct handling of individual bits within binary representations of numbers. It’s a fundamental tool in computer science, enabling efficient computations, compact data storage, and clever algorithmic tricks. Mastery of bitwise operations is a hallmark of strong programmers and is often tested in technical interviews.

---

## Bitwise Operators

| Operator | Symbol | Description                         | Example          | Result   |
|----------|--------|-------------------------------------|------------------|----------|
| AND      | `&`    | 1 if both bits are 1                | `5 & 3`          | 1        |
| OR       | `|`    | 1 if either bit is 1                | `5 | 3`          | 7        |
| XOR      | `^`    | 1 if bits are different              | `5 ^ 3`          | 6        |
| NOT      | `~`    | Inverts bits                        | `~5`             | -6       |
| LEFT SH  | `<<`   | Shifts bits left, adds zeros        | `5 << 1`         | 10       |
| RIGHT SH | `>>`   | Shifts bits right, discards bits    | `5 >> 1`         | 2        |

#### Example (binary):

```
  5: 101
  3: 011
---------
5 & 3: 001 (1)
5 | 3: 111 (7)
5 ^ 3: 110 (6)
~5   : ...11111010 (-6 in two's complement)
```

---

## Common Bit Manipulation Techniques

### 1. Check if a Number is Odd or Even

```python
def is_odd(n):
    return n & 1 == 1  # True if odd
```

### 2. Swap Two Numbers Without a Temporary Variable

```python
a, b = 5, 7
a ^= b
b ^= a
a ^= b
```

### 3. Get, Set, and Clear a Bit

- **Get k-th bit:** `(n >> k) & 1`
- **Set k-th bit:** `n | (1 << k)`
- **Clear k-th bit:** `n & ~(1 << k)`
- **Toggle k-th bit:** `n ^ (1 << k)`

#### Example:

```python
n = 10  # 1010
k = 1
print((n >> k) & 1)  # 1 (2nd bit from right is 1)
```

### 4. Counting Set Bits (Brian Kernighan’s Algorithm)

```python
def count_set_bits(n):
    count = 0
    while n:
        n &= (n - 1)
        count += 1
    return count
```

### 5. Check if a Number is a Power of Two

```python
def is_power_of_two(n):
    return n > 0 and (n & (n - 1)) == 0
```

---

## Bitmasking

A bitmask is an integer where each bit represents a state (on/off, true/false). Bitmasking is used for compactly representing sets, subsets, flags, and permissions.

### Example: Subset Generation

```python
nums = [1, 2, 3]
n = len(nums)
for mask in range(1 << n):
    subset = []
    for i in range(n):
        if mask & (1 << i):
            subset.append(nums[i])
    print(subset)
```

---

## Advanced Bit Tricks

### 1. Isolate the Rightmost Set Bit

```python
n = 12  # 1100
print(n & -n)  # 4 (0100)
```

### 2. Turn Off the Rightmost Set Bit

```python
n = 10  # 1010
print(n & (n - 1))  # 8 (1000)
```

### 3. Count Number of Bits to Convert A to B

```python
def bits_to_convert(a, b):
    return count_set_bits(a ^ b)
```

### 4. Reverse Bits in an Integer

```python
def reverse_bits(n, num_bits):
    rev = 0
    for i in range(num_bits):
        rev = (rev << 1) | (n & 1)
        n >>= 1
    return rev
```

---

## Application Scenarios

- **Permissions and Flags:** File access, user rights, configuration.
- **Compression:** Bit-packing data to save space.
- **Cryptography:** XOR-based encryption.
- **Dynamic Programming:** Representing states as bitmasks for optimization.
- **Game Development:** Board states, toggling features, AI.

---

## Interview Patterns Using Bit Manipulation

1. **Single Number:** Find the element that appears once when all others appear twice.
   - Use XOR: `reduce(lambda x, y: x ^ y, arr)`

2. **Two Single Numbers:** Find two numbers that appear only once.
   - XOR all, find rightmost set bit, partition.

3. **Missing/Repeated Number in Array:** XOR all numbers and indices.

4. **Power Set Generation:** Use bitmask to represent inclusion/exclusion.

5. **Bitwise AND/OR of Range:** Efficiently compute for large intervals.

---

## Gotchas & Tips

- Bitwise NOT (~) in Python returns negative numbers due to two’s complement.
- Left shift (`<<`) multiplies by 2, right shift (`>>`) divides by 2 (for positive numbers).
- Always use parentheses to clarify precedence in expressions.
- Be wary of integer overflow in lower-level languages (C/C++).

---

## Practice Problems

- [LeetCode: Single Number](https://leetcode.com/problems/single-number/)
- [LeetCode: Counting Bits](https://leetcode.com/problems/counting-bits/)
- [LeetCode: Subsets](https://leetcode.com/problems/subsets/)
- [GeeksforGeeks: Bitwise Algorithms](https://www.geeksforgeeks.org/bitwise-algorithms/)

---

## References

- [GeeksforGeeks: Bit Manipulation](https://www.geeksforgeeks.org/bitwise-algorithms/)
- [Wikipedia: Bit manipulation](https://en.wikipedia.org/wiki/Bit_manipulation)
- [Bit Twiddling Hacks](https://graphics.stanford.edu/~seander/bithacks.html)

---
