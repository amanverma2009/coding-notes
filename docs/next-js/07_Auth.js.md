# Authentication in Next.js using Auth.js

## What is Auth.js?

**Auth.js** (formerly known as `NextAuth.js`) is a flexible and secure authentication solution for **Next.js** applications.
It supports multiple authentication methods — **OAuth providers, Credentials, Email, and more** — and integrates seamlessly with **Next.js App Router (v13+)**.

## Key Features

- Simple integration with **App Router** and **API routes**
- Supports **OAuth, Credentials, Magic Links, Email, and WebAuthn**
- Built-in support for **databases** (PostgreSQL, MongoDB, etc.)
- **JWT** and **Session-based authentication**
- Highly **customizable** with callbacks, events, and adapters
- Compatible with **TypeScript**

## Installation

```bash
npm install next-auth
```

## Folder Structure (App Router)

```plaintext
/app
  /api
    /auth
      [...nextauth]
        /route.js
  /dashboard
    page.js
  /login
    page.js
```

## Basic Setup

### 1. Create the Auth Route

File: `/app/api/auth/[...nextauth]/route.js`

```javascript
import NextAuth from "next-auth";
import GoogleProvider from "next-auth/providers/google";

export const authOptions = {
  providers: [
    GoogleProvider({
      clientId: process.env.GOOGLE_CLIENT_ID,
      clientSecret: process.env.GOOGLE_CLIENT_SECRET,
    }),
  ],
  secret: process.env.NEXTAUTH_SECRET,
};

const handler = NextAuth(authOptions);
export { handler as GET, handler as POST };
```

### 2. Add Auth.js Client in Components

You can use **NextAuth React Hooks** to handle login and logout.

```bash
npm install next-auth @auth/react
```

Then wrap your app with the provider.

File: `/app/layout.js`

```javascript
import { SessionProvider } from "next-auth/react";

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        <SessionProvider>{children}</SessionProvider>
      </body>
    </html>
  );
}
```

### 3. Sign In / Sign Out Buttons

```javascript
"use client";
import { signIn, signOut, useSession } from "next-auth/react";

export default function AuthButton() {
  const { data: session } = useSession();

  if (session) {
    return (
      <>
        <p>Signed in as {session.user.email}</p>
        <button onClick={() => signOut()}>Sign out</button>
      </>
    );
  }
  return <button onClick={() => signIn("google")}>Sign in with Google</button>;
}
```

## Securing Pages

You can protect server components or routes using `getServerSession()`.

### Example: Protected Page

```javascript
import { getServerSession } from "next-auth";
import { authOptions } from "../api/auth/[...nextauth]/route";

export default async function Dashboard() {
  const session = await getServerSession(authOptions);

  if (!session) {
    return <p>Access Denied</p>;
  }

  return <h1>Welcome, {session.user.name}</h1>;
}
```

## Supported Providers

Auth.js supports many providers out of the box:

- Google
- GitHub
- Facebook
- Discord
- Twitter
- Auth0
- Apple
- Credentials (Custom username/password)
- Email (Magic link)

Example (Credentials Provider):

```javascript
import CredentialsProvider from "next-auth/providers/credentials";

providers: [
  CredentialsProvider({
    name: "Credentials",
    credentials: {
      username: { label: "Username", type: "text" },
      password: { label: "Password", type: "password" },
    },
    async authorize(credentials) {
      const user = { id: 1, name: "Admin", email: "admin@example.com" };
      if (credentials.username === "admin" && credentials.password === "1234") {
        return user;
      }
      return null;
    },
  }),
];
```

## Session Management

You can access session data from both server and client:

### Client Side

```javascript
import { useSession } from "next-auth/react";

const { data: session } = useSession();
```

### Server Side

```javascript
import { getServerSession } from "next-auth";

const session = await getServerSession();
```

## Database Integration (Optional)

Auth.js can store users, sessions, and tokens in a database using **Adapters**.

Example for **Prisma**:

```bash
npm install @auth/prisma-adapter @prisma/client
```

```javascript
import { PrismaAdapter } from "@auth/prisma-adapter";
import { PrismaClient } from "@prisma/client";
const prisma = new PrismaClient();

export const authOptions = {
  adapter: PrismaAdapter(prisma),
  providers: [
    /* ... */
  ],
};
```

## Environment Variables

Set these in `.env.local`:

```env
GOOGLE_CLIENT_ID=your_client_id
GOOGLE_CLIENT_SECRET=your_client_secret
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_random_secret
```

## Middleware for Route Protection

You can protect routes using middleware:
File: `/middleware.js`

```javascript
export { default } from "next-auth/middleware";

export const config = {
  matcher: ["/dashboard/:path*"],
};
```
