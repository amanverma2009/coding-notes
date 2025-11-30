# ![ ](../assets/nextjs-logo.svg) Layouts in Next.js

## What is a Layout

A layout is a shared UI wrapper that surrounds your pages and components. It stays persistent across route changes and prevents unnecessary re-renders.
Located at: `app/layout.js` or any route’s `layout.js`.

## Key Features

* Persistent components across navigation
* Automatic nested layouts
* Server components by default
* Can fetch data
* Perfect for shared UI: navbars, sidebars, footers, providers

## Root Layout

File: `app/layout.js`

* Required for every Next.js app
* Defines HTML structure, `<html>`, `<body>`
* Wraps the entire app

**Example:**

```jsx
// app/layout.js
export const metadata = {
  title: "My App"
}

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        <Navbar />
        {children}
      </body>
    </html>
  )
}
```

## Nested Layouts

Each folder inside `app/` can have its own `layout.js`.

Folder structure:

```text
app/
 ├ layout.js
 ├ dashboard/
 │   ├ layout.js
 │   └ page.js
 └ settings/
     └ page.js
```

How it works:

* `app/layout.js` wraps everything
* `app/dashboard/layout.js` wraps only `/dashboard` and its children

Nested example:

```jsx
// app/dashboard/layout.js
export default function DashboardLayout({ children }) {
  return (
    <section>
      <aside>Dashboard Sidebar</aside>
      <main>{children}</main>
    </section>
  )
}
```

## Rendering Behavior

* Layouts are **Server Components** unless you add `"use client"`
* They persist across route changes
* Only the `children` part updates
* This improves performance and UX

## Shared UI Patterns

Layouts are perfect for:

* Navbars
* Footers
* Sidebars
* Page containers
* Themes
* Global Providers (wrapped inside body)

## Layout vs Template

| Feature     | Layout                       | Template                           |
| ----------- | ---------------------------- | ---------------------------------- |
| Persistence | Persistent across navigation | Re-rendered on each route          |
| Use case    | Headers, navbars, providers  | Per-page animations or state reset |
| Lifecycle   | Only rendered once           | Rendered every time route changes  |

## Example Layout with Providers

```jsx
// app/layout.js
import { ThemeProvider } from "@/components/theme-provider"

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        <ThemeProvider>
          {children}
        </ThemeProvider>
      </body>
    </html>
  )
}
```

## Segment Layouts

You can apply a layout only to a specific subfolder.
Example: `app/blog/layout.js` affects only blog routes.

## Route Groups with Layouts

Use folder names like `(marketing)` to group routes without affecting URL.

Structure:

```text
app/
 ├ (marketing)/
 │    ├ layout.js
 │    └ page.js
 └ (dashboard)/
      ├ layout.js
      └ page.js
```

URL stays clean, but UI stays grouped.

## File Hierarchy Summary

| File           | Purpose                   |
| -------------- | ------------------------- |
| `layout.js`    | Shared persistent wrapper |
| `page.js`      | Actual route content      |
| `template.js`  | Re-rendering UI wrapper   |
| `loading.js`   | Suspense loading state    |
| `error.js`     | Error boundary            |
| `not-found.js` | 404 for that segment      |
