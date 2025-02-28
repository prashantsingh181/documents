# **CSS Specificity**

[Specificity Calculator](https://specificity.keegan.st/)

**Specificity** is a set of rules that determine which CSS selector takes priority when multiple styles apply to the same element. Understanding specificity helps you **resolve style conflicts** and **avoid unnecessary `!important` usage**.

---

## **1. How Specificity Works**

Each CSS rule gets a **specificity score** based on the types of selectors used. The higher the score, the stronger the rule.

### **Specificity Calculation (Point System)**

| Selector Type                                                                                                   | Example                                  | Score (A, B, C, D) |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | ------------------ |
| **Inline Styles**                                                                                               | `<p style="color: red;">`                | (1, 0, 0, 0)       |
| **ID Selector (`#id`)**                                                                                         | `#main`                                  | (0, 1, 0, 0)       |
| **Class Selector (`.class`)**<br>**Attribute Selector (`[attr]`)**<br>**Pseudo-Class (`:hover`, `:nth-child`)** | `.button`<br>`[type="text"]`<br>`:focus` | (0, 0, 1, 0)       |
| **Element Selector (`div, p`)**<br>**Pseudo-Element (`::before`, `::after`)**                                   | `div`<br>`p::before`                     | (0, 0, 0, 1)       |
| **Universal Selector (`*`)**<br>**Combinators (`>`, `+`, `~`, ` `)**                                            | `*`, `div > p`                           | (0, 0, 0, 0)       |

🔹 **More important selectors (higher specificity) override less specific ones.**

---

## **2. Specificity Examples**

#### **Example 1: Basic Specificity**

```css
div {
  color: blue;
} /* (0, 0, 0, 1) */
#main {
  color: red;
} /* (0, 1, 0, 0) */
```

- The **ID selector (`#main`) wins** because `(0,1,0,0)` is stronger than `(0,0,0,1)`.

#### **Example 2: Combining Selectors**

```css
p {
  color: blue;
} /* (0, 0, 0, 1) */
p.special {
  color: green;
} /* (0, 0, 1, 1) */
#content p.special {
  color: red;
} /* (0, 1, 1, 1) */
```

- **Final color of `<p class="special">` inside `#content`?** → **Red**, because `(0,1,1,1)` is the highest.

---

## **3. Important Specificity Rules**

### **🔹 Rule 1: More Selectors = Higher Specificity**

```css
p {
  color: blue;
} /* (0,0,0,1) */
p.special {
  color: green;
} /* (0,0,1,1) */
```

✅ `.special` adds extra weight, so **green wins**.

---

### **🔹 Rule 2: Inline Styles Override Everything (Except `!important`)**

```html
<p id="main" class="special" style="color: orange;">Text</p>
```

```css
p {
  color: blue;
} /* (0,0,0,1) */
#main {
  color: red;
} /* (0,1,0,0) */
```

✅ Inline `style="color: orange;"` **wins** because **(1,0,0,0) > (0,1,0,0) > (0,0,0,1)**.

---

### **🔹 Rule 3: `!important` Overrides Specificity**

```css
p {
  color: blue !important;
} /* Forces blue */
#main {
  color: red;
} /* (0,1,0,0) */
```

✅ **`!important` wins**, even though `#main` has a higher specificity.

⚠️ **Use `!important` wisely**—it can make debugging hard!

---

## **4. Tiebreakers & Source Order**

If **two selectors have the same specificity**, the **one that appears last** in the CSS file wins.

#### **Example:**

```css
p {
  color: blue;
} /* (0,0,0,1) */
p {
  color: red;
} /* (0,0,0,1) (comes later) */
```

✅ **Red wins** because it appears **last**.

---

## **5. Summary Table**

| Specificity Strength | Selector Type                       | Example                              |
| -------------------- | ----------------------------------- | ------------------------------------ |
| **Highest**          | Inline Styles                       | `style="color: red;"`                |
|                      | ID Selectors                        | `#header`                            |
|                      | Classes, Attributes, Pseudo-Classes | `.button`, `[type="text"]`, `:hover` |
|                      | Elements, Pseudo-Elements           | `div`, `p::before`                   |
| **Lowest**           | Universal Selector, Combinators     | `*`, `div > p`                       |

---

## **🔹 Best Practices to Avoid Specificity Issues**

✔ **Use class names (`.class`) instead of IDs (`#id`)** for styling.  
✔ **Keep specificity low** to make styles easy to override.  
✔ **Use `!important` only when absolutely necessary.**  
✔ **Use a clear naming convention** to avoid conflicts.
