# DOM Part 3: Creating & Removing Elements

## 1. `createElement()`

Creates a new DOM element (not in the document yet).

```js
let newDiv = document.createElement("div");
newDiv.innerText = "Hello World";
```

## 2. `append()` and `appendChild()`

Adds element to the **end** of a parent.

```js
document.body.append(newDiv);       // accepts text, multiple elements
parent.appendChild(newDiv);         // older, only one node
```

### `prepend()`

Adds to the **start** of a parent.

```js
parent.prepend(newDiv);
```

## 3. `insertBefore()`

Inserts a node before another inside the same parent.

```js
parent.insertBefore(newNode, referenceNode);
```

## 4. `remove()` (modern)

Removes an element directly.

```js
element.remove();
```

## 5. `removeChild()` (older)

Used on the **parent**, passing the child to remove.

```js
parent.removeChild(child);
```

## 6. `replaceChild()`

Replaces one child with another.

```js
parent.replaceChild(newNode, oldNode);
```

## 7. Cloning Nodes

### `cloneNode(deep)`

* `true` → clone entire element with children
* `false` → only clone the node itself

```js
let clone = original.cloneNode(true);
parent.append(clone);
```

## 8. Example: Add New List Item

```js
let li = document.createElement("li");
li.innerText = "New Item";

document.querySelector("ul").appendChild(li);
```
