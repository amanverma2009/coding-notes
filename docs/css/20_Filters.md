# ![ ](../assets/css-logo.svg) Filters

The `filter` property applies **visual effects** (like blur, brightness, contrast, etc.) to elements — especially images and backgrounds.

## 1. Syntax

```css
.element {
  filter: filter-function(value);
}
```

Multiple filters can be chained:

```css
filter: brightness(1.2) contrast(90%) saturate(150%);
```

## 2. Common Filter Functions

### a) `blur(px)`

Applies Gaussian blur.

```css
filter: blur(5px);
```

### b) `brightness(%)`

Controls light intensity.

```css
filter: brightness(150%); /* brighter */
filter: brightness(50%);  /* darker */
```

### c) `contrast(%)`

Adjusts contrast.

```css
filter: contrast(200%);
```

### d) `grayscale(%)`

Converts to grayscale.

```css
filter: grayscale(100%);
```

### e) `sepia(%)`

Applies a warm, brown tone.

```css
filter: sepia(100%);
```

### f) `saturate(%)`

Controls color intensity.

```css
filter: saturate(200%);
```

### g) `hue-rotate(deg)`

Shifts hue (color spectrum rotation).

```css
filter: hue-rotate(90deg);
```

### h) `invert(%)`

Inverts colors.

```css
filter: invert(100%);
```

### i) `opacity(%)`

Sets element transparency.

```css
filter: opacity(70%);
```

## 3. Example: Hover Filter

```css
img {
  filter: grayscale(100%);
  transition: filter 0.3s;
}

img:hover {
  filter: grayscale(0%);
}
```

## 4. Notes

* Filters affect rendering — may impact performance.
* Works on most elements (`<img>`, `<div>`, pseudo-elements, etc.).
* Combine with transitions for smooth effects.
