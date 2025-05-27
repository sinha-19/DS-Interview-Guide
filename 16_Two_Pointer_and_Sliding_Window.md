# 16. Two Pointer & Sliding Window Techniques

---

## Two Pointer Technique

### What is it?

The **two pointer technique** involves using two indices (pointers) that move through a data structure (usually an array or linked list) to solve problems efficiently, often in linear time.

---

### Common Patterns

- **Opposite Ends:** Start pointers at each end and move toward each other (e.g., for palindromes, pair sums).
- **Same Direction:** Both pointers start at the beginning and move forward (e.g., removing duplicates, partitioning).

---

### Typical Use Cases

- Pair with given sum in a sorted array
- Reverse an array in-place
- Remove duplicates in-place from a sorted array
- Partitioning arrays
- Checking for palindromes

---

### Example: Two Sum in Sorted Array

```python
def two_sum(nums, target):
    left, right = 0, len(nums) - 1
    while left < right:
        s = nums[left] + nums[right]
        if s == target:
            return [left, right]
        elif s < target:
            left += 1
        else:
            right -= 1
    return []
```

---

## Sliding Window Technique

### What is it?

The **sliding window technique** is a method to reduce the time complexity of some problems involving arrays/lists/strings. The idea is to maintain a window (subarray/substring) that "slides" over the input.

---

### Window Types

- **Fixed Window Size:** The window size is constant (e.g., maximum sum of k consecutive elements).
- **Variable Window Size:** The window expands and contracts based on conditions (e.g., minimum-length substring with all characters).

---

### Typical Use Cases

- Longest/shortest substring with specific properties
- Maximum sum subarray of size k
- Counting distinct elements in every window of size k
- Anagrams in a string

---

### Example: Maximum Sum Subarray of Size K

```python
def max_sum_subarray(nums, k):
    max_sum = curr_sum = sum(nums[:k])
    for i in range(k, len(nums)):
        curr_sum += nums[i] - nums[i - k]
        max_sum = max(max_sum, curr_sum)
    return max_sum
```

---

### Example: Longest Substring Without Repeating Characters

```python
def length_of_longest_substring(s):
    seen = {}
    left = max_len = 0
    for right, char in enumerate(s):
        if char in seen and seen[char] >= left:
            left = seen[char] + 1
        seen[char] = right
        max_len = max(max_len, right - left + 1)
    return max_len
```

---

## Applications

- String processing (substrings, anagrams, palindromes)
- Subarray and subsequence problems
- Array partitioning and searching
- Data stream analysis

---

## Common Interview Questions

1. Two sum in sorted array
2. Remove duplicates from sorted array
3. Longest substring without repeating characters
4. Minimum window substring
5. Smallest subarray with sum ≥ target
6. Find all anagrams of a pattern in a string

---

## Quick Revision Table

| Technique      | Use Case                      | Time Complexity | Space Complexity |
|----------------|------------------------------|-----------------|------------------|
| Two Pointer    | Pair sum, reverse, palindrome| O(n)            | O(1)             |
| Sliding Window | Subarrays/substrings         | O(n)            | O(1) – O(k)      |

---

## References

- [GeeksforGeeks: Two Pointer Technique](https://www.geeksforgeeks.org/two-pointers-technique/)
- [LeetCode: Sliding Window Problems](https://leetcode.com/tag/sliding-window/)
- [GeeksforGeeks: Sliding Window](https://www.geeksforgeeks.org/window-sliding-technique/)

---

Happy Coding! 🚦
