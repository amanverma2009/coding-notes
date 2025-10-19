# ![ ](../assets/Express.js_light.svg#only-light) ![ ](../assets/Express.js_dark.svg#only-dark) EJS Template Engine

## What is EJS?

EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. It is commonly used with Node.js for server-side rendering of dynamic content.

## Advantages of EJS

* Simple to learn for those familiar with JavaScript.
* Allows embedding JavaScript logic directly in HTML.
* Supports partials for reusable components.
* Works seamlessly with Express.js.

## Disadvantages

* Logic-heavy templates can get messy.
* Not as modern as React, Vue, or other component-based frameworks.

## Project Structure (Node.js + Express)

```text
my-ejs-project/
│
├── package.json
├── package-lock.json
├── server.js            # Main server file
│
├── views/               # All EJS templates
   ├── partials/        # Reusable components (header, footer)
   │   ├── header.ejs
   │   └── footer.ejs
   ├── index.ejs
   ├── about.ejs
   └── contact.ejs
```

## Installation

```bash
npm install ejs
```

## Setting Up EJS with Express

```javascript
const express = require('express');
const app = express();

// Set EJS as the template engine
app.set('view engine', 'ejs');

// Optional: Set views directory
app.set('views', './views');

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Creating an EJS Template

`views/index.ejs`

```html
<!DOCTYPE html>
<html>
<head>
    <title><%= title %></title>
</head>
<body>
    <h1>Hello, <%= name %>!</h1>
    <ul>
        <% items.forEach(item => { %>
            <li><%= item %></li>
        <% }) %>
    </ul>
</body>
</html>
```

## Rendering EJS Templates

```javascript
app.get('/', (req, res) => {
    res.render('index', {
        title: 'My EJS Page',
        name: 'John',
        items: ['Item 1', 'Item 2', 'Item 3']
    });
});
```

## EJS Syntax

### Output HTML

* `<%= variable %>` → Outputs the value and escapes HTML
* `<%- variable %>` → Outputs unescaped HTML

### JavaScript Code

* `<% code %>` → Executes JavaScript code (no output)

### Example

```html
<% if(user) { %>
    <p>Welcome, <%= user.name %>!</p>
<% } else { %>
    <p>Please log in.</p>
<% } %>
```

## Partial Templates (Include)

`views/header.ejs`

```html
<header>
    <h1>My Website</h1>
</header>
```

Include in main template:

```html
<%- include('header') %>
```

## Loops & Conditionals

```html
<ul>
<% for(let i=0; i<items.length; i++) { %>
    <li><%= items[i] %></li>
<% } %>
</ul>

<% if(items.length > 0) { %>
    <p>We have items!</p>
<% } else { %>
    <p>No items found.</p>
<% } %>
```
