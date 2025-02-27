# 🎨 CSS Transformations

CSS **transforms** allow you to visually manipulate elements by **rotating, scaling, skewing, or translating** them without affecting the document flow.

---

## **📌 1️⃣ What is CSS Transform?**

The `transform` property applies **2D and 3D transformations** to an element.

### ✅ **Basic Syntax**

```css
selector {
  transform: function(value);
}
```

---

## **📌 2️⃣ Translate (Move Elements)**

Moves an element **without changing the document flow**.

### ✅ **Example: Move Right & Down**

```css
.box {
  transform: translate(50px, 100px);
}
```

| Function                 | Effect                         |
| ------------------------ | ------------------------------ |
| `translateX(50px)`       | Moves right (left if negative) |
| `translateY(100px)`      | Moves down (up if negative)    |
| `translate(50px, 100px)` | Moves **X & Y** together       |

---

## **📌 3️⃣ Scale (Resize Elements)**

Scales an element **up or down** without affecting its position.

### ✅ **Example: Grow on Hover**

```css
.box {
  transition: transform 0.5s;
}

.box:hover {
  transform: scale(1.5);
}
```

| Function          | Effect                 |
| ----------------- | ---------------------- |
| `scaleX(1.5)`     | Grows **horizontally** |
| `scaleY(0.8)`     | Shrinks **vertically** |
| `scale(1.2, 1.5)` | Grows **X & Y**        |

---

## **📌 4️⃣ Rotate (Spin Elements)**

Rotates an element **clockwise or counterclockwise**.

### ✅ **Example: Rotate 45°**

```css
.box {
  transform: rotate(45deg);
}
```

| Function         | Effect                       |
| ---------------- | ---------------------------- |
| `rotate(45deg)`  | Rotates **clockwise**        |
| `rotate(-30deg)` | Rotates **counterclockwise** |

---

## **📌 5️⃣ Skew (Tilt Elements)**

Tilts an element **horizontally or vertically**.

### ✅ **Example: Tilt Right**

```css
.box {
  transform: skew(20deg);
}
```

| Function             | Effect                 |
| -------------------- | ---------------------- |
| `skewX(30deg)`       | Tilts **horizontally** |
| `skewY(-20deg)`      | Tilts **vertically**   |
| `skew(30deg, 10deg)` | Tilts both             |

---

## **📌 6️⃣ Combine Multiple Transforms**

You can apply **multiple transformations** together.

### ✅ **Example: Move, Rotate & Scale**

```css
.box {
  transform: translateX(50px) rotate(45deg) scale(1.2);
}
```

🔹 **Order matters!** The transformations apply **sequentially**.

---

## **📌 7️⃣ Transform Origin**

Controls the **pivot point** of the transformation.

### ✅ **Example: Rotate from Top-Left**

```css
.box {
  transform-origin: top left;
  transform: rotate(45deg);
}
```

| Value      | Effect                         |
| ---------- | ------------------------------ |
| `center`   | (Default) Rotates from center  |
| `top left` | Rotates from top-left corner   |
| `50% 100%` | Rotates from **middle bottom** |

---

## **📌 8️⃣ 3D Transformations**

CSS also supports **3D transformations** with `perspective`.

### ✅ **Example: Rotate in 3D**

```css
.box {
  transform: rotateX(45deg);
}
```

| Function          | Effect                    |
| ----------------- | ------------------------- |
| `rotateX(60deg)`  | Rotates around **X-axis** |
| `rotateY(120deg)` | Rotates around **Y-axis** |
| `rotateZ(90deg)`  | Rotates around **Z-axis** |

---

## **📌 9️⃣ Perspective (Depth Effect)**

`perspective` adds a **depth effect** to 3D transformations.

### ✅ **Example: 3D Rotate with Perspective**

```css
.container {
  perspective: 500px;
}

.box {
  transform: rotateY(45deg);
}
```

🔹 **Lower `perspective` = More depth!**

---

## **📌 🔟 Best Practices for CSS Transform**

✔ **Use `transform` for animations instead of `top`, `left`** (better performance).  
✔ Combine `transform` with `transition` for smooth effects.  
✔ Use `transform-origin` to control the pivot point.  
✔ Use `perspective` for **realistic 3D effects**.

---

## **🚀 Conclusion**

CSS `transform` is a **powerful tool** for moving, scaling, rotating, and skewing elements!
