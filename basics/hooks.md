# React Hooks Guide
< [back](../README.md)

## What Are Hooks?

React Hooks zijn speciale functies die je in staat stellen om React-functionaliteiten te gebruiken binnen je componenten.

Je kunt hooks zien als "tools" die je component meer mogelijkheden geven.

---

## useState

### Wat het doet:
Laat je component **waarden onthouden** (zoals een teller, een naam, enz.).

### Voorbeeld:

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
````

* `useState(0)` maakt een variabele `count` aan en zet deze standaard op 0.
* `setCount` is een functie die de waarde bijwerkt.

---

## useEffect

### Wat het doet:

Voert code uit wanneer je component **laadt**, **bijwerkt** of **wordt verwijderd**.

### Voorbeeld:

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

* De lege array `[]` betekent dat dit effect maar één keer wordt uitgevoerd — wanneer de component voor het eerst laadt.

---

## useContext

### Wat het doet:

Laat je data delen (zoals een thema, gebruikersinfo of taalinstelling) met meerdere componenten zonder handmatig props door te geven op elk niveau.

Dit is handig wanneer meerdere componenten toegang nodig hebben tot dezelfde data.

### Voorbeeld:

Maak eerst een context aan (dit doe je **buiten** een component):

```tsx
import { createContext } from 'react';

export const ThemeContext = createContext('light');
```

Wikkel daarna je app in de provider (hier sla je de waarde daadwerkelijk op; alleen child-componenten hebben toegang):

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

In een andere component die een child is van de provider gebruik je useContext om de waarde te krijgen (of te zetten):

```tsx
import { useContext } from 'react';
import { ThemeContext } from './ThemeContext';

function Page() {
  const theme = useContext(ThemeContext);

  return <div>The current theme is {theme}</div>;
}
```

### Waarom `useContext` gebruiken?

Zonder context zou je dit moeten doen:

```tsx
<App theme="dark">
  <Layout theme="dark">
    <Page theme="dark" />
  </Layout>
</App>
```

Met context **geef je het slechts één keer mee**, en alle child-componenten kunnen het gebruiken.

---

## useRef

### Wat het doet:

Geeft je een manier om een DOM-element (zoals een inputveld) te refereren, of een waarde op te slaan zonder dat er een her-render plaatsvindt.

### Voorbeeld:

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

* Gebruik hooks altijd **bovenaan** je component (niet binnen if-statements of loops).
* Hooks moeten **beginnen met "use"** — zoals `useState`, `useEffect`.
* Gebruik hooks alleen **binnen React function components**.

---

## Learn More

Wil je dieper in de materie duiken? Bekijk dan:

* 🔗 [React Official Docs on Hooks](https://react.dev/learn/state-a-components-memory)
* 🔗 [W3Schools React Hooks](https://www.w3schools.com/react/react_hooks.asp)
