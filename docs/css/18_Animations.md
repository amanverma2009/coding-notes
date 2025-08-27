# ![ ](../assets/css-logo.svg) Animations

CSS animations let you create complex, keyframe-based transitions between styles over time — without JavaScript.

## 1. Basic Structure

```css
.element {
  animation: name duration timing-function delay iteration-count direction fill-mode;
}
```

Only `animation-name` and `animation-duration` are required.

## 2. Example

```css
@keyframes slideIn {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}

.box {
  animation: slideIn 0.5s ease-out;
}
```

## 3. Key Properties

### a) `animation-name`

The name of the `@keyframes`.

```css
animation-name: fadeIn;
```

### b) `animation-duration`

How long the animation takes.

```css
animation-duration: 1s;
```

### c) `animation-timing-function`

Controls animation pacing.

```css
animation-timing-function: ease | linear | ease-in | ease-out | ease-in-out | cubic-bezier();
```

### d) `animation-delay`

Wait time before animation starts.

```css
animation-delay: 0.5s;
```

### e) `animation-iteration-count`

Number of repeats.

```css
animation-iteration-count: 3;   /* 3 times */
animation-iteration-count: infinite;
```

### f) `animation-direction`

Direction of each cycle.

```css
normal | reverse | alternate | alternate-reverse;
```

### g) `animation-fill-mode`

Defines how styles apply **before/after** animation.

```css
none | forwards | backwards | both;
```

Example:

```css
animation-fill-mode: forwards;
```

Keeps final keyframe styles after animation ends.

## 4. Shorthand

```css
animation: fadeIn 1s ease-in 0.2s 1 normal forwards;
```

## 5. Pausing/Controlling

```css
.element {
  animation-play-state: paused | running;
}
```

## 6. Multiple Animations

```css
animation: move 1s ease, fade 2s linear;
```

## 7. Example: Bounce

```css
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.ball {
  animation: bounce 0.6s infinite;
}
```
