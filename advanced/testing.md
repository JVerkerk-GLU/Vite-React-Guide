# Testing & Debugging
< [back](../README.md)

---

## Why Test?

Testen zorgt ervoor dat je app correct werkt en voorkomt dat bugs in productie terechtkomen.

Soorten tests:

- **Unit tests**: Testen van individuele functies of componenten
- **Component tests**: Testen van React-componenten en hun UI-gedrag

---

## Popular Testing Tools

- [Jest](https://jestjs.io/) — JavaScript-testframework
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/) — Voor het testen van React-componenten
- [Vitest](https://vitest.dev/) — Vite-native testrunner (optioneel alternatief voor Jest)

---

## Getting Started with Testing

Installeer de testafhankelijkheden:

```bash
npm install --save-dev jest @testing-library/react @testing-library/jest-dom
````

Voeg dit toe aan de scripts in je `package.json`:

```json
"test": "jest"
```

---

## Example Unit Test

Schrijf een eenvoudige functie om te testen:

```ts
// utils/sum.ts
export function sum(a: number, b: number): number {
  return a + b
}
```

Test deze functie:

```ts
// utils/sum.test.ts
import { sum } from './sum'

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3)
})
```

Voer de tests uit:

```bash
npm test
```

---

## Component Testing Example

Een React-component testen:

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

Testbestand:

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

* Inspecteer elementen, bekijk consolelogs en debug netwerkverzoeken.
* Gebruik de React DevTools-extensie om de componenthiërarchie en props/state te bekijken.

### VSCode Debugger

* Zet breakpoints in `.tsx`-bestanden.
* Start/debug React-apps met een `launch.json`-configuratie.
* De debugconsole en variabeleweergave helpen je realtime bij het opsporen van fouten.

---

## Learn More

* 🔗 [React Testing Library Docs](https://testing-library.com/docs/react-testing-library/intro/)
* 🔗 [Jest Docs](https://jestjs.io/docs/getting-started)
* 🔗 [VSCode Debugging for React](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial)
* 🔗 [React DevTools](https://reactjs.org/blog/2019/08/15/new-react-devtools.html)