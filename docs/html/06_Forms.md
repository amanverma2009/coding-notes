# HTML Forms

## 1. Basic Form Structure

```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="username">
  <button type="submit">Submit</button>
</form>
```

### Output:

<pre>
<form action="/submit" method="POST"><label for="name">Name:</label>
<input type="text" id="name" name="username">
<button type="submit">Submit</button>
</form></pre>

## 2. Common Input Types

```html
<input type="text">
<input type="password">
<input type="email">
<input type="number">
<input type="date">
<input type="file">
<input type="checkbox">
<input type="radio">
<input type="submit">
<input type="reset">
```

### Output:

<pre>
<input type="text">
<input type="password">
<input type="email">
<input type="number">
<input type="date">
<input type="file">
<input type="checkbox">
<input type="radio">
<input type="submit">
<input type="reset">
</pre>

## 3. Label: `<label>`

* Associates text with a specific input
* Clicking the label focuses the input field

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email">
```

### Output:

<pre>
<label for="email">Email:</label>
<input type="email" id="email" name="email">
</pre>

## 4. Select Dropdown: `<select>`

```html
<label for="language">Choose a language:</label>
<select id="language" name="language">
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
</select>
```

### Output:

<pre>
<label for="language">Choose a language:</label>
<select id="language" name="language">
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
</select>
</pre>

## 5. Text Area: `<textarea>`

Used for multi-line input (e.g., comments or messages)

```html
<label for="msg">Message:</label>
<textarea id="msg" name="message" rows="4" cols="30"></textarea>
```

### Output:

<pre>
<label for="msg">Message:</label>
<textarea id="msg" name="message" rows="4" cols="30"></textarea></pre>

## 6. Radio Buttons and Checkboxes

```html
<label>
  <input type="radio" name="gender" value="male"> Male
</label>
<label>
  <input type="radio" name="gender" value="female"> Female
</label>

<label>
  <input type="checkbox" name="subscribe" checked> Subscribe to newsletter
</label>
```

### Output:

<pre>
<label><input type="radio" name="gender" value="male"> Male</label>
<label><input type="radio" name="gender" value="female"> Female</label>

<label><input type="checkbox" name="subscribe" checked> Subscribe to newsletter</label>
</pre>

## 7. Fieldset and Legend

* Group related form elements together

```html
<fieldset>
  <legend>Login Info</legend>
  <label>Username: <input type="text" name="user"></label><br>
  <label>Password: <input type="password" name="pass"></label>
</fieldset>
```

### Output:

<pre>
<fieldset>
  <legend>Login Info</legend>
  <label>Username: <input type="text" name="user"></label><br>
  <label>Password: <input type="password" name="pass"></label>

</fieldset></pre>

## 8. Button: `<button>`

```html
<button type="submit">Submit Form</button>
<button type="reset">Reset Form</button>
<button type="button" onclick="alert('Clicked!')">Click Me</button>
```

### Output:

<pre>
<button type="submit">Submit Form</button>
<button type="reset">Reset Form</button>
<button type="button" onclick="alert('Clicked!')">Click Me</button>
</pre>

## 9. Form Attributes

| Attribute      | Description                          |
| -------------- | ------------------------------------ |
| `action`       | URL where the form data will be sent |
| `method`       | HTTP method to use (`GET` or `POST`) |
| `autocomplete` | Enables or disables autocomplete     |
| `novalidate`   | Disables default browser validation  |

## 10. Input Attributes

| Attribute     | Description                              |
| ------------- | ---------------------------------------- |
| `type`        | Specifies the input type                 |
| `name`        | Name for form submission                 |
| `value`       | Pre-filled value                         |
| `placeholder` | Hint text inside input                   |
| `required`    | Makes input mandatory                    |
| `readonly`    | Makes input non-editable                 |
| `disabled`    | Disables the input                       |
| `min`, `max`  | Minimum/maximum values (for number/date) |
| `pattern`     | Regex pattern for validation             |
