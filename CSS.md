# CSS Complete Notes

## 1. **CSS Basics**
### What is CSS?
CSS (Cascading Style Sheets) is a language used to style HTML elements. It controls the layout, design, and visual presentation of web pages, enhancing their appearance and usability.

### Types of CSS
- **Inline CSS:**
  CSS rules applied directly within an element's `style` attribute. Best for quick changes or single-use styles but not recommended for large-scale projects due to poor maintainability.
  ```html
  <p style="color: red;">This is a red text.</p>
  ```
- **Internal CSS:**
  CSS rules defined within a `<style>` block in the `<head>` section of the HTML document. Useful for styling single pages.
  ```html
  <style>
    p { color: blue; }
  </style>
  ```
- **External CSS:**
  CSS rules written in a separate `.css` file. This is the most efficient method for maintaining styles across multiple web pages.
  ```html
  <link rel="stylesheet" href="styles.css">
  ```

### CSS Syntax
CSS is written as rule sets consisting of selectors and declarations.
```css
selector {
  property: value;
}
```
- **Selector:** Targets the HTML elements to style.
- **Property:** Specifies the aspect of the element to style (e.g., color, font-size).
- **Value:** Defines the style's specific appearance.

---

## 2. **Selectors**
Selectors are patterns used to target elements for styling. 

- **Universal Selector (`*`):** Targets all elements on a page.
- **Type Selector:** Targets elements by their tag name (e.g., `h1`, `p`).
- **Class Selector (`.className`):** Targets elements with a specific class. Classes can be reused across multiple elements.
  ```css
  .highlight { background-color: yellow; }
  ```
- **ID Selector (`#id`):** Targets a single, unique element with a specific ID.
  ```css
  #header { font-size: 24px; }
  ```
- **Group Selector (`,`)**: Applies the same style to multiple selectors by separating them with commas.
  ```css
  h1, p { color: green; }
  ```
- **Attribute Selector:** Targets elements based on attribute values.
  ```css
  input[type="text"] { color: red; }
  ```

Selectors can also combine for advanced targeting, such as child selectors (`>`), descendant selectors (space), and sibling selectors (`+`, `~`).

---

## 3. **Box Model**
The CSS box model describes how elements are structured and spaced on a web page. Each element is considered a rectangular box consisting of:

1. **Content:** The innermost area containing text or images.
2. **Padding:** Space between the content and the border. Increases the clickable area but does not affect spacing between elements.
3. **Border:** A visible or invisible edge around the padding.
4. **Margin:** Space outside the border, separating the element from its neighbors.

### Example:
```css
.box {
  margin: 10px;
  border: 5px solid black;
  padding: 15px;
  width: 100px;
}
```
- `width`: Specifies the content width (excluding padding, border, and margin unless `box-sizing` is adjusted).

---

## 4. **Positioning**
CSS positioning determines how elements are placed on a page.

- **Static:** Default positioning where elements follow the normal flow.
- **Relative:** Position relative to its normal flow position.
- **Absolute:** Position relative to the nearest positioned ancestor.
- **Fixed:** Position relative to the viewport, unaffected by scrolling.
- **Sticky:** A hybrid position that toggles between relative and fixed based on scroll position.

### Example:
```css
.box {
  position: absolute;
  top: 50px;
  left: 100px;
}
```

---

## 5. **Flexbox**
Flexbox is a layout model for distributing space among items in a container. It simplifies alignment, distribution, and responsiveness.

### Key Properties:
- **`display: flex;`** Enables the flex container.
- **Flex Container Properties:**
  - `flex-direction`: Defines the main axis direction (`row`, `column`).
  - `justify-content`: Aligns items along the main axis.
  - `align-items`: Aligns items along the cross axis.
  - `align-content`: Aligns multiple lines.
- **Flex Item Properties:**
  - `order`: Specifies the order of items.
  - `flex-grow`: Defines how much the item can grow.
  - `flex-shrink`: Defines how much the item can shrink.
  - `flex-basis`: Specifies the initial size before growing/shrinking.
  - `align-self`: Overrides `align-items` for a specific item.

### Example:
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

---

## 6. **Grid Layout**
CSS Grid is a powerful system for designing two-dimensional layouts.

### Key Properties:
- `display: grid;` Enables grid on a container.
- `grid-template-columns`: Defines column sizes.
- `grid-template-rows`: Defines row sizes.
- `grid-gap` (or `gap`): Defines spacing between grid items.
- `grid-column` and `grid-row`: Specifies item placement.
- `align-items`, `justify-items`: Align items within their grid areas.

### Example:
```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 10px;
}
```

Grid is ideal for complex, responsive layouts.

---

## 7. **Float and Clear**
### Float
Allows elements to be placed beside each other.
- `none` (default)
- `left`: Floats the element to the left.
- `right`: Floats the element to the right.

### Clear
Ensures elements do not wrap around floated elements.
- `none` (default)
- `left`
- `right`
- `both`

### Example:
```css
.image {
  float: left;
  margin-right: 10px;
}

.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

---

## 8. **Typography**
Typography controls the text appearance.
- `font-family`: Specifies the font.
- `font-size`: Adjusts text size.
- `font-weight`: Controls boldness.
- `line-height`: Sets line spacing.
- `text-align`: Aligns text (left, right, center, justify).
- `text-transform`: Changes text case.
- `letter-spacing`: Adjusts spacing between letters.

### Example:
```css
.text {
  font-family: Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  text-align: center;
}
```

---

## 9. **Backgrounds**
Background properties enhance element visuals.
- `background-color`: Sets the background color.
- `background-image`: Adds an image.
- `background-repeat`: Controls repetition.
- `background-size`: Resizes the image.
- `background-position`: Positions the image.
- `background-attachment`: Fixes or scrolls the background.

### Example:
```css
.background {
  background-color: lightblue;
  background-image: url('image.jpg');
  background-size: cover;
  background-position: center;
}
```

---

## 10. **Transitions and Animations**
### Transitions
Transitions smoothly change properties over time.
```css
.box {
  transition: all 0.3s ease-in-out;
}
```

### Animations
Define animations using `@keyframes`.
```css
@keyframes slide {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}

.box {
  animation: slide 2s infinite;
}
```

---

## 11. **Media Queries**
Media queries make designs responsive by applying styles based on device characteristics.
```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

---

## 12. **CSS Variables**
CSS variables enable reusable, dynamic values.
```css
:root {
  --main-color: #3498db;
}

.box {
  color: var(--main-color);
}
```

---

## 13. **Pseudo-classes and Pseudo-elements**
### Pseudo-classes
Styles specific states of an element (e.g., hover, focus).
```css
a:hover {
  color: red;
}
```

### Pseudo-elements
Styles specific parts of an element (e.g., `::before`, `::after`).
```css
p::before {
  content: "Note: ";
}
```

---

## 14. **CSS Units**
- **Absolute Units:** Fixed sizes (`px`, `cm`, `mm`, `in`).
- **Relative Units:** Scalable sizes (`em`, `rem`, `%`, `vh`, `vw`).

---
