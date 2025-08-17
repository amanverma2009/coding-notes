# Lists

## 1. Unordered List: `<ul>`

* Used for lists **without a specific order**
* List items are marked with **bullets** by default

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

### Output:

<pre>
<ul><li>HTML</li><li>CSS</li><li>JavaScript</li></ul></pre>

## 2. Ordered List: `<ol>`

* Used for lists where the **order matters**
* List items are marked with **numbers** by default

```html
<ol>
  <li>Wake up</li>
  <li>Brush teeth</li>
  <li>Start coding</li>
</ol>
```

### Output:

<pre><ol><li>Wake up</li><li>Brush teeth</li><li>Start coding</li></ol></pre>

### Type Attribute:

You can use the type attribute to change numbering:

```html
<ol type="A">
  <li>Step One</li>
  <li>Step Two</li>
</ol>
```

Types:

* 1 – Default (numbers)
* A – Uppercase letters
* a – Lowercase letters
* I – Uppercase Roman numerals
* i – Lowercase Roman numerals

## 3. Description List: `<dl>`

* Used for name/value pairs such as terms and definitions

### Syntax:

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

* `<dl>` — Description List
* `<dt>` — Description Term
* `<dd>` - Description Definition

### Output:

<pre>
<dl><dt>HTML</dt><dd>HyperText Markup Language</dd><dt>CSS</dt><dd>Cascading Style Sheets</dd></dl></pre>

## Nesting Lists

Lists can be nested inside one another. Used for:

* Navigation menus
* Step-by-step instructions
* Glossaries
* FAQs
* Feature lists

```html
<ol>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>Backend
    <ul>
        <li>NodeJS</li>
        <li>ExpressJS</li>
        <li>MySQL</li>
    </ul>
  </li>
  and much more!
</ol>
```

### Output:

<pre><ol><li>Frontend<ul><li>HTML</li><li>CSS</li><li>JavaScript</li></ul></li><li>Backend<ul><li>NodeJS</li><li>ExpressJS</li><li>MySQL</li></ul></li></ol>and much more!</pre>