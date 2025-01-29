# Advanced HTML Concepts

## 1. **Semantic HTML**
Semantic HTML uses elements that have meaningful names, improving accessibility and SEO.

### Common Semantic Tags:
- `<header>`: Represents the header of a document or section.
- `<nav>`: Defines navigation links.
- `<main>`: Indicates the main content of the document.
- `<article>`: Represents an independent piece of content.
- `<section>`: Groups related content together.
- `<footer>`: Represents the footer of a document or section.

#### Example:
```html
<header>
  <h1>Website Title</h1>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>
<main>
  <section>
    <h2>Introduction</h2>
    <p>Welcome to our website.</p>
  </section>
  <article>
    <h2>Blog Post</h2>
    <p>This is an example blog post.</p>
  </article>
</main>
<footer>
  <p>&copy; 2025 Company Name</p>
</footer>
```
- The `<header>` contains the website title and navigation links.
- `<main>` groups the primary content, including sections and articles.
- `<footer>` adds copyright information.

---

## 2. **HTML Forms**
Forms collect user input, which can be sent to a server for processing.

### Basic Structure:
```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <label for="password">Password:</label>
  <input type="password" id="password" name="password">

  <button type="submit">Submit</button>
</form>
```

#### Explanation:
- `action`: The URL where form data is sent.
- `method`: Specifies the HTTP method (`GET` or `POST`).
- `<label>`: Improves accessibility by associating text with form controls.
- `required`: Ensures the field must be filled before submission.

---

## 3. **Tables**
Tables display structured data.

### Example:
```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>25</td>
      <td>New York</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>30</td>
      <td>Los Angeles</td>
    </tr>
  </tbody>
</table>
```
- `<thead>`: Groups header rows.
- `<tbody>`: Groups body rows.
- `<th>`: Defines table headers.
- `<td>`: Defines table cells.

---

## 4. **HTML Multimedia**
HTML supports embedding images, videos, and audio.

### Images:
```html
<img src="image.jpg" alt="Description of image" width="300">
```
- `src`: Specifies the image file.
- `alt`: Provides alternative text for accessibility.

### Videos:
```html
<video controls width="500">
  <source src="video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```
- `controls`: Adds playback controls.
- `<source>`: Specifies video files.

### Audio:
```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  Your browser does not support the audio tag.
</audio>
```
- Similar to `<video>`, but for audio.

---

## 5. **HTML APIs**
HTML5 introduces APIs for dynamic features.

### Geolocation API:
```html
<button onclick="getLocation()">Get Location</button>
<p id="location"></p>

<script>
function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition((position) => {
      document.getElementById("location").textContent =
        `Latitude: ${position.coords.latitude}, Longitude: ${position.coords.longitude}`;
    });
  } else {
    document.getElementById("location").textContent = "Geolocation is not supported.";
  }
}
</script>
```
- `navigator.geolocation`: Accesses the user's location.
- `getCurrentPosition`: Retrieves latitude and longitude.

---

## 6. **Responsive Design in HTML**
Responsive designs adapt to different screen sizes.

### Viewport Meta Tag:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- Ensures proper scaling on mobile devices.

### Picture Element:
```html
<picture>
  <source srcset="image-large.jpg" media="(min-width: 800px)">
  <source srcset="image-small.jpg" media="(max-width: 799px)">
  <img src="image-default.jpg" alt="Responsive Image">
</picture>
```
- Loads different images based on screen size.

---

## 7. **HTML5 Elements for Interactivity**
### `<details>` and `<summary>`:
```html
<details>
  <summary>More Info</summary>
  <p>This is additional information.</p>
</details>
```
- `<details>` creates a collapsible section.
- `<summary>` defines the visible heading.

---

## 8. **HTML Best Practices**
- Use semantic tags for clarity and SEO.
- Include `alt` attributes for images to improve accessibility.
- Minimize inline styles; use external CSS.
- Validate HTML using tools like the W3C Validator.

---
