# ![ ](../assets/nextjs-logo.svg) next/navigation Module in Next.js

The `next/navigation` module gives you client side and server side navigation APIs in the App Router. These are the modern replacements for `next/router`.

## Server Side Navigation APIs

### `redirect(url)`

Tells the server to immediately redirect to another route.

```js
import { redirect } from "next/navigation";

export async function GET() {
  redirect("/login");
}
```

It stops execution right there and sends a redirect response.

### `notFound()`

Shows the 404 page.

```js
import { notFound } from "next/navigation";

export async function GET() {
  const data = await fetchData();
  if (!data) notFound();
}
```

## Client Side Navigation APIs

### `useRouter()`

Lets you navigate programmatically inside client components.

```js
"use client";

import { useRouter } from "next/navigation";

export default function Page() {
  const router = useRouter();

  function go() {
    router.push("/dashboard");
  }

  return <button onClick={go}>Go</button>;
}
```

**Methods available**:

- `push(url)`
- `replace(url)`
- `back()`
- `forward()`
- `refresh()`

### `usePathname()`

Returns the current URL path.

```js
"use client";

import { usePathname } from "next/navigation";

export default function Example() {
  const pathname = usePathname();
  return <p>{pathname}</p>;
}
```

### `useSearchParams()`

Gives read-only access to query params.

```js
"use client";

import { useSearchParams } from "next/navigation";

export default function Example() {
  const params = useSearchParams();
  const q = params.get("q");
  return <p>{q}</p>;
}
```

### `useParams()`

Returns dynamic route parameters.

```js
"use client";

import { useParams } from "next/navigation";

export default function Page() {
  const params = useParams();
  // Example: { id: "123" }
  return <div>ID: {params.id}</div>;
}
```

## `useSelectedLayoutSegments()` and `useSelectedLayoutSegment()`

Used inside layouts to detect which segment of the route is active.

```js
"use client";

import { useSelectedLayoutSegments } from "next/navigation";

export default function Nav() {
  const segments = useSelectedLayoutSegments();
  return <p>{JSON.stringify(segments)}</p>;
}
```

Useful for active nav link highlighting in layouts.
