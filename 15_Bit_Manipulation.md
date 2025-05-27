# 15. Bit Manipulation

---

## What is Bit Manipulation?

**Bit manipulation** is the act of algorithmically manipulating bits or binary digits (0 and 1) that make up integers and other data types. It is often used for performance optimization, space-efficient storage, and solving certain algorithmic problems efficiently.

---

## Common Bitwise Operators

| Operator | Name         | Symbol | Example             | Result       |
|----------|--------------|--------|---------------------|--------------|
| AND      | Bitwise AND  | `&`    | `5 & 3` (101 & 011) | `1`   (001)  |
| OR       | Bitwise OR   | `|`    | `5 | 3` (101 | 011) | `7`   (111)  |
| XOR      | Bitwise XOR  | `^`    | `5 ^ 3` (101 ^ 011) | `6`   (110)  |
| NOT      | Bitwise NOT  | `~`    | `~5`    (101)       | `-6`         |
| LEFT SHIFT | Shift Left | `<<`   | `5 << 1` (101)      | `10`  (1010) |
| RIGHT SHIFT| Shift Right| `>>`   | `5 >> 1` (101)      | `2`   (10)   |

---

## Common Operations

- **Check if n is odd:** `n & 1`
- **Swap two numbers:** `a ^= b; b ^= a; a ^= b`
- **Get/Set/Clear a bit:**
  - Get bit at position k: `(n >> k) & 1`
  - Set bit at position k: `n | (1 << k)`
  - Clear bit at position k: `n & ~(1 << k)`
- **Count set bits:** Use Brian Kernighan's algorithm or `bin(n).count('1')`
- **Check power of two:** `n > 0 and (n & (n-1)) == 0`

---

## Sample Tricks

### 1. Counting Set Bits (Brian Kernighan’s Algorithm)

```python
def count_set_bits(n):
    count = 0
    while n:
        n &= (n-1)
        count += 1
    return count
```

### 2. Isolate Rightmost Set Bit

```python
n & -n
```

### 3. Turn Off Rightmost Set Bit

```python
n & (n-1)
```

---

## Applications

- Subset generation (using bitmasks)
- Bitmap compression
- Fast arithmetic (multiply/divide by powers of two)
- Parity checks
- Cryptography
- Solving combinatorial problems (e.g., DP with bitmasking)
- Permissions and flags in OS

---

## Common Interview Questions

1. Count number of 1 bits in an integer.
2. Find the single number (element occurring once, others twice).
3. Find two numbers occurring once (others twice).
4. Reverse bits of an integer.
5. Find missing/duplicate number in an array.
6. Subset (power set) generation using bitmasking.
7. Check if integer is a power of two.

---

## Quick Reference Table

| Operation             | Bitwise Expression           |
|-----------------------|-----------------------------|
| Set k-th bit          | `n | (1 << k)`              |
| Clear k-th bit        | `n & ~(1 << k)`             |
| Toggle k-th bit       | `n ^ (1 << k)`              |
| Check k-th bit        | `(n >> k) & 1`              |
| Count set bits        | See above                   |
| Isolate rightmost 1   | `n & -n`                    |
| Turn off rightmost 1  | `n & (n-1)`                 |

---

## References

- [GeeksforGeeks: Bit Manipulation](https://www.geeksforgeeks.org/bitwise-algorithms/)
- [Wikipedia: Bit Manipulation](https://en.wikipedia.org/wiki/Bit_manipulation)

---

Happy Coding! 🕹️
