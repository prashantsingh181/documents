# 🎬 CSS Animations

CSS animations allow you to **bring elements to life** without JavaScript! You can create smooth transitions, fades, movements, and more with just a few lines of code.

---

## **📌 1️⃣ What is CSS Animation?**

CSS animations use `@keyframes` to define **how an element should animate over time**, and then apply that animation using the `animation` property.

### ✅ **Basic Syntax**

```css
@keyframes animationName {
  from {
    property: value;
  }
  to {
    property: value;
  }
}

.element {
  animation: animationName duration timing-function delay iteration-count
    direction fill-mode;
}
```

### **Example: Fading an Element**

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.box {
  animation: fadeIn 2s ease-in-out;
}
```

🔹 The element **fades in** over **2 seconds**.

---

## **📌 2️⃣ The `@keyframes` Rule**

`@keyframes` defines the **steps** of an animation. Instead of just `from` and `to`, we can use percentages to define multiple steps.

### ✅ **Example: Moving a Box**

```css
@keyframes moveBox {
  0% {
    left: 0px;
  }
  50% {
    left: 100px;
    background: red;
  }
  100% {
    left: 200px;
    background: blue;
  }
}

.box {
  position: relative;
  animation: moveBox 3s ease-in-out infinite;
}
```

🔹 The box **moves in steps**:

- **0%** → Start at `left: 0px`
- **50%** → Moves halfway and turns **red**
- **100%** → Moves fully and turns **blue**

---

## **📌 3️⃣ Animation Properties**

| Property                    | Description                                    | Example                                   |
| --------------------------- | ---------------------------------------------- | ----------------------------------------- |
| `animation-name`            | Specifies the animation name                   | `animation-name: slideIn;`                |
| `animation-duration`        | Sets how long the animation runs               | `animation-duration: 2s;`                 |
| `animation-timing-function` | Controls speed changes                         | `animation-timing-function: ease-in-out;` |
| `animation-delay`           | Delays the start of animation                  | `animation-delay: 1s;`                    |
| `animation-iteration-count` | How many times the animation repeats           | `animation-iteration-count: infinite;`    |
| `animation-direction`       | Controls animation direction                   | `animation-direction: alternate;`         |
| `animation-fill-mode`       | Defines how the animation applies before/after | `animation-fill-mode: forwards;`          |

---

## **📌 4️⃣ Animation Timing Functions**

These control **how the speed of the animation changes** over time.

| Value                        | Effect                                  |
| ---------------------------- | --------------------------------------- |
| `linear`                     | Moves at a **constant speed**           |
| `ease`                       | Starts slow, speeds up, then slows down |
| `ease-in`                    | Starts slow, then speeds up             |
| `ease-out`                   | Starts fast, then slows down            |
| `ease-in-out`                | Starts and ends slow                    |
| `cubic-bezier(x, y, x2, y2)` | Custom speed curve                      |

### ✅ **Example: Different Timing Functions**

```css
@keyframes bounce {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-50px);
  }
  100% {
    transform: translateY(0);
  }
}

.box {
  animation: bounce 1s ease-in-out infinite;
}
```

🔹 The box **bounces up and down** smoothly.

---

## **📌 5️⃣ Animation Iteration & Direction**

| Property                    | Value       | Effect                         |
| --------------------------- | ----------- | ------------------------------ |
| `animation-iteration-count` | `infinite`  | Repeats forever                |
| `animation-direction`       | `alternate` | Reverses direction every cycle |
| `animation-direction`       | `reverse`   | Starts **in reverse**          |

### ✅ **Example: Reverse & Alternate**

```css
@keyframes colorChange {
  0% {
    background-color: red;
  }
  100% {
    background-color: blue;
  }
}

.box {
  animation: colorChange 3s linear infinite alternate;
}
```

🔹 The box **changes color**, then reverses **back**.

---

## **📌 6️⃣ Using `animation-fill-mode`**

`animation-fill-mode` controls **how styles apply before & after animation**.

| Value       | Effect                                              |
| ----------- | --------------------------------------------------- |
| `none`      | No effect after animation ends                      |
| `forwards`  | Keeps the final state after animation ends          |
| `backwards` | Applies the **start state** before animation begins |
| `both`      | Applies both **forwards & backwards**               |

### ✅ **Example: Keeping the Final State**

```css
@keyframes grow {
  from {
    transform: scale(1);
  }
  to {
    transform: scale(2);
  }
}

.box {
  animation: grow 2s ease forwards;
}
```

🔹 The box **grows** and **stays enlarged** after animation.

---

## **📌 7️⃣ Combining Multiple Animations**

You can apply **multiple animations** by separating them with commas.

### ✅ **Example: Moving + Rotating**

```css
@keyframes move {
  0% {
    left: 0px;
  }
  100% {
    left: 200px;
  }
}

@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.box {
  position: relative;
  animation: move 3s linear infinite, rotate 2s linear infinite;
}
```

🔹 The box **moves & rotates at the same time**.

---

## **📌 8️⃣ Animation vs. Transition**

| Feature             | Animation                     | Transition           |
| ------------------- | ----------------------------- | -------------------- |
| **Purpose**         | Complex multi-step animations | Simple state changes |
| **Keyframes?**      | ✅ Yes (`@keyframes`)         | ❌ No                |
| **Repeating?**      | ✅ Yes (`infinite`)           | ❌ No                |
| **Multiple Steps?** | ✅ Yes (`0%, 50%, 100%`)      | ❌ No                |

### ✅ **Example: Transition (Single Step)**

```css
button {
  transition: background-color 0.5s ease;
}

button:hover {
  background-color: red;
}
```

🔹 **Transitions only happen on interaction (hover, click, etc.)**

---

## **🚀 Conclusion**

✔️ **CSS animations create engaging effects without JavaScript**  
✔️ Use `@keyframes` to define **step-by-step changes**  
✔️ Control animation **speed, direction, delay, and repetition**  
✔️ Combine multiple animations for **dynamic effects**  
✔️ Use `animation-fill-mode` to **control styles before/after animation**

---
