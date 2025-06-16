# Routing
< [back](../README.md)

---

## What Is Routing?

Routing laat je app navigeren tussen verschillende **pagina’s** of **weergaven**. In React wordt dit meestal geregeld met de bibliotheek **React Router**.

In plaats van de volledige pagina opnieuw te laden, verandert React Router de URL en wisselt dynamisch van component — waardoor je app aanvoelt als een **Single Page Application (SPA)**.

---

## Installing React Router

```bash
npm install react-router-dom
````

---

## Basic Setup

In je `main.tsx`, omhul je je app met een `<BrowserRouter>`:

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

Daarna definieer je routes in `App.tsx`:

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

Maak componenten aan in de `src/pages/` map:

```tsx
// pages/Home.tsx
export default function Home() {
  return <h1>Welkom thuis</h1>
}
```

```tsx
// pages/About.tsx
export default function About() {
  return <h1>Over ons</h1>
}
```

---

## Navigation with Links

Gebruik de `<Link />` component in plaats van `<a>`:

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

Je kunt layouts maken met geneste `<Outlet />` componenten:

```tsx
// App.tsx
<Route path="/dashboard" element={<DashboardLayout />}>
  <Route path="profile" element={<Profile />} />
  <Route path="settings" element={<Settings />} />
</Route>
```

In `DashboardLayout.tsx`:

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

Voeg helemaal onderaan een wildcard route toe met een asterisk `*`:

```tsx
<Route path="*" element={<h1>404 - Pagina niet gevonden</h1>} />
```

---

## Learn More

* 🔗 [React Router Docs](https://reactrouter.com/en/main)
* 🔗 [React Router Tutorial (w3schools)](https://www.w3schools.com/react/react_router.asp)