# Space Complexity in Data Structures and Algorithms

**Space Complexity** is a measure of the **amount of memory** an algorithm uses as a function of the input size. It includes:

1. Input space (sometimes excluded if input is reused)
2. Auxiliary space (temporary variables, call stack, etc.)

---

## Why Space Complexity?

- Helps determine how much memory your program will need.
- Important for optimizing performance on devices with limited memory.

---

## Big-O Notation for Space

| Big-O    | Meaning           | Example                         |
| -------- | ----------------- | ------------------------------- |
| O(1)     | Constant space    | Using a few variables           |
| O(n)     | Linear space      | Copying an array                |
| O(n²)    | Quadratic space   | 2D matrix                       |
| O(log n) | Logarithmic space | Recursive binary search         |
| O(n + m) | Combined space    | Two separate arrays of size n,m |

---

## How to Calculate Space Complexity

We analyze:

- Variables
- Data structures (arrays, objects, stacks, etc.)
- Recursion stack
- Function call stack

---

### Example 1: O(1) - Constant Space

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

- Only one variable `total` and one loop variable `i`
- No matter how big `arr` is, memory usage stays the same
- **Space Complexity: O(1)**

---

### Example 2: O(n) - Linear Space

```javascript
function doubleValues(arr) {
  let result = [];
  for (let i = 0; i < arr.length; i++) {
    result.push(arr[i] * 2);
  }
  return result;
}
```

**Analysis:**

- Result array stores a value for each input item
- Additional space grows linearly with `n`
- **Space Complexity: O(n)**

---

### Example 3: O(n²) - Quadratic Space

```javascript
function createMatrix(n) {
  let matrix = [];
  for (let i = 0; i < n; i++) {
    matrix[i] = [];
    for (let j = 0; j < n; j++) {
      matrix[i][j] = 0;
    }
  }
  return matrix;
}
```

**Analysis:**

- A 2D array of size `n × n` is created
- **Space Complexity: O(n²)**

---

### Example 4: O(log n) - Recursive Binary Search

```javascript
function binarySearch(arr, low, high, target) {
  if (low > high) return -1;
  let mid = Math.floor((low + high) / 2);
  if (arr[mid] === target) return mid;
  if (arr[mid] > target) return binarySearch(arr, low, mid - 1, target);
  else return binarySearch(arr, mid + 1, high, target);
}
```

**Analysis:**

- Recursive calls add frames to the call stack
- Each level halves the array ⇒ total levels = log₂(n)
- **Space Complexity: O(log n)**

---

### Example 5: O(n) - Recursive Fibonacci

```javascript
function fib(n) {
  if (n <= 1) return n;
  return fib(n - 1) + fib(n - 2);
}
```

**Analysis:**

- For every `fib(n)`, two calls are made
- Call stack depth = `n`
- **Space Complexity: O(n)** due to recursive stack frames

---

## General Space Complexity Rules

1. **Variables** → count them if they depend on input size
2. **Data structures** → arrays, objects, matrices = use memory
3. **Recursive functions** → add call stack space
4. **Function parameters** → generally don’t count input parameters
5. **In-place operations** → often O(1) space

---

## Comparing Time vs Space

| Scenario                     | Time Complexity | Space Complexity |
| ---------------------------- | --------------- | ---------------- |
| Sum of array                 | O(n)            | O(1)             |
| Cloning an array             | O(n)            | O(n)             |
| Fibonacci recursive          | O(2ⁿ)           | O(n)             |
| Fibonacci dynamic (memoized) | O(n)            | O(n)             |
| Merge Sort                   | O(n log n)      | O(n)             |

---

## Conclusion

Space complexity helps you understand how efficiently your code uses memory. It’s especially important in resource-constrained environments or when dealing with large data.

- Favor **O(1)** space when possible
- Be mindful of recursion and data structures
