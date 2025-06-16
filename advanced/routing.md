# Routing
< [back](../README.md)

---

## What Is Routing?

Routing allows your app to navigate between different **pages** or **views**. In React, this is typically handled by the library **React Router**.

Instead of reloading the whole page, React Router changes the URL and swaps components dynamically — giving your app a **Single Page Application (SPA)** experience.

---

## Installing React Router

```bash
npm install react-router-dom
````

---

## Basic Setup

In your `main.tsx`, wrap your app in a `<BrowserRouter>`:

```tsx
// main.tsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import { BrowserRouter } from 'react-router-dom'
import App from './App'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
)
```

Then define routes inside `App.tsx`:

```tsx
// App.tsx
import { Routes, Route } from 'react-router-dom'
import Home from './pages/Home'
import About from './pages/About'

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  )
}
```

---

## Creating Pages

Create components in the `src/pages/` folder:

```tsx
// pages/Home.tsx
export default function Home() {
  return <h1>Welcome Home</h1>
}
```

```tsx
// pages/About.tsx
export default function About() {
  return <h1>About Us</h1>
}
```

---

## Navigation with Links

Use the `<Link />` component instead of `<a>`:

```tsx
import { Link } from 'react-router-dom'

function NavBar() {
  return (
    <nav>
      <Link to="/">Home</Link> | <Link to="/about">About</Link>
    </nav>
  )
}
```

---

## Nested Routes (Optional)

You can create layouts with nested `<Outlet />` components:

```tsx
// App.tsx
<Route path="/dashboard" element={<DashboardLayout />}>
  <Route path="profile" element={<Profile />} />
  <Route path="settings" element={<Settings />} />
</Route>
```

Inside `DashboardLayout.tsx`:

```tsx
import { Outlet } from 'react-router-dom'

export default function DashboardLayout() {
  return (
    <div>
      <h2>Dashboard</h2>
      <Outlet />
    </div>
  )
}
```

---

## Handling 404 Pages

Add a wildcard route at the end using an asterisk `*`:

```tsx
<Route path="*" element={<h1>404 - Page Not Found</h1>} />
```

---

## 🔗 Learn More

* [React Router Docs](https://reactrouter.com/en/main)
* [React Router Tutorial (w3schools)](https://www.w3schools.com/react/react_router.asp)