# Installing Packages
< [back](../README.md)

## What Are Packages?

Packages zijn **herbruikbare stukjes code** die door andere developers zijn gemaakt, en die je aan je eigen project kunt toevoegen.

Ze besparen je tijd en zorgen dat je het wiel niet opnieuw hoeft uit te vinden — je kunt bijvoorbeeld een package installeren voor animaties, iconen, routing of UI-componenten.

We gebruiken een tool genaamd **npm** (Node Package Manager) om packages te installeren.

---

## Install Packages

Om een package te installeren, open je de terminal en typ je:

```bash
npm install <package-name>
````

### Example

```bash
npm install react-icons
```

Dit voegt de package toe aan je project zodat je het in je code kunt gebruiken.

---

## Using an Installed Package

Na het installeren importeer je de package meestal bovenaan je `.tsx` bestand.

Voorbeeld met `react-icons`:

```tsx
import { FaBeer } from 'react-icons/fa';

function App() {
  return <h1>Cheers! <FaBeer /></h1>;
}
```

---

## Dev Packages

Sommige packages zijn alleen nodig tijdens het ontwikkelen (zoals formatteertools of testtools). Voor die gevallen gebruik je `-D`:

```bash
npm install -D prettier
```

Deze worden niet meegenomen in de uiteindelijke productieversie van je app.

---

## Remove a Package

Heb je per ongeluk iets geïnstalleerd of gebruik je het niet meer?

```bash
npm uninstall <package-name>
```

---

## Updating Packages

Je kunt controleren of er verouderde packages zijn met:

```bash
npm outdated
```

Om alles bij te werken dat veilig geüpdatet kan worden:

```bash
npm update
```

---

## Useful Package Examples

* **UI Libraries**: [Tailwind CSS](https://tailwindcss.com/), [Radix UI](https://www.radix-ui.com/), [Material UI](https://mui.com/)
* **Routing**: [React Router](https://reactrouter.com/)
* **State Management**: [Zustand](https://zustand-demo.pmnd.rs/), [Redux](https://redux.js.org/), [Jotai](https://jotai.org/)
* **Development Tools**: [ESLint](https://eslint.org/), [Prettier](https://prettier.io/)
* **Testing**: [Vitest](https://vitest.dev/), [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)

---

## Learn More

* 🔗 [npm Docs](https://docs.npmjs.com/)
* 🔗 [React Awesome Packages](https://reactjsexample.com/)