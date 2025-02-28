# **CSS (Cascading Style Sheet)**

CSS (Cascading Style Sheets) is a language used to **style** web pages. It controls the **layout, colors, fonts, and spacing** of HTML elements to make websites look visually appealing.

---

There are three main ways to write CSS:

### **1. Inline CSS**

CSS is written directly within an HTML element using the `style` attribute.

#### Example:

```html
<p style="color: blue; font-size: 20px;">This is inline CSS</p>
```

✅ **Pros**:

- Quick and useful for small changes.

❌ **Cons**:

- Hard to maintain and scale.
- Increases HTML file size.
- Cannot use CSS features like media queries or pseudo-selectors.

---

### **2. Internal (Embedded) CSS**

CSS is written inside a `<style>` tag within the `<head>` section of an HTML file.

#### Example:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      p {
        color: red;
        font-size: 18px;
      }
    </style>
  </head>
  <body>
    <p>This is internal CSS</p>
  </body>
</html>
```

✅ **Pros**:

- Useful for single-page styling.
- Better structure than inline CSS.

❌ **Cons**:

- Not reusable across multiple pages.
- Can make the HTML file large if styles increase.

---

### **3. External CSS (Recommended for Larger Projects)**

CSS is written in a separate `.css` file and linked in the HTML file.

#### Example:

**styles.css**

```css
p {
  color: green;
  font-size: 22px;
}
```

**index.html**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <p>This is external CSS</p>
  </body>
</html>
```

✅ **Pros**:

- Best for maintainability and reusability.
- Keeps HTML and CSS separate.
- Allows better performance with caching.

❌ **Cons**:

- Requires an extra HTTP request to fetch the CSS file.
