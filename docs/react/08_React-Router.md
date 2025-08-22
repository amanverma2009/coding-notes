# React Router

React Router is a library used for handling **navigation** and **routing** in React applications. It allows you to create single-page applications (SPAs) with multiple views.

## 1. Installation

```bash
npm install react-router-dom
```

## 2. Basic Setup

Wrap your app with `BrowserRouter` in the root file:

```jsx
import { BrowserRouter } from "react-router-dom";
import App from "./App";

root.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);
```

## 3. Defining Routes

```jsx
import { Routes, Route } from "react-router-dom";
import Home from "./Home";
import About from "./About";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  );
}
```

- `path` = URL
- `element` = Component to render

## 4. Link Component

Use `Link` instead of `<a>` for navigation (prevents page reload).

```jsx
import { Link } from "react-router-dom";

<Link to="/">Home</Link>
<Link to="/about">About</Link>
```

## 5. useNavigate Hook

Programmatic navigation:

```jsx
import { useNavigate } from "react-router-dom";

function Dashboard() {
  const navigate = useNavigate();

  return <button onClick={() => navigate("/login")}>Go to Login</button>;
}
```

## 6. useParams Hook

Get URL parameters:

```jsx
<Route path="/user/:id" element={<User />} />;

function User() {
  const { id } = useParams();
  return <h1>User ID: {id}</h1>;
}
```

Visiting `/user/42` renders "User ID: 42".

## 7. useSearchParams Hook

Get query string values:

```jsx
import { useSearchParams } from "react-router-dom";

function Products() {
  const [searchParams] = useSearchParams();
  const category = searchParams.get("category");

  return <p>Category: {category}</p>;
}
```

URL: `/products?category=books`

## 8. Nested Routes

```jsx
<Routes>
  <Route path="/dashboard" element={<Dashboard />}>
    <Route path="stats" element={<Stats />} />
    <Route path="settings" element={<Settings />} />
  </Route>
</Routes>
```

Render child route with `<Outlet />` in `Dashboard`.

```jsx
import { Outlet } from "react-router-dom";

function Dashboard() {
  return (
    <div>
      <h1>Dashboard</h1>
      <Outlet />
    </div>
  );
}
```

## 9. Not Found Route

```jsx
<Route path="*" element={<h1>404 Not Found</h1>} />
```

## 10. Protected Routes

```jsx
function PrivateRoute({ children }) {
  const isLoggedIn = false; // example
  return isLoggedIn ? children : <Navigate to="/login" />;
}

<Route
  path="/profile"
  element={
    <PrivateRoute>
      <Profile />
    </PrivateRoute>
  }
/>;
```
