# ![ ](../assets/nextjs-logo.svg) Server Components in Next.js

## What are Server Components?

Server Components are React components that are **rendered on the server** instead of the client.
They allow you to **fetch data, perform heavy computations, and render HTML** directly on the server before sending it to the browser.

In Next.js (especially with the App Router), **Server Components are the default** type of components.

## Key Characteristics

* **Executed on the Server:** The code runs only on the server, never sent to the client.
* **No Client-Side JavaScript:** Since they're not hydrated in the browser, bundle size is reduced.
* **Can Fetch Data Directly:** You can use async/await for data fetching directly inside components.
* **Secure:** Sensitive data (like API keys) stays on the server.

## Syntax Example

```jsx
// app/page.js
import UserList from './UserList';

export default async function Page() {
  const data = await fetch('https://jsonplaceholder.typicode.com/users');
  const users = await data.json();

  return (
    <div>
      <h1>Users</h1>
      <UserList users={users} />
    </div>
  );
}
```

```jsx
// app/UserList.js
export default function UserList({ users }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

Both components here are **Server Components** by default.

## Benefits of Server Components

1. **Improved Performance**

   * Less JavaScript sent to the client → faster page loads.
2. **Direct Data Access**

   * No need for API routes or extra network calls between client and server.
3. **Better Security**

   * Secrets remain on the server.
4. **SEO-Friendly**

   * HTML is pre-rendered and easily indexed by search engines.

## When to Use Server Components

* When you need **data fetching** (e.g., from databases or APIs).
* For **static content** or **HTML-heavy components**.
* When you don’t need interactivity or client-side state.

## Limitations

* Cannot use browser-only APIs (like `window`, `document`, or `localStorage`).
* Cannot use React hooks like `useState`, `useEffect`.
* Cannot attach event handlers (like `onClick`).

If you need any of these → use a **Client Component**.

## Mixing Server and Client Components

You can combine them for flexibility.

```jsx
// app/page.js (Server Component)
import LikeButton from './LikeButton';

export default async function Page() {
  const post = await getPost();

  return (
    <div>
      <h1>{post.title}</h1>
      <LikeButton /> {/* Client Component */}
    </div>
  );
}
```

```jsx
// app/LikeButton.js (Client Component)
'use client';
import { useState } from 'react';

export default function LikeButton() {
  const [liked, setLiked] = useState(false);
  return <button onClick={() => setLiked(!liked)}>{liked ? 'Liked' : 'Like'}</button>;
}
```

## How Next.js Decides

* Files **without `'use client'`** → Server Components (default).
* Files **with `'use client'`** → Client Components.
