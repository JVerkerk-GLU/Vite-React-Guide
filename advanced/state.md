# State Management
< [back](../README.md)

---

## What Is State?

State is how React remembers information between renders. It can be anything: a user's input, a theme toggle, or fetched data.

React provides built-in tools for managing state, and for larger apps, you can bring in libraries like Zustand or Redux.

---

## Local State with useState

The most common way to handle component state:

```tsx
import { useState } from 'react'

function Counter() {
  const [count, setCount] = useState(0)

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  )
}
````

* `useState(0)` sets the initial value to 0
* `setCount` updates the value

---

## Sharing State with Props

You can pass state and functions to child components:

```tsx
function Parent() {
  const [theme, setTheme] = useState("light")
  return <Child theme={theme} toggleTheme={() => setTheme(theme === "light" ? "dark" : "light")} />
}
```

```tsx
function Child({ theme, toggleTheme }: { theme: string; toggleTheme: () => void }) {
  return <button onClick={toggleTheme}>Current Theme: {theme}</button>
}
```

---

## App-Wide State with useContext

If many components need the same state, use **Context**:

```tsx
// ThemeContext.tsx
import { createContext, useContext, useState } from 'react'

const ThemeContext = createContext<any>(null)

export function ThemeProvider({ children }: { children: React.ReactNode }) {
  const [theme, setTheme] = useState("light")
  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      {children}
    </ThemeContext.Provider>
  )
}

export const useTheme = () => useContext(ThemeContext)
```

Wrap your app in `ThemeProvider` in `main.tsx`, then use `useTheme()` in any component.

---

## Zustand (Lightweight Global State)

[Zustand](https://zustand-demo.pmnd.rs/) is a simple and fast state management library.

```bash
npm install zustand
```

Create a store:

```ts
// useCounterStore.ts
import { create } from 'zustand'

export const useCounterStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 }))
}))
```

Use it in any component:

```tsx
import { useCounterStore } from './useCounterStore'

function Counter() {
  const { count, increment } = useCounterStore()
  return <button onClick={increment}>Clicked {count} times</button>
}
```

---

## When to Use What?

| Situation                 | Recommendation  |
| ------------------------- | --------------- |
| UI element, form input    | `useState`      |
| Multiple components share | `useContext`    |
| Large or complex app      | Zustand / Redux |

---

## Learn More

* [React Docs – State](https://react.dev/learn/state-a-components-memory)
* [Zustand Docs](https://docs.pmnd.rs/zustand/introduction)
* [React Context – w3schools](https://www.w3schools.com/react/react_context.asp)