# ![ ](../assets/html-logo.svg) Generic HTML Containers

## 🔹`<div>` — Block-level Container

* Block-level element
* Takes up the full width of its parent
* Starts on a new line
* Commonly used to group large sections of HTML

### Example

```html
<div>
  <h2>Welcome</h2>
  <p>This is a section grouped using a div.</p>
</div>
```

### Output:

<pre>
<div>
<h2>Welcome</h2>
<p>This is a section grouped using a div.</p>
</div></pre>

### Use Cases:

* Layout sections
* Wrapping multiple elements
* Styling or scripting group of elements

## 🔹 `<span>` — Inline Container

* Inline element
* Takes only as much width as necessary
* Does **not** break into a new line
* Used to style or script **inline text portions**

### Example:

```html
<p>This is a <span style="color: red;">highlighted</span> word.</p>
```

### Output:

<pre>
<p>This is a <span style="color: red;">highlighted</span> word.</p></pre>

### Use Cases:

* Highlight part of a sentence
* Apply CSS to a few words
* Target with JavaScript for inline elements
