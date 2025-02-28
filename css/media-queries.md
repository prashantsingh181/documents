# 📌 **Media Queries in CSS – A Complete Guide**

CSS **media queries** allow you to create **responsive designs** by applying styles based on the **screen size**, **device type**, **orientation**, and even **user preferences** like dark mode.

---

## **1️⃣ Basic Syntax of Media Queries**

A **media query** consists of:

1. **`@media`** keyword
2. **Media Type** (optional, like `screen`, `print`)
3. **Media Features** (conditions like `max-width`, `orientation`)
4. **CSS Rules** (styles that apply when the conditions are met)

```css
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

✅ This applies **only when the screen width is 600px or less**.

---

## **2️⃣ Media Query Operators**

You can use **operators** to combine multiple conditions.

### **✅ AND (`and`)**

Both conditions must be **true**.

```css
@media (min-width: 600px) and (max-width: 900px) {
  body {
    background-color: lightgreen;
  }
}
```

✅ This applies **only between 600px and 900px**.

### **✅ OR (`,`)**

Any condition can be **true**.

```css
@media (max-width: 500px), (orientation: portrait) {
  body {
    background-color: orange;
  }
}
```

✅ This applies if the screen is **500px or smaller** OR in **portrait mode**.

### **✅ NOT (`not`)**

Reverses a condition.

```css
@media not (min-width: 800px) {
  body {
    background-color: red;
  }
}
```

✅ This applies **only for screens smaller than 800px**.

---

## **3️⃣ Common Media Features**

| Feature                | Description                                                         | Example                                     |
| ---------------------- | ------------------------------------------------------------------- | ------------------------------------------- |
| `max-width`            | Triggers styles when width is **equal to or less than** a value.    | `@media (max-width: 768px) {...}`           |
| `min-width`            | Triggers styles when width is **greater than or equal to** a value. | `@media (min-width: 1024px) {...}`          |
| `max-height`           | Applies styles for screens **shorter than** a value.                | `@media (max-height: 500px) {...}`          |
| `min-height`           | Applies styles for screens **taller than** a value.                 | `@media (min-height: 800px) {...}`          |
| `orientation`          | Checks if device is `portrait` or `landscape`.                      | `@media (orientation: landscape) {...}`     |
| `hover`                | Checks if the device supports hover (mouse).                        | `@media (hover: hover) {...}`               |
| `prefers-color-scheme` | Detects **light or dark mode** preference.                          | `@media (prefers-color-scheme: dark) {...}` |

---

## **4️⃣ Responsive Design with Breakpoints**

A **responsive design** adjusts styles based on screen size.

### ✅ **Mobile-First Approach**

Start with **default styles for small screens** and use `min-width` to adjust for larger screens.

```css
body {
  font-size: 16px; /* Default for mobile */
}

@media (min-width: 768px) {
  body {
    font-size: 18px;
  }
}

@media (min-width: 1024px) {
  body {
    font-size: 20px;
  }
}
```

✅ This ensures styles **scale up** rather than overriding styles for smaller screens.

### ✅ **Common Breakpoints**

| Device Type   | `min-width` (px) |
| ------------- | ---------------- |
| Mobile        | `0px` (default)  |
| Tablets       | `600px`          |
| Small Laptops | `768px`          |
| Desktops      | `1024px`         |
| Large Screens | `1440px`         |

---

## **5️⃣ Media Queries for Dark Mode**

You can detect whether the user prefers **light or dark mode**.

```css
@media (prefers-color-scheme: dark) {
  body {
    background: black;
    color: white;
  }
}
```

✅ Automatically applies **dark mode styles** when enabled.

---

## **6️⃣ Media Queries for Print**

You can apply special styles **only when printing**.

```css
@media print {
  body {
    font-size: 12pt;
    color: black;
    background: none;
  }
}
```

✅ Hides backgrounds and makes text **easier to print**.

---

## **7️⃣ Media Queries for Hover Devices (Mouse vs. Touch)**

Detect whether a device supports **hovering** (like a mouse).

```css
@media (hover: hover) {
  button:hover {
    background-color: red;
  }
}
```

✅ Ensures hover effects **only apply** to devices that support them.

---

## **🚀 Best Practices**

✔ **Use `min-width` (Mobile-First) instead of `max-width` (Desktop-First).**  
✔ **Group similar media queries** instead of writing them separately.  
✔ **Test on real devices** (Chrome DevTools, responsive simulators).  
✔ **Use `rem` and `em` instead of `px`** for better scalability.

---

### **🎯 Summary Cheat Sheet**

```css
/* Mobile First */
@media (min-width: 768px) {
  ...;
} /* Tablets */
@media (min-width: 1024px) {
  ...;
} /* Desktops */
@media (min-width: 1440px) {
  ...;
} /* Large Screens */

/* Dark Mode */
@media (prefers-color-scheme: dark) {
  ...;
}

/* Portrait Mode */
@media (orientation: portrait) {
  ...;
}

/* Print */
@media print {
  ...;
}

/* Hover Support */
@media (hover: hover) {
  ...;
}
```

---
