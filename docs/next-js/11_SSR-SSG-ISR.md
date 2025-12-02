# ![ ](../assets/nextjs-logo.svg) SSR, SSG and ISR in Next.js

## Server Side Rendering (SSR)

SSR renders the page on the server for every request. The HTML is generated fresh each time someone visits the page.

### Example

Create an async function called `getServerSideProps` inside a page.

```js
export async function getServerSideProps() {
  const data = await fetch("https://api.example.com/data").then((r) =>
    r.json()
  );

  return {
    props: { data },
  };
}
```

### When to use

- Data changes on every request
- User-specific data
- SEO critical pages requiring always fresh content

### Pros

- Always up-to-date
- Great for SEO
- Secure, since secrets stay on server

### Cons

- Slower than SSG
- High server load

## Static Site Generation (SSG)

SSG generates the HTML at build time. Once built, the HTML is reused for every request.

### Example

Use `getStaticProps`.

```js
export async function getStaticProps() {
  const posts = await fetch("https://api.example.com/posts").then((r) =>
    r.json()
  );

  return {
    props: { posts },
  };
}
```

### When to use

- Content does not change often
- Blog posts, docs, product listings
- Maximum performance

### Pros

- Fastest performance
- Zero server load
- Great for SEO

### Cons

- Requires rebuild to update data
- Not suitable for rapidly changing content

## Incremental Static Regeneration (ISR)

**What it is**
ISR updates static pages after deployment without rebuilding the entire app. Next.js regenerates the page in the background after a set time.

**How to use**
Add a `revalidate` key in `getStaticProps`.

```js
export async function getStaticProps() {
  const data = await fetch("https://api.example.com/data").then((r) =>
    r.json()
  );

  return {
    props: { data },
    revalidate: 60, // regenerate every 60 seconds
  };
}
```

### When to use

- Content updates regularly but not per-request
- News, listings, dashboards, blogs with frequent updates

### Pros

- Best of SSG and SSR
- Low server load
- Automatically keeps pages fresh

### Cons

- Updates are not instant
- User may see slightly old content within revalidate window
