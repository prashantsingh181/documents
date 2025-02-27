# 🎭 CSS Pseudo-Classes & Pseudo-Elements

CSS **pseudo-classes** and **pseudo-elements** help us **style elements dynamically** without adding extra HTML or JavaScript. Let's dive deep into their usage and examples.

---

## **📌 1️⃣ What are Pseudo-Classes?**

A **pseudo-class** selects elements **based on their state, position, or interaction**. It **does not create new elements** but **styles existing ones dynamically**.

### ✅ **Syntax:**

```css
selector:pseudo-class {
  property: value;
}
```

Example: Change button color **on hover**

```css
button:hover {
  background-color: red;
}
```

---

## **📌 2️⃣ What are Pseudo-Elements?**

A **pseudo-element** creates a **virtual element** inside an existing one, allowing you to style specific parts of content.

### ✅ **Syntax:**

```css
selector::pseudo-element {
  property: value;
}
```

Example: Add content **before** a heading

```css
h1::before {
  content: "🔥 ";
}
```

---

# **🎯 Complete List of Pseudo-Classes & Pseudo-Elements**

## **🎨 Pseudo-Classes – Styling Elements Dynamically**

### **🟢 User Action & Interaction Pseudo-Classes**

| Pseudo-Class | Description                                    | Example                                |
| ------------ | ---------------------------------------------- | -------------------------------------- |
| `:hover`     | When user hovers over an element               | `button:hover { background: red; }`    |
| `:active`    | When an element is clicked                     | `a:active { color: blue; }`            |
| `:focus`     | When an element is focused (like input fields) | `input:focus { border-color: green; }` |

---

### **🔢 Structural Pseudo-Classes**

| Pseudo-Class         | Description                                              | Example                                  |
| -------------------- | -------------------------------------------------------- | ---------------------------------------- |
| `:first-child`       | Selects the first child of a parent                      | `p:first-child { font-weight: bold; }`   |
| `:last-child`        | Selects the last child of a parent                       | `li:last-child { color: red; }`          |
| `:nth-child(n)`      | Selects the nth child                                    | `li:nth-child(2) { color: blue; }`       |
| `:nth-last-child(n)` | Selects the nth child counting from the end              | `li:nth-last-child(1) { color: green; }` |
| `:only-child`        | Selects elements that are the only child of their parent | `p:only-child { font-style: italic; }`   |

---

### **📌 Form Pseudo-Classes**

| Pseudo-Class | Description                             | Example                                      |
| ------------ | --------------------------------------- | -------------------------------------------- |
| `:checked`   | Styles checked checkboxes/radio buttons | `input:checked { border: 2px solid red; }`   |
| `:disabled`  | Styles disabled form elements           | `input:disabled { background: gray; }`       |
| `:enabled`   | Styles enabled form elements            | `input:enabled { border: 2px solid green; }` |
| `:required`  | Styles required form fields             | `input:required { border: 2px solid blue; }` |
| `:optional`  | Styles optional fields                  | `input:optional { background: yellow; }`     |
| `:valid`     | Styles valid form inputs                | `input:valid { border: 2px solid green; }`   |
| `:invalid`   | Styles invalid form inputs              | `input:invalid { border: 2px solid red; }`   |

---

### **📍 State-Based Pseudo-Classes**

| Pseudo-Class     | Description                                      | Example                            |
| ---------------- | ------------------------------------------------ | ---------------------------------- |
| `:empty`         | Selects elements with no content                 | `div:empty { display: none; }`     |
| `:not(selector)` | Selects everything **except** the given selector | `p:not(.special) { color: gray; }` |

---

### **💡 Advanced & Functional Pseudo-Classes**

| Pseudo-Class      | Description                           | Example                             |
| ----------------- | ------------------------------------- | ----------------------------------- |
| `:first-of-type`  | Selects the first element of its type | `p:first-of-type { color: blue; }`  |
| `:last-of-type`   | Selects the last element of its type  | `h2:last-of-type { color: green; }` |
| `:nth-of-type(n)` | Selects the nth element of its type   | `h2:nth-of-type(2) { color: red; }` |

---

## **🎭 Pseudo-Elements – Styling Parts of Elements**

| Pseudo-Element   | Description                               | Example                                       |
| ---------------- | ----------------------------------------- | --------------------------------------------- |
| `::before`       | Inserts content **before** an element     | `h1::before { content: "🔥 "; }`              |
| `::after`        | Inserts content **after** an element      | `h1::after { content: " 🚀"; }`               |
| `::first-letter` | Styles the **first letter** of an element | `p::first-letter { font-size: 2em; }`         |
| `::first-line`   | Styles the **first line** of text         | `p::first-line { font-weight: bold; }`        |
| `::selection`    | Styles text **when selected**             | `p::selection { background: yellow; }`        |
| `::placeholder`  | Styles placeholder text in input fields   | `input::placeholder { color: gray; }`         |
| `::marker`       | Styles bullets in lists (`<ul>`/`<ol>`)   | `li::marker { color: red; font-size: 20px; }` |

---

## **🔥 Examples of Pseudo-Classes & Pseudo-Elements in Action**

### ✅ **Hover Effect with `::before`**

```css
button {
  position: relative;
  padding: 10px 20px;
  font-size: 16px;
}

button::before {
  content: "🔥 ";
  position: absolute;
  left: -20px;
  opacity: 0;
  transition: opacity 0.3s;
}

button:hover::before {
  opacity: 1;
}
```

🔹 **Before hovering:** `🔥` is hidden  
🔹 **After hovering:** `🔥` appears

---

### ✅ **Styling First Letter of Paragraph**

```css
p::first-letter {
  font-size: 2em;
  font-weight: bold;
  color: red;
}
```

🔹 Makes the **first letter of every paragraph bigger & colored**

---

### ✅ **Making Selected Text Yellow**

```css
p::selection {
  background-color: yellow;
  color: black;
}
```

🔹 Highlights text **when the user selects it**

---

### ✅ **Styling Form Placeholders**

```css
input::placeholder {
  color: gray;
  font-style: italic;
}
```

🔹 Styles **input placeholders**

---

## **🚀 Quick Summary: When to Use What?**

| Feature                              | Pseudo-Class                     | Pseudo-Element                      |
| ------------------------------------ | -------------------------------- | ----------------------------------- |
| Style elements based on user actions | ✅ `:hover`, `:focus`            | ❌                                  |
| Style specific parts of an element   | ❌                               | ✅ `::before`, `::after`            |
| Style first or last child            | ✅ `:first-child`, `:last-child` | ❌                                  |
| Style first letter/line              | ❌                               | ✅ `::first-letter`, `::first-line` |
| Style selection (highlighted text)   | ❌                               | ✅ `::selection`                    |
| Hide empty elements                  | ✅ `:empty`                      | ❌                                  |

---

## **💡 Conclusion**

- **Pseudo-classes** target elements **based on state, structure, or interaction**.
- **Pseudo-elements** target **specific parts** of an element.
- They **reduce the need for JavaScript** and **enhance UI design efficiently**.

💬 **Which pseudo-class or pseudo-element do you use the most?** 🚀
