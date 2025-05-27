# 11. Tries and String Algorithms

---

## What is a Trie?

A **Trie** (also called a prefix tree) is a tree-like data structure used to efficiently store and retrieve keys in a dataset of strings. It is especially useful for tasks involving prefix searches, autocomplete, and spell-checking.

---

## Trie Structure

- Each node represents a character of a string.
- Root node is empty.
- Each path from the root to a leaf (or terminal node) represents a string/key.
- Nodes may store:
  - Map/array of child nodes (for each possible character)
  - A flag to indicate if the node marks the end of a word

### Example: Trie Node (Python)

```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.is_end_of_word = False
```

---

## Basic Operations and Complexity

| Operation    | Description                  | Time Complexity (n = length of word) |
|--------------|------------------------------|--------------------------------------|
| Insert       | Add a word                   | O(n)                                 |
| Search       | Check if word exists         | O(n)                                 |
| StartsWith   | Check if prefix exists       | O(n)                                 |

---

## Sample: Trie Implementation (Python)

```python
class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]
        node.is_end_of_word = True

    def search(self, word):
        node = self.root
        for char in word:
            if char not in node.children:
                return False
            node = node.children[char]
        return node.is_end_of_word

    def startsWith(self, prefix):
        node = self.root
        for char in prefix:
            if char not in node.children:
                return False
            node = node.children[char]
        return True
```

---

## Applications of Tries

- Autocomplete/autosuggest
- Spell checker
- IP routing (longest prefix match)
- Search engines (prefix queries)
- Word games

---

## Other String Algorithms

### 1. Pattern Matching Algorithms

- **Naive Search:** Check all positions (O(m*n))
- **Knuth-Morris-Pratt (KMP):** Preprocess pattern for efficient search (O(m+n))
- **Rabin-Karp:** Hash-based search, good for multiple patterns (O(m+n))
- **Boyer-Moore:** Skips sections using heuristics, good for long alphabets

### 2. Suffix Trie/Tree & Suffix Array

- **Suffix Trie/Tree:** Stores all suffixes of a string for fast substring queries (O(n^2) space, O(n) query)
- **Suffix Array:** Sorted array of all suffixes, efficient for space and substring search

---

## Common Interview Questions

1. Implement a Trie (insert, search, startsWith).
2. Word search in a grid (backtracking + Trie).
3. Longest common prefix in a list of strings.
4. Implement autocomplete with prefix matching.
5. Find repeated substrings in a string.
6. Pattern search using KMP or Rabin-Karp.

---

## Quick Revision Table

| Structure/Algorithm | Best For            | Time Complexity | Use Case              |
|---------------------|---------------------|-----------------|-----------------------|
| Trie                | Prefix search       | O(n)            | Autocomplete, spell   |
| KMP                 | Substring search    | O(m+n)          | Pattern matching      |
| Suffix Tree         | All substring search| O(n)            | Plagiarism, bioinfo   |
| Rabin-Karp          | Multi-pattern match | O(m+n)          | Plagiarism, log scan  |

---

## References

- [GeeksforGeeks: Trie Data Structure](https://www.geeksforgeeks.org/trie-insert-and-search/)
- [GeeksforGeeks: Pattern Searching](https://www.geeksforgeeks.org/pattern-searching/)
- [Wikipedia: Trie](https://en.wikipedia.org/wiki/Trie)

---

Happy Coding! 🔤
