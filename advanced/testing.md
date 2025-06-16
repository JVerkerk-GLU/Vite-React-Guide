# Testing & Debugging
< [back](../README.md)

---

## Why Test?

Testing helps ensure your app works correctly and prevents bugs from slipping into production.

Types of tests:

- **Unit tests**: Test individual functions or components
- **Component tests**: Test React components and their UI behavior

---

## Popular Testing Tools

- [Jest](https://jestjs.io/) — JavaScript testing framework
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) — For testing React components
- [Vitest](https://vitest.dev/) — Vite-native test runner (optional alternative to Jest)

---

## Getting Started with Testing

Install dependencies:

```bash
npm install --save-dev jest @testing-library/react @testing-library/jest-dom
````

Add this to your `package.json` scripts:

```json
"test": "jest"
```

---

## Example Unit Test

Create a simple function to test:

```ts
// utils/sum.ts
export function sum(a: number, b: number): number {
  return a + b
}
```

Test it:

```ts
// utils/sum.test.ts
import { sum } from './sum'

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3)
})
```

Run tests:

```bash
npm test
```

---

## Component Testing Example

Testing a React component:

```tsx
// components/Counter.tsx
import { useState } from 'react'

export function Counter() {
  const [count, setCount] = useState(0)

  return (
    <>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </>
  )
}
```

Test:

```tsx
// components/Counter.test.tsx
import { render, screen, fireEvent } from '@testing-library/react'
import { Counter } from './Counter'

test('increments counter', () => {
  render(<Counter />)
  const button = screen.getByText('Increment')
  fireEvent.click(button)
  expect(screen.getByText('Count: 1')).toBeInTheDocument()
})
```

---

## Debugging Tools

### Browser DevTools

* Inspect elements, view console logs, and debug network requests.
* Use React DevTools extension for inspecting React component hierarchy and props/state.

### VSCode Debugger

* Set breakpoints inside `.tsx` files.
* Launch/debug React apps using `launch.json` configuration.
* Debug console and variable watch helps trace issues in real time.

---

## Learn More

* [React Testing Library Docs](https://testing-library.com/docs/react-testing-library/intro/)
* [Jest Docs](https://jestjs.io/docs/getting-started)
* [VSCode Debugging for React](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial)
* [React DevTools](https://reactjs.org/blog/2019/08/15/new-react-devtools.html)