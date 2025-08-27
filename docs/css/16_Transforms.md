# ![ ](../assets/css-logo.svg) Transforms

The `transform` property lets you apply **2D and 3D transformations** to elements — such as rotating, scaling, moving, or skewing.

## 1. `translate(x, y)`

Moves an element from its current position.

```css
.box {
  transform: translate(50px, 20px);
}
```

* `x` = horizontal shift
* `y` = vertical shift

## 2. `scale(x, y)`

Resizes the element.

```css
.box {
  transform: scale(1.5); /* 1.5x both axes */
}
```

```css
transform: scale(1.2, 0.8); /* x = 120%, y = 80% */
```

## 3. `rotate(angle)`

Rotates the element around its center.

```css
.box {
  transform: rotate(45deg);
}
```

Use negative angles for counter-clockwise rotation.

## 4. `skew(x, y)`

Skews (slants) the element.

```css
.box {
  transform: skew(20deg, 10deg);
}
```

## 5. Combine Multiple Transforms

```css
.box {
  transform: translateX(50px) rotate(15deg) scale(1.2);
}
```

They are applied **in order**, left to right.

## 6. `transform-origin`

Sets the point of transformation.

```css
.box {
  transform: rotate(45deg);
  transform-origin: top left;
}
```

Default is `center center`.

## 7. 3D Transforms (Basic)

Enable 3D perspective with:

```css
.container {
  perspective: 1000px;
}

.box {
  transform: rotateY(45deg);
}
```

## 8. Performance Note

Transforms are GPU-accelerated and more performant than changing `top`, `left`, etc. Use them for animations/movement.
