# **CSS `position` Property**

The `position` property in CSS controls how an element is **placed** in the document. It determines whether an element follows the normal document flow or is positioned independently.

---

## **1️⃣ `position` Values in CSS**

| **Value**  | **Description**                                                     | **Offsets (top, right, bottom, left)?** | **Affects Layout?**       |
| ---------- | ------------------------------------------------------------------- | --------------------------------------- | ------------------------- |
| `static`   | Default value. Follows normal document flow.                        | ❌ No                                   | ✅ Yes                    |
| `relative` | Positioned **relative to its normal position**.                     | ✅ Yes                                  | ✅ Yes                    |
| `absolute` | Positioned **relative to the nearest positioned ancestor**.         | ✅ Yes                                  | ❌ No (removed from flow) |
| `fixed`    | Positioned **relative to the viewport** (stays in place on scroll). | ✅ Yes                                  | ❌ No                     |
| `sticky`   | **Switches between `relative` & `fixed`** based on scroll.          | ✅ Yes                                  | ✅ Yes                    |

---

## **2️⃣ `static` (Default)**

This is the default position. The element follows the normal document flow.

```css
.box {
  position: static; /* Default, no effect */
}
```

✅ **Example**

```html
<div class="box">I follow normal flow.</div>
```

📌 **No special positioning applied!**

---

## **3️⃣ `relative` – Shift From Normal Position**

Elements remain in the document flow but can be **shifted** using `top`, `left`, `right`, or `bottom`.

```css
.box {
  position: relative;
  top: 20px; /* Moves 20px down */
  left: 10px; /* Moves 10px right */
}
```

✅ **Example**

```html
<div class="box">I moved relative to my normal position.</div>
```

📌 **Space is still reserved for the element in the layout.**

---

## **4️⃣ `absolute` – Removed From Normal Flow**

An `absolute` positioned element is **completely removed** from the normal flow. It is positioned **relative to the nearest positioned ancestor** (not `static`).

```css
.parent {
  position: relative; /* Acts as the reference */
}

.child {
  position: absolute;
  top: 0;
  left: 0;
}
```

✅ **Example**

```html
<div class="parent">
  <div class="child">I'm positioned absolutely inside the parent.</div>
</div>
```

📌 **If no positioned ancestor exists, it positions relative to `<html>`.**

---

## **5️⃣ `fixed` – Stays in Place on Scroll**

An element with `fixed` position stays **fixed to the viewport**, meaning it **never moves when scrolling**.

```css
.fixed-box {
  position: fixed;
  top: 10px;
  right: 10px;
}
```

✅ **Example**

```html
<div class="fixed-box">I stay in place even when you scroll.</div>
```

📌 **Useful for headers, floating buttons, and sticky navigation.**

---

## **6️⃣ `sticky` – Behaves Like `relative` & `fixed`**

An element with `sticky` **acts like `relative`** until the user scrolls to a certain point—then it becomes **`fixed`**.

```css
.sticky-box {
  position: sticky;
  top: 0;
  background: yellow;
}
```

✅ **Example**

```html
<div class="sticky-box">I stick to the top when you scroll.</div>
```

📌 **Useful for sticky headers or sidebar navigation.**

---

## **7️⃣ `z-index` – Layering Elements**

Use `z-index` to control the **stacking order** of elements.

```css
.box1 {
  position: absolute;
  z-index: 10;
}

.box2 {
  position: absolute;
  z-index: 5; /* Appears behind box1 */
}
```

📌 **Higher `z-index` values appear in front.**

---

## **8️⃣ Summary – When to Use What?**

| Position   | Use Case                                                         |
| ---------- | ---------------------------------------------------------------- |
| `static`   | Default behavior, no positioning needed.                         |
| `relative` | Small adjustments **without affecting other elements**.          |
| `absolute` | Positioning **inside another element** without affecting layout. |
| `fixed`    | **Always visible** (sticky headers, floating buttons).           |
| `sticky`   | **Sticks on scroll** (navigation bars, sidebars).                |

---

## **🔹 Quick Takeaways**

✔ `relative` moves an element **without affecting others**.  
✔ `absolute` positions **relative to the nearest positioned parent**.  
✔ `fixed` stays **locked to the viewport**.  
✔ `sticky` **switches** between `relative` and `fixed`.
