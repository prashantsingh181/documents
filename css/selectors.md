# CSS Selectors

CSS selectors are patterns used to select and style HTML elements. There are different types of selectors based on how elements are targeted.

---

## **1. Basic Selectors**

### **a) Universal Selector (`*`)**

Selects all elements on the page.

#### Example:

```css
* {
  margin: 0;
  padding: 0;
}
```

### **b) Element (Type) Selector**

Selects all instances of a specific HTML tag.

#### Example:

```css
p {
  color: blue;
}
```

This applies to all `<p>` elements.

### **c) Class Selector (`.`)**

Targets elements with a specific class.

#### Example:

```css
.text {
  font-size: 18px;
}
```

```html
<p class="text">This is a paragraph</p>
```

### **d) ID Selector (`#`)**

Targets an element with a specific ID (must be unique).

#### Example:

```css
#main-heading {
  font-weight: bold;
}
```

```html
<h1 id="main-heading">Hello</h1>
```

---

## **2. Grouping & Combinator Selectors**

### **a) Grouping Selector (`,`)**

Applies the same styles to multiple elements.

#### Example:

```css
h1,
h2,
h3 {
  color: darkblue;
}
```

### **b) Descendant Selector (Space )**

Selects elements inside another element.

#### Example:

```css
div p {
  color: red;
}
```

This styles `<p>` inside a `<div>`.

### **c) Child Selector (`>`)**

Selects direct children only (not deeper nested elements).

#### Example:

```css
div > p {
  color: green;
}
```

### **d) Adjacent Sibling Selector (`+`)**

Selects an element immediately after another.

#### Example:

```css
h1 + p {
  color: orange;
}
```

This applies to the `<p>` that comes **right after** `<h1>`.

### **e) General Sibling Selector (`~`)**

Selects all matching siblings after a given element.

#### Example:

```css
h1 ~ p {
  color: purple;
}
```

---

## **3. Attribute Selectors**

### **a) Exact Attribute Match (`[attr="value"]`)**

```css
input[type="text"] {
  border: 1px solid black;
}
```

Targets `<input type="text">`.

### **b) Attribute Presence (`[attr]`)**

```css
input[required] {
  border: 2px solid red;
}
```

Targets any `<input>` with the `required` attribute.

### **c) Partial Attribute Match**

- **Starts with (`^=`)** → `a[href^="https"]` (links that start with `https`).
- **Ends with (`$=`)** → `img[src$=".png"]` (images that end in `.png`).
- **Contains (`*=`)** → `div[class*="box"]` (elements whose class contains "box").

---

## **4. Pseudo-Classes (`:`)**

### **a) Hover, Focus, Active**

```css
button:hover {
  background-color: yellow;
}
button:focus {
  outline: 2px solid blue;
}
button:active {
  transform: scale(0.95);
}
```

### **b) First & Last Child**

```css
ul li:first-child {
  font-weight: bold;
}
ul li:last-child {
  color: red;
}
```

### **c) nth-child & nth-of-type**

```css
tr:nth-child(even) {
  background-color: lightgray;
}
```

Applies styles to every even row.

---

## **5. Pseudo-Elements (`::`)**

### **a) Before & After**

```css
p::before {
  content: "→ ";
  color: blue;
}
p::after {
  content: " ←";
  color: red;
}
```

Adds symbols before and after paragraphs.

### **b) First Letter & First Line**

```css
p::first-letter {
  font-size: 2rem;
}
p::first-line {
  color: gray;
}
```

---
