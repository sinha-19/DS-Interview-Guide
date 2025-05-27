# 16. Interview Patterns (Sliding Window, Two Pointer, etc.)

---

## Introduction

Mastering common problem-solving patterns accelerates algorithmic thinking and interview performance. This section covers **sliding window**, **two pointer**, **fast & slow pointer**, **monotonic stack/queue**, **binary search on answer**, and **backtracking**.

---

## Sliding Window

Efficiently processes subarrays/substrings by maintaining a "window" over the data.

### Types

- **Fixed window:** Window size is constant (e.g., max sum of k elements)
- **Variable window:** Window expands/contracts to satisfy constraints (e.g., longest substring with k distinct chars)

### Example: Maximum Sum Subarray (Fixed Window)

```python
def max_sum_subarray(nums, k):
    window_sum = sum(nums[:k])
    max_sum = window_sum
    for i in range(k, len(nums)):
        window_sum += nums[i] - nums[i-k]
        max_sum = max(max_sum, window_sum)
    return max_sum
```

### Example: Longest Substring with K Distinct Chars (Variable Window)

```python
def longest_k_distinct(s, k):
    from collections import defaultdict
    left = 0
    counts = defaultdict(int)
    max_len = 0
    for right, c in enumerate(s):
        counts[c] += 1
        while len(counts) > k:
            counts[s[left]] -= 1
            if counts[s[left]] == 0:
                del counts[s[left]]
            left += 1
        max_len = max(max_len, right - left + 1)
    return max_len
```

---

## Two Pointer Technique

Use two indices moving through the data, from the same or opposite ends.

### Patterns

- **Opposite ends:** For sorted arrays (pair sum, palindrome)
- **Same direction:** Removing duplicates, partitioning

### Example: Pair Sum in Sorted Array

```python
def has_pair_with_sum(arr, target):
    arr.sort()
    l, r = 0, len(arr)-1
    while l < r:
        s = arr[l] + arr[r]
        if s == target:
            return True
        elif s < target:
            l += 1
        else:
            r -= 1
    return False
```

---

## Fast & Slow Pointer (Tortoise and Hare)

Used for cycle detection in linked lists or arrays.

### Example

```python
def has_cycle(head):
    fast = slow = head
    while fast and fast.next:
        fast = fast.next.next
        slow = slow.next
        if fast == slow:
            return True
    return False
```

---

## Monotonic Stack/Queue

Stack or queue that maintains increasing/decreasing elements for efficient "next greater/smaller" queries.

### Example: Next Greater Element

```python
def next_greater(nums):
    stack = []
    res = [-1] * len(nums)
    for i, num in enumerate(nums):
        while stack and nums[stack[-1]] < num:
            res[stack.pop()] = num
        stack.append(i)
    return res
```

---

## Binary Search on Answer

Binary search not on data but on the solution space, commonly for optimization problems.

### Example: Minimum Capacity to Ship Packages

- Guess a capacity, check if feasible, adjust search.

---

## Backtracking

Systematic search for solutions by exploring all possibilities recursively and undoing choices.

### Example: N-Queens

- Place queens row by row, backtrack if conflict.

---

## Practice Problems

- Longest substring without repeating characters (LeetCode 3)
- Minimum window substring (LeetCode 76)
- Two sum, three sum, four sum (LeetCode 1/15/18)
- Detect cycle in linked list (LeetCode 141)
- Next greater element (LeetCode 496)
- N-Queens (LeetCode 51)
- Subsets/permutations/combinations (LeetCode 78, 46, 39)

---

## Interview Tips

- Recognize which pattern fits the problem.
- Draw diagrams for pointers/windows.
- Optimize only after a brute-force solution.
- Write test cases for edge situations.

---

## References

- [NeetCode Patterns](https://neetcode.io/practice)
- [GeeksforGeeks: Two Pointer Technique](https://www.geeksforgeeks.org/two-pointers-technique/)
- [LeetCode: Sliding Window](https://leetcode.com/tag/sliding-window/)

---
