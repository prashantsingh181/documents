# 📘 Algorithms - Introduction

## 🔍 What is an Algorithm?

An **algorithm** is a step-by-step set of instructions to solve a specific problem or perform a task.

> Think of it like a recipe: just like a cooking recipe tells you what to do step-by-step to prepare a dish, an algorithm tells a computer what steps to follow to solve a problem.

---

# ✅ Characteristics of an Algorithm

To be considered valid and effective, an algorithm must follow these five key characteristics:

---

## 1. **Clearly Defined Problem Statement, Input, and Output**

- The algorithm should begin with a **clear understanding of the problem** it is solving.
- It must specify:
  - What **input(s)** it expects.
  - What **output(s)** it will produce.

> 🔹 Example: Given an array of numbers (input), return the maximum value (output).

---

## 2. **Steps in a Specific Order**

- The steps of the algorithm must be **arranged logically**.
- The **sequence of operations matters**, as the wrong order can lead to incorrect results.

> 🔹 Just like a cooking recipe — mixing ingredients before chopping them doesn’t work!

---

## 3. **Steps Must Be Clear**

- Each step should be **simple, well-defined, and unambiguous**.
- Anyone reading the algorithm should understand exactly what to do.

> 🔹 Avoid vague instructions like “do it properly” — be precise!

---

## 4. **Must Finish in a Finite Amount of Time**

- The algorithm must **terminate** after a limited number of steps.
- It should **not run forever or get stuck in infinite loops**.

> 🔹 It must solve the problem in a predictable amount of time.

---

## 5. **Must Produce a Result**

- After completing all the steps, the algorithm must **produce a valid output**.
- The result should solve the original problem defined at the start.

> 🔹 If no result is produced, it’s not a complete algorithm.

---

## 📌 Summary Table

| Characteristic                            | Description |
|-------------------------------------------|-------------|
| **Defined Problem, Input & Output**       | What is the task, and what data goes in/out |
| **Specific Order of Steps**               | Instructions must follow a logical sequence |
| **Clear Instructions**                    | Each step must be easy to understand and execute |
| **Finite Time**                           | Algorithm must complete in limited steps |
| **Produces a Result**                     | Must return a meaningful outcome |

---


## ✅ Correctness

An algorithm is **correct** if it solves the given problem for **all valid inputs** and produces the **expected output**.

### ✔️ Key Points:
- It should handle all possible input cases (edge cases included).
- It should terminate for all possible input cases
- It should not produce errors or incorrect results.

> 🔸 Example: A sorting algorithm should always return a sorted array for any valid input.

### 📌 Tip:
> Prove correctness by using **dry runs** and **test cases**.

---

## ⚡ Efficiency

Efficiency refers to **how much time and memory** an algorithm uses when solving a problem.

### 🕒 Time Efficiency

- Measured by **Time Complexity** (usually in Big-O notation like O(n), O(log n), etc.).
- Indicates how fast the algorithm runs as input size grows.

> 🔸 Example: A linear search has O(n) time complexity.

### 💾 Space Efficiency

- Measured by **Space Complexity**.
- Refers to the amount of **extra memory** the algorithm needs besides the input.

> 🔸 Example: A recursive algorithm might use more memory due to function call stack.

---

## 📊 Trade-off: Time vs. Space

Sometimes, faster algorithms use more memory, and memory-efficient ones may run slower.

> Choose based on the problem’s requirements.

---

## 📌 Summary Table

| Measure       | What It Means                         | How to Analyze           |
|----------------|----------------------------------------|---------------------------|
| **Correctness** | Produces the right result for all inputs | Test with edge cases     |
| **Time**        | How long it takes to run              | Use Time Complexity       |
| **Space**       | How much memory it uses              | Use Space Complexity      |

---
