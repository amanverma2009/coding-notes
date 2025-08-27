# ![ ](../assets/html-logo.svg) Entities and Code Tags

## 1. HTML Entities

HTML Entities are used to **display reserved characters** that would otherwise be interpreted as HTML.

### Common Entities:

| Character | Entity Code | Description        |
| --------- | ----------- | ------------------ |
| `<`       | `&lt;`      | Less than          |
| `>`       | `&gt;`      | Greater than       |
| `&`       | `&amp;`     | Ampersand          |
| `"`       | `&quot;`    | Double quote       |
| `'`       | `&apos;`    | Single quote       |
| ` `       | `&nbsp;`    | Non-breaking space |

### Example:

```html
<p>5 &lt; 10 &amp;&amp; 10 &gt; 5</p>
```

### Output:

<pre>
<p>5 &lt; 10 &amp;&amp; 10 &gt; 5</p></pre>

## 2. `<code>` — Inline Code

* Displays a short snippet of code
* Renders using a monospaced font
* Usually used **inside paragraphs**

```html
<p>Use the <code>&lt;section&gt;</code> tag for grouping content.</p>
```

### Output:

<pre>
<p>Use the <code>&lt;section&gt;</code> tag for grouping content.</p></pre>

## 3. `<pre>` — Preformatted Text

* Preserves **whitespace**, **tabs**, and **line breaks**
* Often used to display **blocks of code**

```html
<pre>
function greet(name) {
  console.log("Hello, " + name);
}
</pre>
```

### Output:

<pre>
function greet(name) {
  console.log("Hello, " + name);
}
</pre>

## 4. `<kbd>` — Keyboard Input

* Used to show what the user should **type**
* Usually renders in a **monospace font**

```html
<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.</p>
```

### Output:

<pre>
<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.</p></pre>

## 5. `<samp>` — Sample Output

* Represents **sample output** from a program

```html
<p>Output: <samp>Hello, World!</samp></p>
```

### Output:

<pre>
<p>Output: <samp>Hello, World!</samp></p></pre>

## 6. `<var>` — Variable Name

* Used to represent a variable in programming or math

```html
<p>The value of <var>x</var> is 10.</p>
```

### Output:

<pre>
<p>The value of <var>x</var> is 10.</p></pre>
