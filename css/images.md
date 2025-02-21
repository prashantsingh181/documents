# **📸 CSS Images – A Complete Guide**

Images in CSS can be used in multiple ways, including setting **backgrounds**, controlling **size**, applying **filters**, and more. Let’s explore everything in detail.

---

## **1️⃣ Adding Images in CSS**

There are two main ways to add images using CSS:

### ✅ **1. Background Images (CSS)**

Uses `background-image` to apply an image to an element’s background.

```css
.box {
  width: 300px;
  height: 200px;
  background-image: url("image.jpg");
  background-size: cover;
}
```

### ✅ **2. `<img>` Tag (HTML)**

Using the `<img>` tag inside HTML.

```html
<img src="image.jpg" alt="Sample Image" class="image" />
```

---

## **2️⃣ Removing the Default Space Below Images**

By default, images inside inline elements (like `<img>`) have a small **gap** below them. This happens because images are treated as **inline elements** and align with the **baseline** of surrounding text.

### 🔥 **Fix: Use `display: block`**

```css
img {
  display: block;
}
```

### 🔥 **Alternative Fix: Set `vertical-align: middle|top|bottom;`**

```css
img {
  vertical-align: middle;
}
```

---

## **3️⃣ `background-image` – Applying Backgrounds**

The `background-image` property sets an image as the background of an element.

```css
.box {
  background-image: url("image.jpg");
}
```

🔹 **Multiple Backgrounds** (comma-separated list)

```css
.box {
  background-image: url("layer1.png"), url("layer2.png");
}
```

---

## **4️⃣ `background-size` – Controlling Image Size**

The `background-size` property defines how an image should be scaled.

```css
.box {
  background-size: cover;
}
```

| Value         | Description                                              |
| ------------- | -------------------------------------------------------- |
| `auto`        | (Default) Keeps original size.                           |
| `cover`       | Fills the entire container **without stretching**.       |
| `contain`     | Ensures the whole image is visible **without cropping**. |
| `100px 200px` | Custom width and height.                                 |

✅ **Example – Full-Page Background**

```css
body {
  background-image: url("bg.jpg");
  background-size: cover;
  background-repeat: no-repeat;
}
```

---

## **5️⃣ `background-position` – Positioning the Image**

Controls where the image is placed inside the element.

```css
.box {
  background-position: center center;
}
```

| Value           | Description                 |
| --------------- | --------------------------- |
| `left top`      | Aligns to **top-left**.     |
| `center center` | Centers the image.          |
| `right bottom`  | Aligns to **bottom-right**. |
| `50% 50%`       | Custom **X Y** positioning. |

---

## **6️⃣ `background-repeat` – Repeating the Image**

By default, background images **repeat**. You can control this using `background-repeat`.

```css
.box {
  background-repeat: no-repeat;
}
```

| Value       | Description                                       |
| ----------- | ------------------------------------------------- |
| `repeat`    | (Default) Repeats both horizontally & vertically. |
| `repeat-x`  | Repeats **horizontally**.                         |
| `repeat-y`  | Repeats **vertically**.                           |
| `no-repeat` | No repetition.                                    |

---

## **7️⃣ `background-attachment` – Fixed or Scroll**

Controls whether the background moves with scrolling.

```css
.box {
  background-attachment: fixed;
}
```

| Value    | Description                   |
| -------- | ----------------------------- |
| `scroll` | (Default) Moves with content. |
| `fixed`  | Stays fixed while scrolling.  |
| `local`  | Scrolls within the element.   |

✅ **Example – Parallax Effect**

```css
.box {
  background-attachment: fixed;
  background-size: cover;
}
```

---

## **8️⃣ `background-clip` – Controlling Background Area**

The `background-clip` property controls how far the background extends inside an element.

```css
.box {
  background-clip: border-box;
}
```

| Value         | Description                                            |
| ------------- | ------------------------------------------------------ |
| `border-box`  | (Default) Background extends **to the border**.        |
| `padding-box` | Background stops **at the padding**.                   |
| `content-box` | Background only covers the **content area**.           |
| `text`        | Background applies only to **text** (with `-webkit-`). |

✅ **Example – Text Background**

```css
.text {
  background-image: url("gradient.jpg");
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
}
```

---

## **9️⃣ `object-fit` – Resizing `<img>` Elements**

When using `<img>`, `object-fit` controls how the image fits inside its container.

```css
img {
  width: 100%;
  height: 300px;
  object-fit: cover;
}
```

| Value     | Description                         |
| --------- | ----------------------------------- |
| `fill`    | (Default) Stretches image.          |
| `cover`   | Fills container without distortion. |
| `contain` | Fits image within container.        |
| `none`    | Keeps original size.                |

✅ **Example – Responsive Images**

```css
img {
  width: 100%;
  height: auto;
  object-fit: contain;
}
```

---

## **🔟 `filter` – Applying Effects to Images**

You can apply **CSS filters** to images for cool effects.

```css
img {
  filter: grayscale(100%);
}
```

| Filter             | Example                          |
| ------------------ | -------------------------------- |
| `grayscale(100%)`  | Converts image to black & white. |
| `blur(5px)`        | Blurs the image.                 |
| `brightness(150%)` | Increases brightness.            |
| `contrast(200%)`   | Increases contrast.              |
| `invert(100%)`     | Inverts colors.                  |
| `sepia(100%)`      | Applies a sepia effect.          |

✅ **Example – Hover Effect**

```css
img:hover {
  filter: brightness(50%);
}
```

---

## **🎯 Summary: CSS Image Properties Cheat Sheet**

```css
.image {
  background-image: url("image.jpg");
  background-size: cover; /* cover | contain */
  background-position: center; /* left | right */
  background-repeat: no-repeat; /* repeat | no-repeat */
  background-clip: padding-box; /* border-box | content-box */
}

img {
  display: block; /* Removes bottom gap */
  object-fit: cover; /* cover | contain | fill */
  object-position: center; /* left | right | top */
  filter: grayscale(100%); /* blur | brightness | contrast */
}
```

---

## **🚀 Best Practices**

✔ **Use `display: block;` on `<img>`** to avoid unwanted gaps.  
✔ Use **background images** for decorative elements.  
✔ Use `<img>` for **content images** (SEO & accessibility).  
✔ Optimize images using **WebP** or **AVIF** for better performance.  
✔ Use `object-fit` for **responsive** images.  
✔ Combine images in **CSS sprites** to reduce requests.

---
