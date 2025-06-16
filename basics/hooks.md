# React Hooks Guide
< [back](../README.md)

## What Are Hooks?

React Hooks are special functions that let you use React features inside your components.

Before hooks, you had to write **class components** to use things like state or lifecycle methods. Now you can do all of that with simpler **function components**.

You can think of hooks as "tools" that help your component do more things.

---

## useState

### What it does:
Lets your component **remember values** (like a counter, a name, etc).

### Example:

```tsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
}
```

- `useState(0)` creates a variable called `count` and sets it to 0 at first.
- `setCount` is a function that updates the value.

---

## useEffect

### What it does:
Runs code when your component **mounts**, **updates**, or **cleans up**.

### Example:

```tsx
import { useEffect } from 'react';

function App() {
  useEffect(() => {
    console.log('Component mounted');

    return () => {
      console.log('Component will unmount');
    };
  }, []);

  return <h1>Hello</h1>;
}
```

- The empty array `[]` means this effect runs only once — when the component first loads.

---

## useContext

### What it does:
Lets you share data (like a theme, user info, or language setting) with many components without passing props down manually through every level.

This is helpful when multiple components need access to the same data.

### Example:

First, create a context (note that you create a context **outside** a function of a component):

```tsx
import { createContext } from 'react';

export const ThemeContext = createContext('light');
```

Now wrap your app with the provider (this is where you actually store the value, only child elements have access to the value):
```tsx
import { ThemeContext } from './ThemeContext';

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Page />
    </ThemeContext.Provider>
  );
}
```

Inside any other component that is a child of the provider, use useContext to get (or set) the value:

```tsx
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

function Page() {
  const theme = useContext(ThemeContext);

  return <div>The current theme is {theme}</div>;
}
```

### Why use `useContext`?

Without it, you'd have to do this:
```tsx
<App theme="dark">
  <Layout theme="dark">
    <Page theme="dark" />
  </Layout>
</App>
```
With context, you **only provide it once**, and all child components can access it.

---

## useRef

### What it does:
Gives you a way to reference a DOM element (like an input field), or store a value without causing a re-render.

### Example:

```tsx
import { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef(null);

  const handleClick = () => {
    inputRef.current?.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={handleClick}>Focus the input</button>
    </div>
  );
}
```

---

## Tips for Using Hooks

- Always use hooks **at the top** of your component (not inside if-statements or loops).
- Hooks **must start with "use"** — like `useState`, `useEffect`.
- Only use hooks **inside React function components**.

---

## Learn More

Want to go deeper? Check these out:

🔗 [React Official Docs on Hooks](https://react.dev/learn/state-a-components-memory)  
🔗 [W3Schools React Hooks](https://www.w3schools.com/react/react_hooks.asp)
