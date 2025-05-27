# 3. Strings

---

## What is a String?

A **string** is a sequence of characters, typically stored as an array of characters terminated by a special character (such as '\0' in C) or managed by the language (e.g., Python, Java, C++).

---

## Key Properties

- **Immutable vs Mutable:**  
  - In some languages (Java, Python), strings are immutable (cannot be changed after creation).
  - Mutable strings (e.g., StringBuilder in Java, list of chars in Python) allow in-place modifications.
- **Indexed:** Characters can be accessed by their position (index).
- **Support for Unicode:** Modern languages support Unicode for internationalization.

---

## Common Operations

| Operation      | Description                               | Time Complexity |
|----------------|-------------------------------------------|-----------------|
| Access         | Get character at index                    | O(1)            |
| Search         | Find substring or pattern                 | O(n) / O(m+n)   |
| Concatenation  | Combine two strings                       | O(n + m)        |
| Insertion      | Insert character/substring                | O(n)            |
| Deletion       | Remove character/substring                | O(n)            |
| Comparison     | Compare two strings                       | O(n)            |
| Split/Join     | Divide/join string on delimiter           | O(n)            |

---

## String Algorithms

- **Pattern Matching:** Naive, KMP, Rabin-Karp, Boyer-Moore
- **Palindrome Checking:** Two-pointer approach
- **Longest Common Substring/Subsequence**
- **Trie Data Structure:** Efficient for prefix searches

---

## Sample Code: Reverse a String (Python)

```python
def reverse_string(s):
    return s[::-1]
```

---

## Common Interview Questions

1. Reverse a string.
2. Check if a string is a palindrome.
3. Find the first non-repeating character.
4. Implement strstr() (substring search).
5. Longest substring without repeating characters.
6. Count occurrences of a character or word.

---

## Applications

- Text processing (editors, IDEs)
- Pattern matching (search engines)
- Data parsing (CSV, logs)
- Natural Language Processing (NLP)

---

## Quick Revision Table

| Feature        | Detail                              |
|----------------|-------------------------------------|
| Immutable      | Java, Python (str), C# (string)     |
| Mutable        | Java (StringBuilder), Python (list) |
| Common Uses    | Text, passwords, IDs, file paths    |
| Algorithms     | KMP, Rabin-Karp, Trie, Manacher’s   |

---

## References

- [GeeksforGeeks: String Data Structure](https://www.geeksforgeeks.org/string-data-structure/)
- [Wikipedia: String (computer science)](https://en.wikipedia.org/wiki/String_(computer_science))

---

Happy Coding! 🚀
