# Dynamic Routes in Next.js

## What are Dynamic Routes

Dynamic routes let you create pages where part of the URL is variable. For example:

* `/products/1`
* `/products/2`
* `/blog/how-to-code`
* `/user/steve`

These routes share the same page structure but show different data.

## How to Create a Dynamic Route

Use square brackets for the file or folder name.

Example:

```text
app/
  blog/
    [slug]/
      page.js
```

This makes `/blog/something` work.

Another example:

```text
app/
  product/
    [id]/
      page.js
```

This makes `/product/123` work.

## Accessing Route Params

In the App Router (Next.js 13+):

```js
export default function Page({ params }) {
  return (
    <div>
      <h1>Product ID: {params.id}</h1>
    </div>
  )
}
```

`params.id` is the dynamic value from the URL.

## Multiple Dynamic Segments

Example:

```text
app/
  blog/
    [year]/
      [slug]/
        page.js
```

Gives URLs like:
`/blog/2025/nextjs-routing`

Access:

```js
export default function Page({ params }) {
  const { year, slug } = params
}
```

## Catch All Routes

Sometimes you need to match any depth.

### Catch-all:

```text
app/docs/[...slug]/page.js
```

URL examples:

* `/docs/getting-started`
* `/docs/guides/install/setup`

`params.slug` becomes an array.

### Optional Catch-all:

```text
app/docs/[[...slug]]/page.js
```

Matches:

* `/docs`
* `/docs/a`
* `/docs/a/b`

## Dynamic API Routes

In `app/api` or `pages/api`:

```text
app/api/user/[id]/route.js
```

Access:

```js
export async function GET(req, { params }) {
  return Response.json({ id: params.id })
}
```

## Pre-rendering with generateStaticParams

For static site generation:

```js
export async function generateStaticParams() {
  return [
    { id: "1" },
    { id: "2" }
  ]
}
```
