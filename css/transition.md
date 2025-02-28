# 🎨 **CSS Transitions**

CSS **transitions** allow you to animate changes in **CSS properties** smoothly over time instead of having them change instantly.

---

## **📌 1️⃣ What is a CSS Transition?**

A transition **animates the change** of a property when an element enters a new state (e.g., hover, focus, active).

### ✅ **Basic Syntax**

```css
selector {
  transition: property duration timing-function delay;
}
```

| Property          | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| `property`        | The CSS property to animate (`all` for everything)           |
| `duration`        | How long the transition lasts (`0.5s`, `2s`)                 |
| `timing-function` | Controls the speed curve (`ease`, `linear`, `ease-in`, etc.) |
| `delay`           | When the transition should start (`0s`, `1s`)                |

---

## **📌 2️⃣ Example: Smooth Hover Effect**

Let's create a **button that changes color smoothly** when hovered:

```css
button {
  background-color: blue;
  color: white;
  padding: 10px 20px;
  border: none;
  transition: background-color 0.5s ease-in-out;
}

button:hover {
  background-color: red;
}
```

🔹 **Without `transition`**, the color would change **instantly**.  
🔹 **With `transition`**, the color changes **smoothly over 0.5s**.

---

## **📌 3️⃣ Transition Timing Functions**

The `timing-function` controls **how the speed changes** over time.

| Value                        | Effect                                            |
| ---------------------------- | ------------------------------------------------- |
| `linear`                     | Moves at a **constant speed**                     |
| `ease`                       | (Default) Starts slow, speeds up, then slows down |
| `ease-in`                    | Starts slow, then speeds up                       |
| `ease-out`                   | Starts fast, then slows down                      |
| `ease-in-out`                | Starts and ends slow                              |
| `cubic-bezier(x, y, x2, y2)` | Custom speed curve                                |

### ✅ **Example: Different Speed Curves**

```css
.box {
  width: 100px;
  height: 100px;
  background: orange;
  transition: transform 1s ease-in-out;
}

.box:hover {
  transform: translateX(200px);
}
```

🔹 The box **moves smoothly to the right** over **1 second**.

---

## **📌 4️⃣ Transitioning Multiple Properties**

You can transition **multiple properties** by separating them with commas.

### ✅ **Example: Smooth Size & Color Change**

```css
.box {
  width: 100px;
  height: 100px;
  background: green;
  transition: width 1s, height 1s, background 0.5s ease-in;
}

.box:hover {
  width: 200px;
  height: 200px;
  background: yellow;
}
```

🔹 The box **grows and changes color** smoothly.

---

## **📌 5️⃣ Using `all` to Transition Everything**

Instead of specifying multiple properties, you can use `all`.

### ✅ **Example: Transition All Properties**

```css
.box {
  transition: all 0.5s ease-in-out;
}
```

🔹 **⚠ Be careful!** Using `all` may transition **unwanted properties**, causing unexpected effects.

---

## **📌 6️⃣ Adding Delay with `transition-delay`**

The `transition-delay` property **delays the start** of the transition.

### ✅ **Example: Delayed Hover Effect**

```css
.box {
  transition: background-color 1s ease-in-out 0.5s;
}
```

🔹 The transition **waits 0.5s before starting**.

---

## **📌 7️⃣ Transitioning Transformations**

CSS `transform` properties like **scale, rotate, and translate** work great with transitions!

### ✅ **Example: Scaling on Hover**

```css
.box {
  transition: transform 0.5s ease-in-out;
}

.box:hover {
  transform: scale(1.2);
}
```

🔹 The element **grows** when hovered.

### ✅ **Example: Rotating on Hover**

```css
.box {
  transition: transform 0.5s;
}

.box:hover {
  transform: rotate(180deg);
}
```

🔹 The element **spins** when hovered.

---

## **📌 8️⃣ Transitioning Opacity & Visibility**

### ✅ **Example: Smooth Fade-In & Fade-Out**

```css
.box {
  opacity: 1;
  transition: opacity 1s ease-in-out;
}

.box:hover {
  opacity: 0;
}
```

🔹 The element **fades out smoothly**.

### ✅ **Example: Fading & Hiding Element**

```css
.box {
  opacity: 1;
  visibility: visible;
  transition: opacity 0.5s ease, visibility 0.5s;
}

.box.hidden {
  opacity: 0;
  visibility: hidden;
}
```

🔹 This **hides the element** while keeping a smooth transition.

---

## **📌 9️⃣ Transition vs. Animation**

| Feature             | Transition                    | Animation                   |
| ------------------- | ----------------------------- | --------------------------- |
| **Purpose**         | Simple effects (hover, focus) | Complex, multi-step effects |
| **Keyframes?**      | ❌ No                         | ✅ Yes (`@keyframes`)       |
| **Repeating?**      | ❌ No                         | ✅ Yes (`infinite`)         |
| **Multiple Steps?** | ❌ No                         | ✅ Yes (`0%, 50%, 100%`)    |

### ✅ **Example: Transition (Single Step)**

```css
button {
  transition: background-color 0.5s ease;
}

button:hover {
  background-color: red;
}
```

### ✅ **Example: Animation (Multi-Step)**

```css
@keyframes colorChange {
  0% {
    background-color: red;
  }
  50% {
    background-color: yellow;
  }
  100% {
    background-color: blue;
  }
}

button {
  animation: colorChange 3s infinite;
}
```

🔹 **Use `animation` for complex effects** and `transition` for **simple changes**.

---

## **🚀 Conclusion**

✔ **CSS transitions create smooth effects with minimal code**  
✔ Use `transition: property duration timing-function delay;`  
✔ Combine `transform`, `opacity`, and `background` for stunning effects  
✔ Use `ease-in-out` for a **natural feel**  
✔ Use `transition-delay` for **staggered animations**

---
