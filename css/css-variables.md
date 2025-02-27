# 🎨 **CSS Variables (Custom Properties)**

CSS variables (also called **custom properties**) allow you to **store reusable values** in CSS, making styling more **consistent, maintainable, and dynamic**.

---

## **1️⃣ Declaring CSS Variables**

CSS variables are defined using `--variable-name` and are typically placed inside the `:root` selector for **global scope**.

```css
:root {
  --primary-color: #3498db;
  --font-size: 18px;
}
```

📌 **`:root` ensures the variables are available globally**.

---

## **2️⃣ Using CSS Variables**

You can use the `var(--variable-name)` function to apply the variables.

```css
button {
  background-color: var(--primary-color);
  font-size: var(--font-size);
}
```

---

## **3️⃣ Changing Variables Dynamically**

CSS variables can be modified dynamically using **JavaScript**.

```js
document.documentElement.style.setProperty("--primary-color", "#e74c3c");
```

📌 **Effect:** Updates the primary color in real-time without modifying the CSS file.

---

## **4️⃣ Local vs Global Variables**

- **Global Variables**: Declared in `:root`, available everywhere.
- **Local Variables**: Declared inside a specific selector, only available inside that selector.

```css
.card {
  --card-bg: #f8f9fa;
  background-color: var(--card-bg);
}
```

📌 **Effect:** `--card-bg` is only available inside `.card`.

---

## **5️⃣ Default Fallback Values**

If a variable is not defined, you can provide a **fallback value**.

```css
h1 {
  color: var(--heading-color, black);
}
```

📌 **Effect:** Uses `--heading-color` if defined, otherwise defaults to `black`.

---

## **6️⃣ Nested Variables**

You can use variables inside other variables.

```css
:root {
  --base-size: 16px;
  --large-text: calc(var(--base-size) * 1.5);
}

p {
  font-size: var(--large-text);
}
```

---

## **🚀 Why Use CSS Variables?**

✔ **Improves maintainability** – Change one value instead of updating multiple places.  
✔ **Supports theming** – Easily switch between light and dark modes.  
✔ **Works in JavaScript** – Update styles dynamically.  
✔ **More flexibility** – Unlike SASS/LESS variables, CSS variables are runtime-based.

---

## **🎯 Quick Recap:**

```css
:root {
  --main-color: #ff5733;
}

body {
  background-color: var(--main-color);
}

button {
  background-color: var(--main-color, blue); /* Fallback */
}
```
