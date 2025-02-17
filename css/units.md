# CSS Units 📏

CSS uses **units** to define lengths, sizes, spacing, and positioning of elements. These units are divided into **absolute** and **relative** types.  

---

## **1. Absolute Units 📌**  
Absolute units are **fixed** and do not change based on screen size or parent elements.  

| Unit  | Description | Example |
|--------|------------|---------|
| `px`  | Pixels (most common) | `width: 100px;` |
| `cm`  | Centimeters | `width: 10cm;` |
| `mm`  | Millimeters | `width: 50mm;` |
| `in`  | Inches (`1in = 96px`) | `width: 2in;` |
| `pt`  | Points (`1pt = 1/72in`) | `font-size: 12pt;` |
| `pc`  | Picas (`1pc = 12pt`) | `width: 5pc;` |

✅ **Use Case:** `px` is the most commonly used for screen design since it aligns well with display resolutions.  

---

## **2. Relative Units 🔄**  
Relative units adjust based on the parent element, viewport, or other factors.  

### **(a) Relative to Font Size**
| Unit | Description | Example |
|------|------------|---------|
| `em` | Relative to the **parent element’s font size** | `font-size: 2em;` (2× parent’s size) |
| `rem` | Relative to the **root (`<html>`) font size** | `font-size: 1.5rem;` (1.5× root size) |

🔹 **Difference Between `em` and `rem`**  
```css
html { font-size: 16px; }
.parent { font-size: 20px; }
.child { font-size: 1.5em; } /* 30px (1.5 × 20px) */
.child-rem { font-size: 1.5rem; } /* 24px (1.5 × 16px) */
```
✅ **Use `rem` for consistent scaling across the page.**  

---

### **(b) Relative to Viewport (Responsive Design)**
| Unit  | Description | Example |
|--------|------------|---------|
| `vw`  | **Viewport Width** (`1vw = 1% of viewport width`) | `width: 50vw;` (50% of screen width) |
| `vh`  | **Viewport Height** (`1vh = 1% of viewport height`) | `height: 100vh;` (Full screen height) |
| `vmin` | The **smaller** of `vw` or `vh` | `width: 50vmin;` |
| `vmax` | The **larger** of `vw` or `vh` | `width: 50vmax;` |

✅ **Use Case:**  
- `100vh` ensures a section takes up the **full screen height**.  
- `50vw` makes an element **half the width of the screen**.  

---

### **(c) Relative to Content**
| Unit | Description | Example |
|------|------------|---------|
| `%`  | Relative to the **parent element** | `width: 50%;` (50% of parent) |
| `ch` | Width of the `0` character in the current font | `width: 20ch;` (Fits ~20 characters) |
| `ex` | Height of the letter `x` in the current font | `height: 2ex;` |
| `lh` | Line height of the element | `line-height: 1.5lh;` |

✅ **Use Case:**  
- `%` is great for **flexible layouts** (e.g., `width: 80%;`).  
- `ch` is useful for **setting readable text widths** (e.g., `max-width: 60ch;`).  

---

## **3. CSS Unit Best Practices 🏆**
✔ **Use `px` for precise control over spacing and borders.**  
✔ **Use `rem` for font sizes** (ensures consistent scaling).  
✔ **Use `vw`/`vh` for full-screen layouts** (e.g., `height: 100vh;`).  
✔ **Use `%` for flexible layouts** inside containers.  
✔ **Avoid `cm`, `mm`, `in`, `pt`, `pc`** unless working on print media.  
✔ **Avoid `100vw`** on body width as it doesn't account for vertical scrollbar and will result in an unwanted horizontal scrollbar when content outgrows the container.  

