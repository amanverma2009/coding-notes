# CSS Transitions

CSS transitions let you smoothly animate changes in CSS property values over time.

## 1. Basic Syntax

```css
.element {
  transition: property duration timing-function delay;
}
```

Example:

```css
.button {
  background-color: blue;
  transition: background-color 0.3s ease-in-out;
}

.button:hover {
  background-color: red;
}
```

When `:hover` is triggered, the background smoothly changes from blue to red.

## 2. Shorthand Breakdown

```css
transition: all 0.5s ease 0.1s;
```

* `property` — what to animate (`color`, `all`, etc.)
* `duration` — how long the transition lasts (`s` or `ms`)
* `timing-function` — how the animation accelerates
* `delay` — time before transition starts

## 3. Timing Functions

| Value               | Description         |
| ------------------- | ------------------- |
| `linear`            | Constant speed      |
| `ease`              | Slow → fast → slow  |
| `ease-in`           | Slow start          |
| `ease-out`          | Slow end            |
| `ease-in-out`       | Slow start and end  |
| `cubic-bezier(...)` | Custom easing curve |

## 4. Multiple Properties

```css
.box {
  transition: width 0.3s ease, background-color 0.3s linear;
}
```

Each property can have its own config.

## 5. Transitionable Properties

Only **animatable properties** can be transitioned:

✅ Examples:

* `color`
* `background-color`
* `width`, `height`
* `transform`
* `opacity`
* `margin`, `padding`

❌ Not animatable:

* `display`
* `position`
* `visibility` (though can be paired with `opacity`)

## 6. Tips

* Use `transition: all` with caution — it's less performant and harder to debug.
* Transitions only work when there's a change in property value (e.g. via `:hover`, `.active`, JS toggle).

## 7. Example: Button Hover

```css
.button {
  background-color: #333;
  color: white;
  transition: background-color 0.3s ease, transform 0.2s;
}

.button:hover {
  background-color: #555;
  transform: scale(1.05);
}
```
