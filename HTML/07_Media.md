# HTML Media Elements

## 1. Image: `<img>`

* Embeds images into the webpage
* Inline element
* Requires `src` and `alt` attributes

```html
<img src="https://images.pexels.com/photos/1563356/pexels-photo-1563356.jpeg" alt="Image" width="200" height="100">
```

### Output:

<pre>
<img src="https://images.pexels.com/photos/1563356/pexels-photo-1563356.jpeg" alt="Image" width="200" height="100">
</pre>

## 2. Audio: `<audio>`

* Embeds audio files like `.mp3`, `.ogg`, etc.
* Requires `<source>` inside
* Needs `controls` for play/pause UI

```html
<audio controls>
  <source src="music.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

### Output:

<pre>
<audio controls>
  <source src="music.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
</pre>

## 3. Video: `<video>`

* Embeds video content like `.mp4`, `.webm`
* Use `controls`, `autoplay`, `loop`, `muted`, and `poster` attributes as needed

```html
<video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

### Output:

<pre>
<video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
</pre>

## 4. Multiple Sources: `<source>`

* Inside `<audio>` or `<video>`
* Used to provide format fallback for cross-browser compatibility

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```

### Output:

<pre>
<video controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
</pre>

## 5. Subtitles and Captions: `<track>`

* Adds subtitles, captions, descriptions, or metadata to video
* Placed inside `<video>`

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English" default>
</video>
```

### Output:

<pre>
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="subtitles.vtt" kind="subtitles" srclang="en" label="English" default>
</video>
</pre>

## 6. Canvas: `<canvas>`

* Used to draw graphics via JavaScript
* Requires a JS script to render anything

```html
<canvas id="myCanvas" width="200" height="100"></canvas>

<script>
  const canvas = document.getElementById('myCanvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = "red";
  ctx.fillRect(20, 20, 150, 50);
</script>
```

### Output:

<pre>
<canvas id="myCanvas" width="200" height="100"></canvas><script>
  const canvas = document.getElementById('myCanvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = "red";
  ctx.fillRect(20, 20, 150, 50);</script></pre>

## 7. Iframe: `<iframe>`

* Embeds other web content like maps, videos, or sites
* Use `loading="lazy"` for performance

```html
<iframe src="https://example.com" width="600" height="300" loading="lazy"></iframe>
```

### Output:

<pre>
<iframe src="https://example.com" width="600" height="300" loading="lazy"></iframe>
</pre>

## 9. Lazy Loading Media

* Helps improve performance by deferring image or iframe loading
* Supported in modern browsers

```html
<img src="https://images.pexels.com/photos/1563356/pexels-photo-1563356.jpeg" loading="lazy" alt="Lazy Image">
<iframe src="https://example.com" loading="lazy"></iframe>
```

### Output:

<pre>
<img src="https://images.pexels.com/photos/1563356/pexels-photo-1563356.jpeg" loading="lazy" alt="Lazy Image">
<iframe src="https://example.com" loading="lazy"></iframe>
</pre>
