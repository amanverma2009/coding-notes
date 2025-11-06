# ![ ](../assets/nextjs-logo.svg) Server Actions in Next.js

## What Are Server Actions?

Server Actions are **functions that run on the server** in Next.js, allowing you to **mutate data**, perform **secure operations**, and handle **form submissions** or **server logic** directly from components.

They are part of the **React Server Components (RSC)** architecture and introduced in **Next.js 13.4+** with the **App Router**.

## Key Features

- Run **only on the server**, never in the browser.
- Allow **form submissions without API routes**.
- **Directly access databases, files, and environment variables**.
- Reduce boilerplate by avoiding separate `/api` endpoints.
- Can be imported and used in **Server Components** and **Client Components** (with form submission).

## Benefits

1. No need for `/api` routes for simple CRUD operations
2. Automatically handled security - runs server-side only
3. Reduces client-side JavaScript bundle size
4. Great for form handling and database mutations

## Limitations

1. Must be **async** functions
2. Cannot run client-side logic or access browser APIs
3. Must use `"use server"` directive
4. Limited to App Router (not supported in Pages Router)

## Syntax

### 1. Define a Server Action

You declare a server action by adding `"use server"` at the top of a function:

```js
"use server";

export async function addTodo(formData) {
  const title = formData.get("title");
  // Example: save to database
  await db.todo.create({ data: { title } });
}
```

### 2. Use with Forms

Server Actions can be directly connected to a `<form>` element using the `action` attribute:

```jsx
<form action={addTodo}>
  <input type="text" name="title" placeholder="Enter todo" />
  <button type="submit">Add</button>
</form>
```

When the form is submitted:

- The browser automatically sends data to the server.
- The `addTodo()` server action executes on the server.
- The page re-renders with updated data (if applicable).

### 3. Use Inside Server Components

You can call server actions in server components (e.g., for fetching or mutating data):

```js
import { revalidatePath } from "next/cache";
import { addTodo } from "./actions";

export default async function TodoForm() {
  async function handleAdd(formData) {
    "use server";
    const title = formData.get("title");
    await db.todo.create({ data: { title } });
    revalidatePath("/todos"); // revalidate page after mutation
  }

  return (
    <form action={handleAdd}>
      <input name="title" />
      <button type="submit">Add Todo</button>
    </form>
  );
}
```

### 4. Use in Client Components

If you want to call a Server Action from a **Client Component**, you can import it and call it **indirectly**, but not directly (since it's server-only).

Example:

```jsx
"use client";
import { addTodo } from "../actions/todoActions";

export default function AddTodoClient() {
  const handleClick = async () => {
    const formData = new FormData();
    formData.append("title", "Learn Next.js");
    await addTodo(formData);
  };

  return <button onClick={handleClick}>Add Todo</button>;
}
```

Next.js automatically handles calling the action on the server.

## Revalidation and Cache

Server Actions integrate with **Next.js caching**:

- Use `revalidatePath("/path")` to re-render a page after data changes.
- Use `revalidateTag("tag")` if using tag-based caching.

Example:

```js
import { revalidatePath } from "next/cache";

("use server");

export async function deleteTodo(id) {
  await db.todo.delete({ where: { id } });
  revalidatePath("/todos");
}
```
