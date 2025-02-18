# **CSS Columns – Multi-Column Layout 📖**

The `columns` property in CSS allows you to create a **multi-column layout**, where text and content **automatically flow** into multiple columns, similar to a newspaper or magazine.

---

## **1️⃣ Basic Syntax**

You can define the number of columns, their width, or both:

```css
.container {
  columns: 3; /* Creates 3 columns */
}

.container {
  columns: 200px; /* Each column will be at least 200px wide */
}

.container {
  columns: 3 200px; /* 3 columns, each at least 200px wide */
}
```

---

## **2️⃣ Individual Column Properties**

| Property       | Description                                     | Example                         |
| -------------- | ----------------------------------------------- | ------------------------------- |
| `columns`      | Shorthand for `column-count` and `column-width` | `columns: 3 200px;`             |
| `column-count` | Specifies the **number** of columns             | `column-count: 3;`              |
| `column-width` | Specifies the **minimum width** of columns      | `column-width: 250px;`          |
| `column-gap`   | Sets **space between columns**                  | `column-gap: 30px;`             |
| `column-rule`  | Sets a **line between columns** (like `border`) | `column-rule: 2px solid black;` |
| `column-span`  | Allows elements to **span multiple columns**    | `column-span: all;`             |
| `column-fill`  | Controls how columns **fill** with content      | `column-fill: balance;`         |

---

## **3️⃣ Example: Creating a Multi-Column Layout**

```css
.container {
  columns: 3 200px;
  column-gap: 20px;
  column-rule: 2px solid gray;
}
```

```html
<div class="container">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit...</p>
</div>
```

✅ **Text will automatically flow into 3 columns!**

---

## **4️⃣ Column Span (`column-span`)**

By default, elements stay inside their assigned column, but you can make an element **span across all columns**.

```css
h2 {
  column-span: all;
  background-color: lightgray;
}
```

```html
<div class="container">
  <h2>Section Title</h2>
  <p>Content will be divided into columns...</p>
</div>
```

✅ **The `<h2>` will span across all columns.**

---

## **5️⃣ Controlling Column Filling (`column-fill`)**

Determines how content is distributed in columns.

- `column-fill: balance;` → Balances content across columns.
- `column-fill: auto;` → Fills columns in order (first gets filled, then the next).

Example:

```css
.container {
  columns: 3;
  column-fill: balance;
}
```

---

## **6️⃣ CSS Columns vs. Flexbox & Grid**

| Feature                 | CSS Columns      | Flexbox               | Grid              |
| ----------------------- | ---------------- | --------------------- | ----------------- |
| Content Flows           | ✅ Yes           | ❌ No                 | ❌ No             |
| Fixed Number of Columns | ✅ Yes           | ❌ No                 | ✅ Yes            |
| Responsive Control      | ❌ Limited       | ✅ Yes                | ✅ Yes            |
| Best for                | **Text layouts** | **Row-based layouts** | **Complex grids** |

✅ **Use `columns` for text-heavy layouts**  
✅ **Use Grid/Flexbox for full-page layouts**

---

## **🔹 Quick Takeaways**

✔ Use `columns` for **text-based layouts**, not for page structure.  
✔ `column-span: all;` lets elements span across multiple columns.  
✔ Use `column-gap` and `column-rule` for styling columns.  
✔ Consider **Flexbox or Grid** for more control over layout.
