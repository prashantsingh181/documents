# 🎯 **CSS Grid**

CSS Grid is a **powerful layout system** that allows you to design complex, responsive layouts **easily**. It provides **rows and columns** to align elements efficiently.

---

## **📌 1️⃣ Basics of CSS Grid**

To create a **grid container**, apply `display: grid` to a parent element:

```css
.container {
  display: grid;
}
```

🔹 **Grid Terminology:**  
✔ **Grid Container** → The parent element with `display: grid`.  
✔ **Grid Items** → Direct children of the container.  
✔ **Grid Lines** → Horizontal & vertical dividing lines.  
✔ **Grid Tracks** → Rows & columns between grid lines.  
✔ **Grid Cells** → Single space between grid lines.  
✔ **Grid Areas** → Group of grid cells forming a section.

---

## **📌 2️⃣ Defining Columns & Rows**

Use `grid-template-columns` and `grid-template-rows` to create a grid layout:

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px; /* 3 columns of 200px each */
  grid-template-rows: 100px 100px; /* 2 rows of 100px each */
  gap: 10px; /* Spacing between grid items */
}
```

🔹 **Auto-sizing columns with `fr` (fractional unit):**

```css
grid-template-columns: 1fr 2fr 1fr; /* 3 columns, middle one is twice as large */
```

🔹 **Using `repeat()` for efficiency:**

```css
grid-template-columns: repeat(3, 1fr); /* Creates 3 equal columns */
grid-template-rows: repeat(2, 100px); /* Creates 2 rows of 100px each */
```

---

## **📌 3️⃣ Placing Items in the Grid**

Use `grid-column` and `grid-row` to position elements:

```css
.item1 {
  grid-column: 1 / 3; /* Spans from column 1 to 3 */
  grid-row: 1 / 3; /* Spans from row 1 to 3 */
}
```

🔹 **Shortcut: `span` for dynamic placement**

```css
.item1 {
  grid-column: span 2; /* Takes up 2 columns */
  grid-row: span 2; /* Takes up 2 rows */
}
```

---

## **📌 4️⃣ Grid Auto-Placement**

Grid automatically places items **if positions aren't defined**.  
Use `grid-auto-flow` to change default behavior:

```css
.container {
  grid-auto-flow: row; /* Default - fills row first */
  grid-auto-flow: column; /* Fills column first */
}
```

---

## **📌 5️⃣ Explicit vs. Implicit Grids**

🔹 **Explicit Grid:** You define the grid structure using `grid-template-columns/rows`.

🔹 **Implicit Grid:** Items go outside the defined grid, and CSS auto-generates rows/columns.

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px;
  grid-auto-rows: 50px; /* Automatically add rows of 50px */
}
```

---

## **📌 6️⃣ Grid Alignment & Justification**

Use **alignment properties** to position items inside the grid:

### ✅ **Aligning Items Within a Grid Cell**

```css
.container {
  align-items: center; /* Aligns items vertically */
  justify-items: center; /* Aligns items horizontally */
}
```

🔹 Values: `start`, `center`, `end`, `stretch` (default)

### ✅ **Aligning the Whole Grid Inside the Container**

```css
.container {
  align-content: center; /* Aligns grid vertically */
  justify-content: center; /* Aligns grid horizontally */
}
```

---

## **📌 7️⃣ Grid Template Areas – Named Layouts**

You can **name** grid areas to make layouts more readable:

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr auto;
}
.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.content {
  grid-area: content;
}
.footer {
  grid-area: footer;
}
```

---

## **📌 8️⃣ Responsive Grid Layouts**

Make your grid **responsive** using `minmax()` and `auto-fit / auto-fill`.

### ✅ **Using `minmax()` for Flexible Columns**

```css
.container {
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

✔ Columns will never be smaller than **200px**, but will stretch as needed.

### ✅ **Using Media Queries for Different Layouts**

```css
@media (max-width: 600px) {
  .container {
    grid-template-columns: 1fr; /* Switch to 1 column on smaller screens */
  }
}
```

---

## **📌 9️⃣ Combining CSS Grid with Flexbox**

You can **combine Flexbox & Grid** for powerful layouts!

✔ Use **Grid** for overall page layout  
✔ Use **Flexbox** for smaller components

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

.card {
  display: flex;
  align-items: center;
  justify-content: center;
}
```

---

## **📌 🔟 CSS Grid Cheat Sheet**

| Property                | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| `display: grid`         | Defines a grid container                                  |
| `grid-template-columns` | Defines columns                                           |
| `grid-template-rows`    | Defines rows                                              |
| `grid-column`           | Specifies column span                                     |
| `grid-row`              | Specifies row span                                        |
| `grid-auto-flow`        | Controls item placement (`row` / `column`)                |
| `grid-template-areas`   | Defines named grid areas                                  |
| `align-items`           | Aligns items within a row (`start, center, end, stretch`) |
| `justify-items`         | Aligns items within a column                              |
| `align-content`         | Aligns grid vertically                                    |
| `justify-content`       | Aligns grid horizontally                                  |

---

## **🚀 Conclusion**

CSS Grid is **powerful, flexible, and modern**! It makes **complex layouts easy** without relying on floats or positioning hacks.
