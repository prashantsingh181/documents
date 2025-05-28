# How to Calculate Time Complexity Mathematically

Understanding time complexity isn’t just about memorizing Big-O notations — it’s about knowing how to **derive** them from code using **step-by-step analysis**.

---

## Step-by-Step Analysis

You can calculate time complexity by counting the number of operations relative to the input size `n`.

### Example 1: Linear Loop

```javascript
function sum(arr) {
  let total = 0;
  for (let i = 0; i < arr.length; i++) {
    total += arr[i];
  }
  return total;
}
```

**Analysis:**

- Line 2: `let total = 0` → 1 operation
- Loop runs `n` times (length of `arr`)
  - Each iteration does `total += arr[i]` → 1 operation
- Total: `1 + n` operations ⇒ **O(n)**

---

## Example 2: Nested Loop

```javascript
function printPairs(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]);
    }
  }
}
```

**Analysis:**

- Outer loop runs `n` times
- Inner loop runs `n` times for each outer iteration
- Total operations: `n * n = n²` ⇒ **O(n²)**

---

## Example 3: Logarithmic Complexity

```javascript
function binarySearch(arr, target) {
  let low = 0,
    high = arr.length - 1;
  while (low <= high) {
    let mid = Math.floor((low + high) / 2);
    if (arr[mid] === target) return mid;
    else if (arr[mid] < target) low = mid + 1;
    else high = mid - 1;
  }
  return -1;
}
```

**Analysis:**

- Each iteration halves the array size:
  - n → n/2 → n/4 → n/8 → ... → 1
- This continues for `log₂(n)` times
- Total: **O(log n)**

---

## Example 4: Recursive Fibonacci

```javascript
function fib(n) {
  if (n <= 1) return n;
  return fib(n - 1) + fib(n - 2);
}
```

**Analysis:**

- Let T(n) be the number of calls for fib(n)
- T(n) = T(n - 1) + T(n - 2) + 1
- This forms an exponential recurrence:
  - T(n) ≈ 2ⁿ
- Total: **O(2ⁿ)**

---

## Using Summations

### Example: Two Separate Loops

```javascript
function example(arr) {
  for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
  }
  for (let j = 0; j < arr.length; j++) {
    console.log(arr[j]);
  }
}
```

**Analysis:**

- First loop: n operations
- Second loop: n operations
- Total = n + n = 2n ⇒ Drop constants ⇒ **O(n)**

---

### Example: Triangular Pattern (Nested Loop with Shrinking Range)

```javascript
function triangularPattern(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; j <= i; j++) {
      console.log(i, j);
    }
  }
}
```

**Analysis:**

- Inner loop runs:
  - 1 time on i = 0
  - 2 times on i = 1
  - ...
  - n times on i = n-1
- Total operations: 1 + 2 + 3 + ... + n = n(n + 1)/2
- Drop constants and lower-order terms ⇒ **O(n²)**

---

## General Steps to Find Time Complexity

1. Count the number of primitive operations inside loops/functions
2. Use summation formulas if needed
3. Keep the most significant term (as n → ∞)
4. Drop constants
5. Result is Big-O

---

## Common Summation Formulas

- Sum of first n numbers:  
  1 + 2 + 3 + ... + n = n(n + 1)/2 ⇒ O(n²)

- Sum of a geometric series:  
  1 + 2 + 4 + 8 + ... + 2^k = 2ⁿ - 1 ⇒ O(2ⁿ)

- Logarithmic splits:  
  n + n/2 + n/4 + ... + 1 = 2n ⇒ O(n)

---

## Conclusion

Time complexity helps predict how code behaves as input grows. By analyzing loops, recursion, and summations, we can **mathematically estimate** the performance of any algorithm.
