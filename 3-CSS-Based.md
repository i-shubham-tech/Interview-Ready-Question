# CSS Interview Questions & Answers 

## Table of Contents

1. [What is CSS?](#1-what-is-css)
2. [What is Flexbox?](#2-what-is-flexbox)
3. [When do you use Flexbox?](#3-when-do-you-use-flexbox)
4. [What is CSS Grid?](#4-what-is-css-grid)
5. [Difference between Flexbox and Grid?](#5-difference-between-flexbox-and-grid)
6. [What is Responsive Design?](#6-what-is-responsive-design)
7. [What are Media Queries?](#7-what-are-media-queries)
8. [What are CSS Positions?](#8-what-are-css-positions)
9. [Difference between Absolute and Relative Position?](#9-difference-between-absolute-and-relative-position)
10. [What is z-index?](#10-what-is-z-index)
11. [What is transform in CSS?](#11-what-is-transform-in-css)
12. [What are CSS animations?](#12-what-are-css-animations)
13. [What is Tailwind CSS?](#13-what-is-tailwind-css)
14. [Why do companies prefer Tailwind?](#14-why-do-companies-prefer-tailwind)
15. [How do you make a website responsive in Tailwind?](#15-how-do-you-make-a-website-responsive-in-tailwind)
16. [BONUS: How do you handle layout in CSS?](#bonus-how-do-you-handle-layout-in-css)

---

## 1️⃣ What is CSS?

**Answer:**
CSS stands for Cascading Style Sheets.  
It is used to style HTML elements — like colors, fonts, spacing, layout, animations, and responsiveness.

---

## 2️⃣ What is Flexbox?

**Answer:**
Flexbox is a one-dimensional layout system in CSS.  
It helps to arrange items in a row or a column easily.  
It handles alignment, spacing, and responsiveness without needing floats or complex code.

---

## 3️⃣ When do you use Flexbox?

**Answer:**
I use Flexbox when I need to align items horizontally or vertically, center content, or create responsive layouts like navbars and card layouts.

---

## 4️⃣ What is CSS Grid?

**Answer:**
Grid is a two-dimensional layout system.  
It allows us to design web layouts using rows and columns together.  
It's great for full-page layouts or dashboards.

---

## 5️⃣ Difference between Flexbox and Grid?

**Answer:**
- Flexbox → One dimension (row OR column)  
- Grid → Two dimensions (rows AND columns)  
- Flexbox is best for simple alignment; Grid is best for full layouts.

---

## 6️⃣ What is Responsive Design?

**Answer:**
Responsive design means the website adjusts automatically on all screen sizes — mobile, tablet, laptop, desktop.  
We achieve this using flexible units, Flexbox/Grid, and media queries.

---

## 7️⃣ What are Media Queries?

**Answer:**
Media queries are used to apply different CSS styles based on screen size.  
For example:  
```css
@media (max-width: 768px) { ... }
```  
They help make websites mobile-friendly.

---

## 8️⃣ What are CSS Positions?

**Answer:**
There are 5 main positions in CSS: static, relative, absolute, fixed, sticky.  
These control how an element is placed on a page.

---

## 9️⃣ Difference between Absolute and Relative Position?

**Answer:**
- Absolute → moves the element based on its nearest positioned parent.  
- Relative → moves an element based on its own original position.  
- Absolute breaks the flow; relative stays in the flow.

---

## 🔟 What is z-index?

**Answer:**
z-index controls which element appears on top when elements overlap.  
Higher z-index = appears above lower z-index.

---

## 1️⃣1️⃣ What is transform in CSS?

**Answer:**
Transform is used to move, rotate, scale, or skew elements.  
Example:  
```css
transform: scale(1.2);
```  
enlarges an element.

---

## 1️⃣2️⃣ What are CSS animations?

**Answer:**
CSS animations allow us to animate elements without JavaScript.  
We use `@keyframes` to define the animation and `animation:` property to apply it.

---

## 1️⃣3️⃣ What is Tailwind CSS?

**Answer:**
Tailwind is a utility-first CSS framework.  
Instead of writing custom CSS, we use classes like `flex`, `mt-4`, `text-center`, `p-2`.  
It speeds up development and keeps design consistent.

---

## 1️⃣4️⃣ Why do companies prefer Tailwind?

**Answer:**
Because Tailwind is fast, consistent, and reduces custom CSS.  
Developers can build responsive UI quickly, and the code remains clean and maintainable.

---

## 1️⃣5️⃣ How do you make a website responsive in Tailwind?

**Answer:**
I use Tailwind’s responsive classes like `sm:`, `md:`, `lg:`, `xl:`.  
For example:  
```html
class="text-sm md:text-lg"
```
→ small text on mobile, bigger text on medium screens.

---

## ⭐ BONUS: How do you handle layout in CSS?

**Answer:**
I use Flexbox for small layouts, Grid for big page layouts, media queries for responsiveness, and Tailwind to build UI faster with utility classes.
```
