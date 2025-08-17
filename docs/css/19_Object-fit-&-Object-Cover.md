# CSS `object-fit` and `object-position`

The `object-fit` property defines **how content like images or videos are resized** to fit their container.

## 1. `object-fit`

### Syntax:

```css
img {
  object-fit: value;
}
```

### Values:

| Value        | Description                                                          |
| ------------ | -------------------------------------------------------------------- |
| `fill`       | Default. Stretches to fill container — **may distort** aspect ratio. |
| `contain`    | Fits inside container without cropping — maintains aspect ratio.     |
| `cover`      | Fills entire container — **may crop**, maintains aspect ratio.       |
| `none`       | Image keeps original size — no resize.                               |
| `scale-down` | Chooses the smaller result of `none` or `contain`.                   |

### Example:

```css
img {
  width: 300px;
  height: 200px;
  object-fit: cover;
}
```

**Result:** The image fills the 300×200 box, cropped if necessary.

## 2. `object-position`

Controls **alignment** of the image inside its box when `object-fit` ≠ `fill`.

### Syntax:

```css
img {
  object-position: center top;
}
```

### Common values:

* `center`, `top`, `bottom`, `left`, `right`
* You can also use `px`, `%`

### Example:

```css
img {
  object-fit: cover;
  object-position: top;
}
```

**Result:** Image fills the container, cropping from the bottom if needed.

---

## 3. Practical Use Case: Responsive Image Crop

```css
img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  object-position: center;
}
```

* Maintains aspect ratio
* Crops the excess
* Ensures consistent layout
