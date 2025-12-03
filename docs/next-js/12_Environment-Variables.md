# ![ ](../assets/nextjs-logo.svg) Environment Variables in Next.js

## Why Environment Variables Matter

Environment variables let you store sensitive values outside your codebase. They keep secrets secure and allow different values for development and production.

## Naming Conventions

### Public Variables

These start with `NEXT_PUBLIC_`. They are exposed to the browser.

Example:

```env
NEXT_PUBLIC_API_URL=https://example.com/api
```

Use in code:

```js
const url = process.env.NEXT_PUBLIC_API_URL;
```

### Server Only Variables

These do not start with `NEXT_PUBLIC_`. They are available only on the server.

Example:

```env
DATABASE_URL=mongodb+srv://...
```

Use in server components, API routes, and server actions:

```js
const db = process.env.DATABASE_URL;
```

## Where Environment Files Go

Next.js loads variables from these files:

1. `.env.local` (git ignored, highest priority)
2. `.env.development`
3. `.env.production`
4. `.env`

Example folder:

```text
project/
  .env.local
  .env
  .env.production
```

## Accessing Environment Variables

### In Server Components

```js
console.log(process.env.SECRET_KEY);
```

### In Client Components

Only public variables can be accessed.

```js
"use client";

console.log(process.env.NEXT_PUBLIC_STRIPE_KEY);
```

## Environment Variables in next.config.js

You can define custom environment variables inside config.

```js
// next.config.js
module.exports = {
  env: {
    CUSTOM_KEY: "value",
  },
};
```

Access anywhere:

```js
process.env.CUSTOM_KEY;
```

## Adding Environment Variables in Production

### Vercel

Go to:
Settings > Environment Variables > Add > Redeploy

### Other Platforms

Each platform has its own dashboard to add variables. Never push `.env.local` to GitHub.

## When You Need to Restart Dev Server

If you change a variable in `.env.local`, restart the dev server:

```cd
npm run dev
```

## Best Practices

- Never commit secrets to GitHub.
- Use `NEXT_PUBLIC_` only for safe-to-share values.
- Split variables per environment using `.env.development` and `.env.production`.
- Validate required variables on server start to avoid runtime issues.

## Example Setup

`.env.local`

```env
DATABASE_URL=...
JWT_SECRET=...
NEXT_PUBLIC_SITE_NAME=MySite
```

Usage:

```js
const db = process.env.DATABASE_URL;
const siteName = process.env.NEXT_PUBLIC_SITE_NAME;
```
