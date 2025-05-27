# 11. Tries & Suffix Trees

---

## Tries (Prefix Trees)

### What is a Trie?
A **Trie** is a tree-like data structure that stores a dynamic set of strings, usually used for retrieval operations like autocomplete, spell-checking, and dictionary word queries. Each node represents a character of a string.

### Main Operations
- **Insert:** Add a word to the trie.
- **Search:** Check if a word exists.
- **Prefix Search:** Check if any word starts with a given prefix.
- **Delete:** Remove a word (less common due to complexity).

### Example Implementation (Python)
```python
class TrieNode:
    def __init__(self):
        self.children = {}
        self.is_end = False

class Trie:
    def __init__(self):
        self.root = TrieNode()

    def insert(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                node.children[ch] = TrieNode()
            node = node.children[ch]
        node.is_end = True

    def search(self, word):
        node = self.root
        for ch in word:
            if ch not in node.children:
                return False
            node = node.children[ch]
        return node.is_end

    def startsWith(self, prefix):
        node = self.root
        for ch in prefix:
            if ch not in node.children:
                return False
            node = node.children[ch]
        return True
```
### Trie Diagram
```
         (root)
        /   |   \
      c     d    t
      |     |    |
      a     o    h
      |     |    |
      t     g    e
                 |
                 n
```
Here, "cat", "dog", and "then" are stored.

---

## Suffix Trees

### What is a Suffix Tree?
A **Suffix Tree** is a compressed trie of all the suffixes of a given string. Useful for many string processing problems, such as substring search, longest repeated substring, etc.

### Key Properties
- Each edge is labelled with a substring of the original string.
- Each leaf represents a suffix.
- Construction time: O(n), where n is the length of the string (using Ukkonen’s algorithm).

### Example Use Cases
- Fast substring search
- Longest repeated substring
- Longest common substring (between two strings)
- Counting distinct substrings

### Suffix Tree Diagram
For the string "banana$":

```
"banana$"
|
+---- b a n a n a $
|     a n a n a $
|         n a n a $
|             a n a $
|                 n a $
|                     a $
|                         $
```

### Suffix Tree Construction (Conceptual)
- Start with all suffixes of the string.
- Insert each suffix into the tree, compressing nodes where possible.

### Suffix Tree vs. Suffix Array
- **Suffix Tree:** Fast for substring queries, more complex to implement.
- **Suffix Array:** More space-efficient, often used with LCP array for similar queries.

---

## Common Interview Questions
1. Implement a Trie with insert, search, and startsWith.
2. Given a list of words, find the longest word that is built one character at a time by other words in the list.
3. Find all words in a dictionary that match a given prefix.
4. Find the longest repeated substring in a string.

---

## References
- [GeeksforGeeks: Trie Data Structure](https://www.geeksforgeeks.org/trie-insert-and-search/)
- [GeeksforGeeks: Suffix Tree Introduction](https://www.geeksforgeeks.org/suffix-tree-introduction/)
- [Stanford Trie and Suffix Tree Explanation (PDF)](https://web.stanford.edu/class/cs97si/suffix-tree.pdf)
- [Wikipedia: Trie](https://en.wikipedia.org/wiki/Trie)
- [Wikipedia: Suffix tree](https://en.wikipedia.org/wiki/Suffix_tree)

---
