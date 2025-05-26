# 🧠 Big O Notation

Big O Notation is a way to **describe the performance or complexity** of an algorithm as the input size grows (or as function of the size of input).

It helps answer questions like:

- How fast is my algorithm?
- How much memory does it use?
- Will it still work efficiently if input size increases a lot?

---

## 📌 Why Use Big O?

Big O focuses on the **worst-case scenario**. It helps developers:

- Predict performance for large inputs.
- Compare different algorithms.
- Write scalable code.

---

## ⚙️ What Does It Measure?

Big O describes:

### 1. **Time Complexity**

- How the **execution time** of an algorithm grows with input size.

### 2. **Space Complexity**

- How the **memory usage** grows with input size.

---

## 📈 Common Big O Time Complexities

| Big O      | Name              | Example Scenario                  |
| ---------- | ----------------- | --------------------------------- |
| O(1)       | Constant Time     | Accessing an element in an array  |
| O(log n)   | Logarithmic Time  | Binary Search                     |
| O(n)       | Linear Time       | Loop through an array             |
| O(n log n) | Linearithmic / Quasilinear Time | Merge Sort, Quick Sort (avg case) |
| O(n²)      | Quadratic Time    | Nested loops (e.g., Bubble Sort)  |
| O(2ⁿ)      | Exponential Time  | Recursive Fibonacci               |
| O(n!)      | Factorial / Combinatorial Time    | Solving permutations              |

---

## 📊 Visual Representation

(From fastest to slowest growth)

O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)

---

## 🧠 Notes to Remember

- We ignore **constants** in Big O.  
  → `O(2n)` is simplified to `O(n)`
- We only care about the **largest term**.  
  → `O(n² + n)` becomes `O(n²)`

---

## 🛠️ Big O Rules of Thumb

1. **Single loop →** Usually O(n)
2. **Nested loops →** O(n²), O(n³), etc.
3. **Divide and Conquer →** O(log n) or O(n log n)

---

## ✅ Summary

| Term      | Meaning                             |
| --------- | ----------------------------------- |
| **Big O** | Worst-case performance measure      |
| **Time**  | Measures execution time             |
| **Space** | Measures memory usage               |
| **Goal**  | Write code with low time/space cost |

---

## 📚 Learn This First

- How loops and recursion affect complexity
- Big O of sorting/searching algorithms
- Simplifying Big O expressions

---
