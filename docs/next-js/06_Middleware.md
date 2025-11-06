# ![ ](../assets/nextjs-logo.svg) Middleware in Next.js

## What is Middleware?

Middleware in **Next.js** is a special function that runs **before a request is completed**.
It allows you to **modify the request or response**, **redirect**, or **conditionally render** content **before reaching a page or API route**.

Middleware runs on the **Edge Runtime**, meaning it executes **closer to the user** — resulting in faster performance.

## Common Use Cases

- Authentication and access control
- Redirects and rewrites
- Logging and analytics
- Localization (e.g., redirecting users based on language or region)
- Feature flags or A/B testing

## File Location and Naming

Middleware is defined in a file named **`middleware.js`** or **`middleware.ts`**, placed in the **root of your project** or inside the **`src/`** directory (if you’re using one).

## Basic Example

```js
// middleware.js
import { NextResponse } from "next/server";

export function middleware(request) {
  const url = request.nextUrl.clone();

  // Example: redirect user if not logged in
  const isLoggedIn = request.cookies.get("token");

  if (!isLoggedIn && url.pathname.startsWith("/dashboard")) {
    url.pathname = "/login";
    return NextResponse.redirect(url);
  }

  return NextResponse.next();
}
```

## Matching Paths (Configuration)

You can control **where middleware runs** using the `config.matcher` property.

```js
export const config = {
  matcher: ["/dashboard/:path*", "/profile/:path*"],
};
```

- `/dashboard/:path*` → applies to all subpaths under `/dashboard`
- `/about` → applies only to `/about`

## Redirects Example

```js
import { NextResponse } from "next/server";

export function middleware(request) {
  const url = request.nextUrl.clone();

  if (url.pathname === "/") {
    url.pathname = "/home";
    return NextResponse.redirect(url);
  }

  return NextResponse.next();
}
```

## Rewriting Example

Rewriting lets you **serve content from a different path** without changing the URL.

```js
import { NextResponse } from "next/server";

export function middleware(request) {
  if (request.nextUrl.pathname === "/old-page") {
    return NextResponse.rewrite(new URL("/new-page", request.url));
  }
}
```

## Conditional Headers Example

You can modify headers in requests or responses:

```js
import { NextResponse } from "next/server";

export function middleware(request) {
  const response = NextResponse.next();
  response.headers.set("X-Custom-Header", "EdgeMiddleware");
  return response;
}
```

## Middleware Execution Order

1. The middleware runs **before the request is processed**.
2. If the middleware modifies or redirects, it affects what the user receives.
3. If not, it passes control to the requested page or API route.

## Edge Runtime Limitations

Middleware runs on the **Edge Runtime**, which:

- Does **not support Node.js APIs** like `fs`, `path`, or `process`.
- Supports **Web APIs** such as `fetch`, `URL`, and `Request`.
