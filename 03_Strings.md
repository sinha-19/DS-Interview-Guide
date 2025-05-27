# 03. Strings

---

## What is a String?

A **string** is a sequence of characters, typically used to represent text. Strings are among the most common data types in programming and are supported natively by most languages.

---

## Features

- **Immutable (in most languages):** In Python, Java, strings cannot be changed after creation.
- **Indexed:** Each character has a position (starting from 0).
- **Homogeneous:** Only characters (letters, numbers, symbols).

---

## String Declaration & Initialization

### Python

```python
s = "hello"
```

### C

```c
char s[] = "hello";
```

### Java

```java
String s = "hello";
```

---

## Common String Operations

| Operation         | Time Complexity | Example              |
|-------------------|----------------|----------------------|
| Access char       | O(1)           | s[2]                 |
| Concatenation     | O(n)           | s1 + s2              |
| Substring         | O(k)           | s[1:4]               |
| Search            | O(n)           | "ab" in s            |
| Length            | O(1)           | len(s)               |

---

## String Methods (Python Examples)

```python
s = "hello world"
s.upper()          # "HELLO WORLD"
s.lower()          # "hello world"
s.find("lo")       # 3
s.replace("l", "x")# "hexxo worxd"
s.split(" ")       # ["hello", "world"]
s.strip()          # Removes whitespace
```

---

## String Immutability

- Changing a string creates a new string (does not modify original).
- Efficient for safety but can be slow for many modifications (use StringBuilder in Java, lists in Python for heavy editing).

---

## Unicode & Encoding

- Modern strings support Unicode for internationalization.
- Encoding is the process of converting strings to bytes (`utf-8`, `ascii`, etc.).

```python
s = "café"
b = s.encode("utf-8")  # b'caf\xc3\xa9'
s2 = b.decode("utf-8") # "café"
```

---

## Common Algorithms

### 1. Reverse a String

```python
s = "hello"
reversed_s = s[::-1]  # "olleh"
```

### 2. Palindrome Check

```python
def is_palindrome(s):
    return s == s[::-1]
```

### 3. Find All Substrings

```python
s = "abc"
substrings = [s[i:j] for i in range(len(s)) for j in range(i+1, len(s)+1)]
```

### 4. Anagram Check

```python
def is_anagram(a, b):
    return sorted(a) == sorted(b)
```

---

## Applications

- Text processing (search, replace, split)
- Parsing and tokenization
- Pattern matching (regular expressions)
- Cryptography (hashes)
- Data storage (CSV, JSON, XML)

---

## Regular Expressions

A powerful tool for matching patterns in strings.

```python
import re
pattern = r"\d+"
result = re.findall(pattern, "abc123def456")  # ['123', '456']
```

---

## Interview Patterns

- Sliding window for substrings (longest unique substring)
- Hash maps for frequency counting (anagrams, unique chars)
- Two pointers for palindromes, substring search

---

## Real-World Applications

- Search engines (query parsing)
- Spell checkers
- URL parsing
- Log file analysis

---

## Common Interview Questions

1. Reverse a string in-place.
2. Check if two strings are anagrams.
3. Find the longest substring without repeating characters.
4. Implement strstr() (substring search).
5. Group anagrams from a list of strings.

---

## Best Practices

- Use built-in string functions for reliability and speed.
- Avoid concatenating strings in loops; use join or StringBuilder.
- Be aware of encoding issues with Unicode data.

---

## References

- [GeeksforGeeks: Strings](https://www.geeksforgeeks.org/python-strings/)
- [Wikipedia: String (computer science)](https://en.wikipedia.org/wiki/String_(computer_science))
- [Python String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods)
- [Regular Expressions HOWTO](https://docs.python.org/3/howto/regex.html)

---

## Exercises

1. Implement function to reverse words in a string.
2. Check if a string is a valid palindrome, ignoring non-alphanumeric characters.
3. Write a regular expression to validate an email address.

---

## Summary Table

| Operation     | Complexity | Notes                        |
|---------------|------------|------------------------------|
| Access char   | O(1)       | s[i]                         |
| Search        | O(n)       | "xyz" in s                   |
| Concatenation | O(n)       | Use join for many strings    |
| Substring     | O(k)       | s[start:end]                 |
| Replace       | O(n)       | s.replace("a", "b")          |

---

Strings are fundamental: mastering their manipulation is critical for text-based algorithms and interviews!
