# 🔍 Linear Search vs Binary Search

Searching is the process of finding the position of an element in a data structure like an array.

Two common search algorithms are:

- ✅ **Linear Search**
- ⚡ **Binary Search**

---

## ✅ 1. Linear Search

### 📌 Description:

- Goes through **each element one by one** to find the target value.
- Can be used on **unsorted or sorted** arrays.

### 📋 Steps:

1. Start from the first element.
2. Compare each element with the target.
3. Return the position if found, or indicate it's not present.

### ⏱️ Time Complexity:

- **Best Case**: O(1) – if the target is at the beginning.
- **Worst Case**: O(n) – if the target is at the end or not found.

```javascript
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i; // Target found at index i
    }
  }
  return -1; // Target not found
}
```

---

## ⚡ 2. Binary Search

### 📌 Description:

- Repeatedly divides the **sorted array** in half to find the target.
- Only works on **sorted data**.

### 📋 Steps:

1. Find the middle element of the array.
2. Compare the middle element with the target.
3. If it's equal, return its position.
4. If the target is smaller, repeat the process on the left half.
5. If the target is larger, repeat on the right half.

### ⏱️ Time Complexity:

- **Best Case**: O(1)
- **Worst Case**: O(log n)

```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) {
      return mid; // Target found
    } else if (arr[mid] < target) {
      left = mid + 1; // Search right half
    } else {
      right = mid - 1; // Search left half
    }
  }

  return -1; // Target not found
}
```

---

## 📊 Comparison Table

| Feature             | Linear Search       | Binary Search     |
| ------------------- | ------------------- | ----------------- |
| **Data Required**   | Unsorted/Sorted     | Sorted only       |
| **Time Complexity** | O(n)                | O(log n)          |
| **Approach**        | Check each element  | Divide & Conquer  |
| **Simplicity**      | Very simple         | Slightly complex  |
| **Use Case**        | Small/unsorted data | Large/sorted data |

---

## ✅ Summary

- Use **Linear Search** for small or unsorted data sets.
- Use **Binary Search** for faster search on **sorted** arrays.

---
