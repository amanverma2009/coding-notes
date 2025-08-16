# HTML Semantic Tags

Semantic tags clearly describe the **meaning** of the content inside them — making HTML **more readable, accessible, and SEO-friendly**.

They help both **developers and browsers** understand the structure and purpose of the content.

## 1. `<header>`

* Represents the header of a section or page
* Typically contains logo, navigation, or page titles

```html
<header>
  <h1>My Portfolio</h1>
  <nav>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
</header>
```

### Output:

<pre>
<header><h1>My Portfolio</h1><nav><a href="#projects">Projects</a>
<a href="#contact">Contact</a></nav></header></pre>

## 2. `<nav>`

* Defines navigation links
* Typically used inside a `<header>`, `<aside>`, or separately

```html
<nav>
  <a href="/">Home</a>
  <a href="/about">About</a>
  <a href="/services">Services</a>
</nav>
```

### Output:

<pre>
<nav><a href="/">Home</a>
<a href="/about">About</a>
<a href="/services">Services</a></nav></pre>

## 3. `<main>`

* Represents the main content of the page
* Should only be used once per page

```html
<main>
  <h2>Welcome to My Website</h2>
  <p>This is where the main content goes.</p>
</main>
```

### Output:

<pre>
<main><h2>Welcome to My Website</h2><p>This is where the main content goes.</p></main></pre>

## 4. `<section>`

* Represents a standalone section of content
* Useful for grouping related content blocks

```html
<section>
  <h2>Projects</h2>
  <p>Here are some of my recent works.</p>
</section>
```

### Output:

<pre>
<section><h2>Projects</h2><p>Here are some of my recent works.</p></section></pre>

## 5. `<article>`

* Represents **independent, reusable** content — like blog posts, news articles, or comments

```html
<article>
  <h2>Blog Post Title</h2>
  <p>This is the content of the blog post.</p>
</article>
```

### Output:

<pre>
<article><h2>Blog Post Title</h2><p>This is the content of the blog post.</p></article></pre>

## 6. `<aside>`

* Represents side content — like sidebars, ads, or related links
* Should be related to the main content

```html
<aside>
  <h3>Related Posts</h3>
  <ul>
    <li><a href="#">Post 1</a></li>
    <li><a href="#">Post 2</a></li>
  </ul>
</aside>
```

### Output:

<pre>
<aside><h3>Related Posts</h3><ul><li><a href="#">Post 1</a></li><li><a href="#">Post 2</a></li></ul></aside></pre>

## 7. `<footer>`

* Represents the footer of a section or page
* Commonly includes copyright, contact info, or navigation

```html
<footer>
  <p>&copy; 2025 Aman Verma. All rights reserved.</p>
</footer>
```

### Output:

<pre>
<footer><p>&copy; 2025 Aman Verma. All rights reserved.</p></footer></pre>

## 8. `<figure>` and `<figcaption>`

* Used to wrap media (image, chart, video) and its caption

```html
<figure>
  <img src="https://as1.ftcdn.net/v2/jpg/05/40/08/54/1000_F_540085480_WN26Tz5VOFRwdPsLmK73JXNuSYsi2luw.jpg" alt="Project Screenshot">
  <figcaption>Screenshot of my latest project</figcaption>
</figure>
```

### Output:

<pre>
<figure><img src="https://as1.ftcdn.net/v2/jpg/05/40/08/54/1000_F_540085480_WN26Tz5VOFRwdPsLmK73JXNuSYsi2luw.jpg" alt="Project Screenshot"><figcaption>Screenshot of my latest project</figcaption></figure></pre>

## 9. `<mark>` (Highlight Text)

* Highlights or emphasizes text

```html
<p>I want to <mark>highlight</mark> this word.</p>
```

### Output:

<pre><p>I want to <mark>highlight</mark> this word.</p></pre>
