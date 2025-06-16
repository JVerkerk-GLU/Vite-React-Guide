# State Management
< [back](../README.md)

---

## What Is State?

State is hoe React informatie onthoudt tussen renders. Het kan van alles zijn: invoer van een gebruiker, een thema-toggle of opgehaalde data.

React heeft ingebouwde tools voor het beheren van state, en voor grotere apps kun je extra bibliotheken gebruiken zoals Zustand of Redux.

---

## Local State with useState

De meest gebruikte manier om component-state te beheren:

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

* `useState(0)` stelt de beginwaarde in op 0
* `setCount` wijzigt de waarde

---

## Sharing State with Props

Je kunt state en functies doorgeven aan child components:

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

Als meerdere componenten dezelfde state nodig hebben, gebruik je **Context**:

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

Omhul je app met `ThemeProvider` in `main.tsx`, en gebruik `useTheme()` in elke component.

---

## Zustand (Lightweight Global State)

[Zustand](https://zustand-demo.pmnd.rs/) is een eenvoudige en snelle bibliotheek voor state management.

```bash
npm install zustand
```

Maak een store aan:

```ts
// useCounterStore.ts
import { create } from 'zustand'

export const useCounterStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 }))
}))
```

Gebruik deze store in een component:

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

* 🔗 [React Docs – State](https://react.dev/learn/state-a-components-memory)
* 🔗 [Zustand Docs](https://docs.pmnd.rs/zustand/introduction)
* 🔗 [React Context – w3schools](https://www.w3schools.com/react/react_context.asp)