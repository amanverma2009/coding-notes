# ![ ](../assets/nextjs-logo.svg) Script, Link & Image components in Next.js

## 1. **`<Script>` Component**

The `<Script>` component in Next.js is used to load third-party scripts (like analytics or ads) efficiently. It helps improve **performance and control** over when and how scripts are executed.

### **Import**

```javascript
import Script from "next/script";
```

### **Example**

```jsx
<Script
  src="https://example.com/script.js"
  strategy="lazyOnload"
  onLoad={() => console.log("Script loaded!")}
/>
```

### **Script Loading Strategies**

| Strategy                | Description                                                                               |
| ----------------------- | ----------------------------------------------------------------------------------------- |
| **`beforeInteractive`** | Loads the script **before the page becomes interactive**. Useful for critical scripts.    |
| **`afterInteractive`**  | Default. Loads **right after** the page becomes interactive.                              |
| **`lazyOnload`**        | Loads **during idle time** (after onload event). Ideal for analytics or tracking scripts. |
| **`worker`**            | Loads script **inside a web worker** (for heavy scripts).                                 |

### **Example with Google Analytics**

```jsx
<Script
  src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"
  strategy="afterInteractive"
/>
<Script id="google-analytics" strategy="afterInteractive">
  {`
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'GA_TRACKING_ID');
  `}
</Script>
```

## 2. **`<Link>` Component**

The `<Link>` component enables **client-side navigation** between pages — meaning page transitions are instant and don’t reload the browser.

### **Import**

```javascript
import Link from "next/link";
```

### **Example**

```jsx
<Link href="/about">About Us</Link>
```

✅ **No full page reload**
✅ **Preserves React state**
✅ **Prefetching enabled by default**

### **With Child Element**

```jsx
<Link href="/blog">
  <button>Go to Blog</button>
</Link>
```

### **Prefetch**

- Next.js automatically prefetches links when they are visible in the viewport.
- To disable prefetch:

```jsx
<Link href="/contact" prefetch={false}>
  Contact
</Link>
```

## 3. **`<Image>` Component**

The `<Image>` component is used for **optimized image loading**, **lazy loading**, **resizing**, and **format conversion** automatically.

### **Import**

```javascript
import Image from "next/image";
```

### **Example**

```jsx
<Image src="/hero.jpg" alt="Hero Banner" width={800} height={400} priority />
```

### **Key Props**

| Prop                   | Description                                                       |
| ---------------------- | ----------------------------------------------------------------- |
| **`src`**              | Image source (local or remote).                                   |
| **`alt`**              | Alt text for accessibility.                                       |
| **`width` & `height`** | Required for layout and optimization.                             |
| **`priority`**         | Preloads image for faster loading (good for hero images).         |
| **`fill`**             | Makes image fill its parent container using absolute positioning. |
| **`sizes`**            | Defines responsive image sizes for different screen widths.       |

### **Example: Responsive Image**

```jsx
<div className="relative w-[100%] h-[400px]">
  <Image
    src="/banner.jpg"
    alt="Banner"
    fill
    sizes="(max-width: 768px) 100vw, 50vw"
    style={{ objectFit: "cover" }}
  />
</div>
```

### **Remote Images**

Add domains in `next.config.js`:

```js
module.exports = {
  images: {
    domains: ["example.com", "images.unsplash.com"],
  },
};
```
