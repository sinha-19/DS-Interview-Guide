# 15. Memory Management & Garbage Collection

---

## What is Memory Management?

Memory management refers to the techniques and processes used by programs and operating systems to handle computer memory. It’s essential for performance, reliability, and avoiding errors like memory leaks or buffer overflows.

---

## Memory Segments

- **Stack:** Stores function call data, local variables. Managed automatically; fast but limited in size.
- **Heap:** Dynamically allocated memory; must be managed by programmer or garbage collector.
- **Data Segment:** Global/static variables.
- **Text Segment:** Program code.

---

## Stack vs Heap

| Stack                    | Heap                      |
|--------------------------|---------------------------|
| Fast allocation/deletion | Slower allocation         |
| Managed automatically    | Manual/automatic (GC)     |
| Limited size             | Usually larger            |
| Grows/shrinks automatically | Explicit management    |

### Example (C):

```c
void foo() {
    int a = 5; // Stack allocation
    int* ptr = malloc(sizeof(int)); // Heap allocation
    *ptr = 10;
    free(ptr); // Must free manually!
}
```

---

## Manual Memory Management

#### Languages: C, C++

- Use `malloc`, `calloc`, `realloc`, `free` in C.
- Use `new`, `delete` in C++.
- Programmer must keep track of resource lifetimes.

#### Dangers

- **Memory Leak:** Allocated memory not freed.
- **Dangling Pointer:** Accessing freed memory.
- **Double Free:** Freeing the same pointer twice.
- **Buffer Overflow:** Writing past array bounds.

---

## Automatic Memory Management

#### Languages: Java, Python, Go, C#.

- Rely on a **Garbage Collector (GC)** to reclaim unused memory.

### Garbage Collection Algorithms

1. **Reference Counting:** Objects are freed when reference count drops to zero.
   - Fast, but cannot handle cycles.
2. **Mark and Sweep:** Mark all reachable objects, sweep unmarked.
3. **Generational GC:** Separate objects by age; collect young ones frequently.

#### Example (Python):

```python
class MyClass:
    pass
a = MyClass()
b = a
del a  # b still references object
del b  # Now object is eligible for GC
```

---

## Smart Pointers (C++)

- **Unique Pointer (`std::unique_ptr`)**: Sole ownership, auto-deletes.
- **Shared Pointer (`std::shared_ptr`)**: Reference counting.
- **Weak Pointer (`std::weak_ptr`)**: Non-owning, avoids cycles.

---

## Memory Management Best Practices

- Always free memory after use (in manual languages).
- Use smart pointers to avoid leaks (C++).
- Avoid global/static variables unless necessary.
- Minimize object retention in managed languages (break references).
- Profile and analyze memory usage (Valgrind, LeakSanitizer, JVM profilers).

---

## Common Interview Questions

- What is a memory leak? How to detect/avoid?
- Difference between stack and heap? When to use each?
- How does GC work in Java/Python/C#?
- What is a dangling pointer? How to avoid?
- What are smart pointers?

---

## Tools for Memory Management

- **Valgrind:** Memory debugging, leak detection (C/C++).
- **GDB:** Debugger for low-level memory analysis.
- **Java VisualVM, JProfiler:** Java memory analysis.
- **Python `gc` module:** Exposure for manual GC tuning.

---

## References

- [GeeksforGeeks: Memory Management](https://www.geeksforgeeks.org/memory-management-in-c/)
- [Wikipedia: Garbage collection (computer science)](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science))
- [Valgrind](https://valgrind.org/)
- [C++ Smart Pointers](https://en.cppreference.com/w/cpp/memory)

---

## Further Reading

- "Effective C++" by Scott Meyers (for resource management idioms)
- "Java Performance: The Definitive Guide" (for JVM GC tuning)
- Official docs for your language of choice

---
