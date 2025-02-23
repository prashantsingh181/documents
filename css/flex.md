# **CSS Flexbox – The Complete Guide**

CSS Flexbox (**Flexible Box Layout**) is a **one-dimensional** layout model that helps position and distribute elements **horizontally or vertically**. It provides **better control** over alignment, spacing, and resizing of elements inside a container.

---

## **1️⃣ How to Enable Flexbox?**

Flexbox is enabled using `display: flex;` on a **container**. The elements inside this container become **flex items**.

```css
.container {
  display: flex;
}
```

✅ **Example**:

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

---

# **2️⃣ Flexbox Terminology**

Before diving deep, here’s an overview of the **main concepts**:

- **Flex Container** → The parent element that holds flex items.
- **Flex Items** → The child elements inside the flex container.
- **Main Axis** → The **primary direction** (`row` or `column`).
- **Cross Axis** → Perpendicular to the **main axis**.

---

# **3️⃣ `display: flex;` vs. `display: inline-flex;`**

| Property      | Description                                 |
| ------------- | ------------------------------------------- |
| `flex`        | Creates a **block-level** flex container.   |
| `inline-flex` | Creates an **inline-level** flex container. |

```css
.container {
  display: flex; /* Block-level flex container */
}

.container-inline {
  display: inline-flex; /* Inline-level flex container */
}
```

---

# **4️⃣ `flex-direction` – Main Axis Direction**

Controls the **direction** of the **main axis**.

```css
.container {
  display: flex;
  flex-direction: row; /* Default */
}
```

| Value            | Description                          |
| ---------------- | ------------------------------------ |
| `row`            | (Default) Items go **left → right**. |
| `row-reverse`    | Items go **right → left**.           |
| `column`         | Items go **top → bottom**.           |
| `column-reverse` | Items go **bottom → top**.           |

✅ **Example**

```css
.container {
  flex-direction: column;
}
```

---

# **5️⃣ `justify-content` – Align on Main Axis**

Controls **horizontal alignment** (`row`) or **vertical alignment** (`column`).

```css
.container {
  justify-content: center;
}
```

| Value           | Description                               |
| --------------- | ----------------------------------------- |
| `flex-start`    | (Default) Aligns items to the **start**.  |
| `flex-end`      | Aligns items to the **end**.              |
| `center`        | Centers items.                            |
| `space-between` | Even spacing **without gaps at edges**.   |
| `space-around`  | Even spacing **with gaps on edges**.      |
| `space-evenly`  | **Equal space** between and around items. |

✅ **Example**

```css
.container {
  justify-content: space-between;
}
```

---

# **6️⃣ `align-items` – Align on Cross Axis**

Controls **vertical alignment** (`row`) or **horizontal alignment** (`column`).

```css
.container {
  align-items: center;
}
```

| Value        | Description                               |
| ------------ | ----------------------------------------- |
| `stretch`    | (Default) Stretches items to fill height. |
| `flex-start` | Aligns items to the **top**.              |
| `flex-end`   | Aligns items to the **bottom**.           |
| `center`     | Centers items **vertically**.             |
| `baseline`   | Aligns items based on **text baseline**.  |

✅ **Example**

```css
.container {
  align-items: baseline;
}
```

---

# **7️⃣ `flex-wrap` – Wrap or No Wrap?**

By default, flex items **shrink** to fit the container.

```css
.container {
  flex-wrap: wrap;
}
```

| Value          | Description                          |
| -------------- | ------------------------------------ |
| `nowrap`       | (Default) Items **stay in one row**. |
| `wrap`         | Items **wrap** to new rows.          |
| `wrap-reverse` | Items wrap in **reverse order**.     |

✅ **Example**

```css
.container {
  flex-wrap: wrap;
}
```

---

# **8️⃣ `align-content` – Multiple Rows Alignment**

Only works if `flex-wrap: wrap;` is applied.

```css
.container {
  align-content: space-around;
}
```

| Value           | Description                                  |
| --------------- | -------------------------------------------- |
| `flex-start`    | Rows align at the **top**.                   |
| `flex-end`      | Rows align at the **bottom**.                |
| `center`        | Rows align at the **center**.                |
| `space-between` | **Even spacing** between rows.               |
| `space-around`  | **Equal space around** rows.                 |
| `stretch`       | (Default) Rows **stretch** to fit container. |

✅ **Example**

```css
.container {
  align-content: space-between;
}
```

---

# **9️⃣ `flex` – Control Item Size**

The **shorthand** for `flex-grow`, `flex-shrink`, and `flex-basis`.

```css
.item {
  flex: 1; /* All items take equal space */
}
```

| Property      | Description                    |
| ------------- | ------------------------------ |
| `flex-grow`   | Controls how items **expand**. |
| `flex-shrink` | Controls how items **shrink**. |
| `flex-basis`  | Sets **default item size**.    |

✅ **Example**

```css
.item {
  flex: 2 1 100px; /* grow, shrink, basis */
}
```

---

# **🔟 `order` – Change Item Order**

Changes the **visual order** without changing HTML structure.

```css
.item {
  order: 2; /* Moves to the end */
}
```

| Value | Description                          |
| ----- | ------------------------------------ |
| `0`   | (Default) Items follow source order. |
| `> 0` | Moves item **later** in the order.   |
| `< 0` | Moves item **earlier** in the order. |

✅ **Example**

```css
.item:nth-child(2) {
  order: -1; /* Moves before others */
}
```

---

# **🔹 Example: Responsive Navbar with Flexbox**

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.nav-links {
  display: flex;
  gap: 20px;
}
```

```html
<nav class="navbar">
  <div class="logo">LOGO</div>
  <div class="nav-links">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>
</nav>
```

✅ **Responsive, flexible navbar!**

---

# **🎯 Flexbox Cheatsheet**

```css
.container {
  display: flex;
  flex-direction: row; /* row | row-reverse | column | column-reverse */
  justify-content: flex-start; /* flex-start | flex-end | center | space-between | space-around | space-evenly */
  align-items: stretch; /* flex-start | flex-end | center | stretch | baseline */
  flex-wrap: nowrap; /* nowrap | wrap | wrap-reverse */
  align-content: flex-start; /* flex-start | flex-end | center | space-between | space-around | stretch */
}

.item {
  flex-grow: 0; /* 0 (default) | Positive integer */
  flex-shrink: 1; /* 1 (default) | 0 (no shrinking) */
  flex-basis: auto; /* auto | px | % | rem */
  flex: 0 1 auto; /* flex-grow flex-shrink flex-basis */
  order: 0; /* 0 (default) | Positive/Negative integers */
}
```

---

# **🚀 When to Use Flexbox?**

✔ **Best for** one-dimensional layouts.  
✔ **Perfect for** centering items.  
✔ **Ideal for** navigation bars, buttons, and responsive UI.  
❌ **Use Grid for** complex two-dimensional layouts.

---
