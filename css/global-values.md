# CSS Global Values

CSS provides several **global values** that allow you to control how properties behave, whether they inherit, reset, or revert to previous styles. These values ensure flexibility when managing styles across different elements.

---

## **1. `initial` (Reset to Browser Default)**

- Resets the property to the **default value** set by the browser.
- Does **not** consider parent styles.

✅ **Use Case:** When you want to remove any applied styles and return to the browser’s default behavior.

#### **Example:**

```css
p {
  color: red;
  font-size: 20px;
}

p.reset {
  color: initial; /* Goes back to default (usually black) */
  font-size: initial; /* Returns to browser default (usually 16px) */
}
```

---

## **2. `inherit` (Force Inheritance from Parent)**

- Explicitly inherits the property value from its **parent element**.
- Works even for properties that normally **do not inherit** (e.g., `margin`, `background`).

✅ **Use Case:** When you want child elements to always match their parent’s styles.

#### **Example:**

```css
div {
  color: blue;
}

p {
  color: inherit; /* Will be blue because it inherits from <div> */
}
```

---

## **3. `unset` (Smart Reset: `inherit` + `initial`)**

- Acts like `inherit` for properties that **normally inherit** (e.g., `color`, `font`).
- Acts like `initial` for properties that **do not inherit** (e.g., `margin`, `border`).

✅ **Use Case:** When you want a property to **follow its natural behavior** instead of forcing `inherit` or `initial`.

#### **Example:**

```css
p {
  color: red;
  margin: 10px;
}

p.smart-reset {
  color: unset; /* Acts like `inherit` (inherits from parent) */
  margin: unset; /* Acts like `initial` (resets to 0) */
}
```

---

## **4. `revert` (Reset to Closest Applied Style)**

- Resets the property to the **closest defined style** in the cascade (e.g., user styles, framework styles).
- If no styles exist, it behaves like `initial`.

✅ **Use Case:** When using a **CSS framework (like Bootstrap, Tailwind, or Material UI)** and you want to **remove custom styles** but keep the framework’s default styles.

#### **Example:**

```css
p {
  color: red; /* Custom style */
}

p.framework-default {
  color: revert; /* Goes back to the framework's style */
}
```

---

## **5. `revert-layer` (Reset to a Lower Cascade Layer)**

- Similar to `revert`, but only removes styles **from higher layers**, keeping styles from **lower layers** in CSS Cascade Layers (`@layer`).

✅ **Use Case:** When working with **CSS Cascade Layers** and you want to **remove a custom style but keep a framework’s styles**.

#### **Example (Using `@layer`):**

```css
@layer framework {
  p {
    color: blue;
  }
}

@layer custom {
  p {
    color: red;
  }
}

p {
  color: revert-layer; /* Resets to blue (framework layer) */
}
```

---

## **📌 Summary Table**

| **Value**          | **Behavior**                                                                   |
| ------------------ | ------------------------------------------------------------------------------ |
| **`initial`**      | Resets to **browser default**. Ignores parent styles.                          |
| **`inherit`**      | Forces **inheritance** from the parent element.                                |
| **`unset`**        | **Acts like `inherit`** for inherited properties, **`initial`** otherwise.     |
| **`revert`**       | Resets to the **closest applied style** (framework/user styles).               |
| **`revert-layer`** | Resets only styles from **higher cascade layers**, keeping lower-layer styles. |

---

### **🔹 When to Use Which?**

- ✅ **Use `initial`** when you want to **completely reset a property** to its **browser default**.
- ✅ **Use `inherit`** when you want a property to **always match its parent’s value**.
- ✅ **Use `unset`** when you want a property to **naturally behave** (either inherit or reset).
- ✅ **Use `revert`** when working with **CSS frameworks** and you want to **restore framework styles**.
- ✅ **Use `revert-layer`** when using **CSS Cascade Layers** and want to **remove only certain styles**.

---
